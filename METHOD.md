# Method

How to run an update of this repository. Written after the September 2026 pass, which found that
a refresh consisting only of new material leaves the old material wrong and the summaries built
on it wrong too.

Read this before starting. Read `skills/verification.md` for the failure modes and the mechanical
checks.

## The governing rule

**Adding sources is half the job. The other half is verifying what is already here.**

The January 2026 corpus held 148 excerpts. The September 2026 refresh added 82 new ones from 71
new sources with zero overlap against the existing 100, and opened none of the existing files.
Verification afterwards found that the repository's most-quoted figure appeared in no version of
its cited paper, that one file named the wrong authors and took both its headline claims from a
different study, and that several excerpts asserted data-centre relevance their sources never
claimed. Every one of those had been sitting in the corpus being cited.

Plan an update as audit, search, verify, prune, rebuild. Not as search alone.

## Phases

### Phase 0. Audit before touching anything

Run the mechanical checks in `skills/verification.md` and produce a written audit. Establish:

- How many excerpts, how many unique sources, how much duplication
- Which excerpts are cited in a README or carry numbers (these are load-bearing)
- Which excerpts mention AI or data centres fewer than three times (candidates for off-topic)
- Which excerpts lack a system boundary, a funding note, or a `Type` field
- Which claims in README and RESEARCH_PLAN have no supporting file

The last one matters most. A headline number with no file behind it is either unsourced or
mis-sourced, and it has usually been repeated.

### Phase 1. Ask before scoping

Decisions that change the work and belong to the user: how wide the pass goes, whether corporate
and agency primaries are admitted, which areas to prioritise, whether summaries get rewritten.
Ask once, with the audit findings attached so the choice is informed. Do not ask about anything
the audit or the repository already settles.

### Phase 2. Search in parallel, one agent per area

One agent per topic folder, each owning that folder exclusively. Give every agent:

- The shared brief (recency window, source hierarchy, format, hard rules, style)
- Its starting file number, so numbering never collides
- Named targets. "Find the IEA *Energy and AI* TWh figures and the scenario ranges" produces
  better work than a keyword like "AI energy"
- Instructions to report negative results, which mark where evidence does not exist

Agents must not edit `_index.md` or `README.md`. The orchestrator rebuilds those at the end from
the final file state, which avoids write conflicts and keeps the summaries consistent with what
actually exists.

### Phase 3. Verify what the summaries cite

Any excerpt that a summary cites, or that carries a number, gets re-pulled against full text.
This is not optional and it is where the errors are.

Verification means: retrieve the source, confirm each number exists in it, attach the system
boundary, record funding and affiliation, and state whether the figure is measured, modelled,
estimated or projected. If the source cannot be reached, say so in the file and mark what could
not be checked. Never carry a number forward because the corpus already contains it.

`DELETE` is a valid outcome. An excerpt that misdescribes its source is worse than no excerpt.

### Phase 4. Prune

Remove, in this order:

1. Sources with no AI or data-centre content, where relevance was asserted by the excerpt rather
   than claimed by the source
2. Duplicate write-ups. One canonical file per source; cross-reference from the other folder's
   index
3. Files whose claims did not survive verification and cannot be repaired

Removals are recoverable from git history. Record the reason in the commit message.

### Phase 5. Rebuild summaries from the final state

Regenerate every `_index.md` mechanically from the files that exist. Rewrite each folder
`README.md` and the root `README.md` from the verified numbers, not from the previous version of
the summary. A summary rewritten by editing the old one carries the old one's errors forward.

Every figure in a summary must trace to a file that was verified in this pass. If it does not,
either verify it now or cut it.

### Phase 6. Mechanical verification

Run the full check suite in `skills/verification.md`. Nothing ships with a broken link, an
orphaned file, a numbering collision, or an unresolvable URL.

### Phase 7. Commit

One commit per phase group, with the corrections named in the message. The commit message is
where edit history lives.

## Working state, not changelog

Files describe the current state of the evidence. They carry no `supersedes`, `corrected`,
`previously stated`, or `correction needed` annotations. When an excerpt is wrong, write the
right thing; git history records the change and the commit message names it.

`Relation to existing corpus` is for genuine relationships between different sources: this
confirms, contradicts, or bounds that. It is not for narrating edits.

Report corrections to the user in conversation. That is where they are useful.

## Subagent design

What worked:

- **Exclusive file ownership.** Each agent owns a folder or an explicit file list. No agent edits
  another's files or any index.
- **One agent per source, not per folder, when a source appears in several folders.** Five
  write-ups of one paper made five different claims about it. Reading it once settles all five.
- **Named targets in the prompt.** Specific documents, specific disputed figures, specific
  questions to settle.
- **Ask for errors in the report, not in the files.** The agent's final message is the right
  place for "this number was wrong"; the file gets the corrected version.
- **Tell agents what is already known.** Give them the verified findings that bear on their area
  so they cross-check instead of rediscovering.

What to watch: agents working concurrently on related sources will sometimes reach the same
conclusion independently. That agreement is evidence. Two agents independently recovering the
same corrected figure from the same paper is a stronger signal than either alone.

## Cross-checking

Three checks that have each caught real errors here:

**Duplicate disagreement.** When one source has several write-ups, compare what they claim. If
two files make incompatible claims about the same paper, at least one is wrong, and usually both
were written from the abstract.

**Boundary arithmetic.** When two figures for the same quantity differ by a large factor, compute
whether the ratio is explained by a boundary difference before treating it as a dispute. Scope 1
against scope 1+2, market-based against location-based, withdrawal against consumption, and
accelerator-only against full-stack each produce large factors that are not disagreements.

**Derivation from the source's own inputs.** Where a paper reports a ratio, recompute it from the
paper's own stated inputs. A published ratio that does not follow from the paper's own numbers
has been found here more than once.

## Known environment gotchas

- `zsh` does not word-split unquoted variables. `for f in $list` iterates once over the whole
  string. Use a file and `while read`, or `${=var}`.
- `$d[0-9]` in zsh is array subscripting, not globbing. Use `"${d}"[0-9]*.md`.
- Basename collisions across folders will match the wrong file in a `grep -l` loop. Match on the
  full path.
- `WebFetch` returns binary for PDFs. Download and run `pdftotext -layout`.
- Several publishers return 403 to automated requests but serve the same text elsewhere. See
  `skills/primary-sources.md`.
