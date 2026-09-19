# Verification Skill

Failure modes found in this corpus, and the checks that catch them. Every entry below is an
error that was actually present and was corrected, not a hypothetical.

## Failure modes

### Manufactured relevance

A source about something else, with a "Relevance to Data Centers" section the excerpt author
invented. Found in excerpts citing recycled water in building construction, a chemical-site
cooling tower, a Ukrainian power plant, lithium-ion battery recycling, and general ESG theory.

**Check:** does the source itself mention AI, data centres, or computing? If the relevance
appears only in the excerpt, the file goes.

```bash
grep -ciE "artificial intelligence|\bAI\b|\bLLM|machine learning|data.?cent(re|er)|GPU|hyperscal|inference" FILE
```

### Claims taken from a different paper

One file's two headline claims were verbatim from another study's abstract. The cited paper
contained neither.

**Check:** find each headline number in the retrieved full text. If it is not there, it is not
the paper's.

### Misattributed citation

One file named an author's first name as the lead surname, producing an author list that matches
no publication.

**Check:** confirm the author list against Crossref, not against the existing excerpt. One call,
in `skills/metadata.md`. A wrong DOI returns a different paper entirely, which is the signal.

### Back-computed figures attributed to a source

The most-quoted figure in this corpus, "10 to 25 mL per ChatGPT query", appears in no version of
the paper it was credited to. It was derived by dividing a superseded preprint's wording. The
paper's own table gives different numbers.

**Check:** the figure must appear in the source as a figure. A number arrived at by arithmetic on
the source's prose is the excerpt author's estimate and must be labelled as one.

### Boundary mismatch presented as disagreement

Comparing a scope-1 figure against a scope 1+2 total produced an apparent 40x to 100x gap between
two water estimates. The like-for-like ratio is 8.5x.

**Check:** before reporting two figures as conflicting, establish that they share a boundary.
The recurring pairs:

| Pair | Typical factor |
|---|---|
| Water withdrawal against consumption | ~10x for generation |
| On-site (scope 1) against on-site + generation (scope 1+2) | 3x to 8x |
| Market-based against location-based Scope 2 | 4x to 4,400x |
| Accelerator-only against full-stack PUE-inclusive energy | ~2.4x |
| Announced against energised capacity | years, and multiples |

### Ratio that does not follow from the source's own inputs

A paper reporting 130x to 1,500x gives inputs that yield 82x to 875x. A "~20x" efficiency claim
computes to 18.3x, of which 6.4x is an electricity emission-factor ratio and not a property of
the hardware.

**Check:** recompute every published ratio from the paper's own stated inputs.

### Counterfactual not established

An AI-against-human emissions comparison charged the human a pro-rata share of their entire
national annual footprint across all 8,760 hours of the year. The human emits the same whether
performing the task or not.

**Check:** what would have happened without the AI? A baseline that allocates existing emissions
by time spent, with no behavioural alternative, establishes nothing.

### Aggregate that is an artefact

An "average PUE 2.23" is the reciprocal of an unweighted mean of six undated published IT-share
figures, four of them illustrative diagrams. It is not a fleet average.

**Check:** what population, what period, what weighting. An average with no denominator is not an
average.

### Self-reported range with no common definition

"Energy savings up to 115%" aggregates 27 studies, each self-reported against its own baseline,
with the review defining no metric. A saving above 100% is the tell.

**Check:** does the review define the quantity it is aggregating? If not, the range is not a
range.

### Macro panel presented as causal

AI proxied by industrial-robot stock over 1993 to 2019, or technological innovation proxied by
patent counts, with system-GMM internal instruments. Coefficients of -0.0018 sit beside an
energy-use control of +0.1673 in the same regression.

**Check:** state the proxy, the period, the estimator, and the coefficient against its own
controls. A panel ending before generative AI says nothing about generative AI.

### Laboratory demonstration presented as deployment

Simulated ASICs benchmarked against fabricated GPUs two process generations newer;
batch-size-1 results whose advantage vanishes by batch 64; devices on 180 nm and 500 nm nodes.

**Check:** fabricated or simulated, what process node, what batch size, what duty cycle, what
baseline software stack. Specialised silicon idles at 30 to 80% of TDP against about 20% for
GPUs, so any "Nx more efficient" claim needs a duty cycle to mean anything.

### Citation count as authority

"578 citations, exceptionally influential." Counts go stale, are sometimes impossible (a count
dated before the paper's publication was found twice), and say nothing about whether a claim is
correct.

**Check:** do not use citation counts as evidence. If a count is recorded, date it and name the
index. Verified here: an excerpt claiming "578 citations, exceptionally high" against a current
Crossref figure of 1,361.

```bash
# impossible counts: publication year later than the "as of" year
grep -rlE "citations as of" research/*/[0-9]*.md
```

## Mechanical checks

Run all of these before committing.

```bash
cd /Users/olivier/DEV/research-ai-energy

# 1. Index rows point at files that exist
for d in research/*/; do
  grep -oE '\(([0-9]{3}-[^)]+\.md)\)' "${d}_index.md" | tr -d '()' | while read b; do
    [ -f "${d}${b}" ] || echo "BROKEN ${d}${b}"
  done
done

# 2. Every excerpt appears in its index
for d in research/*/; do
  for f in "${d}"[0-9]*.md; do
    b=$(basename "$f"); grep -q "($b)" "${d}_index.md" || echo "ORPHAN $f"
  done
done

# 3. No sequence-number collisions
for d in research/*/; do ls "$d" | grep -oE '^[0-9]{3}' | sort | uniq -d | sed "s|^|$d |"; done

# 4. Every excerpt has a URL
for f in $(find research -name "[0-9]*.md"); do
  grep -q "^\*\*URL:\*\*" "$f" || echo "NO URL $f"
done

# 5. Links in the top-level docs resolve
for m in README.md METHOD.md RESEARCH_PLAN.md CLAUDE.md research/*/README.md; do
  grep -oE '\]\((research/[^)]+|skills/[^)]+|[A-Z_]+\.md)\)' "$m" | tr -d ']()' | sort -u | \
    while read p; do [ -e "$p" ] || echo "MISSING in $m: $p"; done
done

# 6. Source URLs resolve (403 means bot-blocked, not dead)
grep -rh --include="[0-9]*.md" "^\*\*URL:\*\*" research/ | sed 's/^\*\*URL:\*\* *//' | sort -u | \
  while read u; do
    c=$(curl -s -o /dev/null -w "%{http_code}" -L --max-time 20 "$u")
    case "$c" in 200|301|302|202|403) ;; *) echo "FAIL $c $u";; esac
  done

# 7. Sources held in more than one file. Not automatically wrong: a large agency or corporate
#    report can support distinct findings in distinct folders. Each hit needs a human judgment
#    that the findings genuinely differ, and each file should name the other in its
#    "Relation to existing corpus" section.
grep -rh --include="[0-9]*.md" "^\*\*URL:\*\*" research/ | sed 's/^\*\*URL:\*\* *//' | \
  sort | uniq -c | awk '$1>1'

# 8. Format compliance
for field in '\*\*Type:' '\*\*Published:' '^## Finding' '^## Methodology' '^## Limitations'; do
  n=$(grep -rLE "$field" research/*/[0-9]*.md | wc -l)
  echo "$field missing from $n files"
done

# 9. House style (the grep pattern below matches its own line; ignore that hit)
for f in README.md METHOD.md CLAUDE.md RESEARCH_PLAN.md research/*/README.md; do
  n=$(( $(grep -c '—' "$f") + $(grep -coE 'rather than|not just|instead of' "$f") ))
  [ "$n" -gt 0 ] && echo "$f: $n style hits"
done

# 10. No changelog scaffolding in the corpus
grep -rln "supersede\|correction needed\|Corrected excerpt\|Gap closed" \
  research/*/[0-9]*.md research/*/_index.md research/*/README.md README.md
```

## Shell gotchas that have produced wrong results here

- `zsh` does not word-split unquoted variables. `for f in $list` iterates once over the whole
  string and silently does nothing useful. Write the list to a file and use `while read`.
- `$d[0-9]` is array subscripting in zsh, not a glob. Use `"${d}"[0-9]*.md`.
- Matching a basename across folders hits the wrong file when two folders hold the same
  filename. Match full paths.
- `curl -I` returns 403 where `GET` succeeds on several publishers. Do not validate with HEAD.
