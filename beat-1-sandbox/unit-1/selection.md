# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

(https://github.com/codepath/pathreview-ai301-fa26-s3/issues/56)

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
Skill(issue-select)
Successfully loaded skill

  Read 3 files, ran 2 shell commands

⏺ Auto mode lets Claude handle permission prompts automatically — Claude checks each tool call for risky actions and prompt injection before executing. Actions Claude identifies as safe are executed, while actions Claude identifies as risky are blocked and Claude may try a different approach. Ideal for long-running tasks. Sessions are slightly more expensive. Claude can make mistakes that allow harmful commands to run, it's recommended to only use in isolated environments. Shift+Tab to change mode.

Good, curl works with the GitHub API. Let me gather all the needed facts.

  Ran 3 shell commands

Found docs/CONTRIBUTING.md. Let me check its AI policy.

  Ran 3 shell commands

All three unassigned, opened by a Collaborator. Now let's check comments and linked PRs for each.

  Ran 2 shell commands

No linked PRs for any issue. Now let's check maintainer response time — the maintainer-alive check via issue thread responses, plus check the fit profile (empty placeholder in scope.md, so I'll note it's unfilled and skip ranking by fit, or use generic reasoning).

  Ran 2 shell commands

Here's the grading. Note: scope.md's "fit profile" section is still the unfilled placeholder ("(Write a few sentences here.)"), so I ranked the accepted issues by general newcomer-friendliness (bounded scope, low ambiguity) rather than personal fit — fill that section in if you want future rankings tailored to you.

All three pass every required check — all are viable first issues.

┌─────────────────────────┬───────────────────────────────────────────────────────┬───────────────────────────────┬────────────────────────┐
│          Check          │             #68 (BM25 ZeroDivisionError)              │ #56 (chunker drops headings)  │   #47 (API.md curl     │
│                         │                                                       │                               │       examples)        │
├─────────────────────────┼───────────────────────────────────────────────────────┼───────────────────────────────┼────────────────────────┤
│ maintainer-alive        │ pass — 5/5 recent commits by human (Andrew Burke),    │ pass — same                   │ pass — same            │
│                         │ latest 6 days ago                                     │                               │                        │
├─────────────────────────┼───────────────────────────────────────────────────────┼───────────────────────────────┼────────────────────────┤
│ repo-in-use             │ pass — not archived, last push 6 days ago             │ pass                           │ pass                   │
├─────────────────────────┼───────────────────────────────────────────────────────┼───────────────────────────────┼────────────────────────┤
│                         │ pass — a classmate (NONE association) commented "I'd  │ pass — no assignees,           │ pass — no assignees,   │
│ unclaimed               │ like to take this on"; house rule says student claims │ comments, or linked PRs        │ comments, or linked    │
│                         │  don't block                                          │                               │ PRs                    │
├─────────────────────────┼───────────────────────────────────────────────────────┼───────────────────────────────┼────────────────────────┤
│ ai-contribution-allowed │ pass — CONTRIBUTING.md is silent on AI, no ban        │ pass                           │ pass                   │
├─────────────────────────┼───────────────────────────────────────────────────────┼───────────────────────────────┼────────────────────────┤
│                         │ pass — one function, 2 named files, repro described,  │ pass — one function, repro     │ pass — single doc      │
│ scope-bounded           │ 2-4h estimate                                         │ steps + failing test named,    │ file                   │
│                         │                                                       │ single fix                     │                        │
└─────────────────────────┴───────────────────────────────────────────────────────┴───────────────────────────────┴────────────────────────┘

Ranking (all accepted):
1. #56 – tightest, most concrete: reproduction snippet included, a specific pre-existing xfail test already pins the expected fix, single file/function. Lowest ambiguity of the three.
2. #68 – equally well-scoped (specific files, xfail test to un-mark, effort estimate given), just nudged behind #56 only because someone else already commented intent to work it — not a blocker per the house rule, but a tiebreaker if you'd rather avoid overlap.
3. #47 – bounded and easy, but it's pure documentation (no code/test to touch), so it teaches less of the actual PR workflow (no CI test-suite interaction, no xfail marker to remove) than the other two.

[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/56",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "last 5 default-branch commits all by Andrew Burke (human), most recent 2026-09-16, 6 days before capture"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived: false; pushed_at 2026-09-16 (6 days before capture)"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: []; issue comments: none; PR search for #56 returns 0 results"},
      {"name": "ai-contribution-allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no mention of AI-generated/AI-assisted contributions"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "body gives a runnable repro snippet and names the exact failing test test_document_with_no_headings; single-function fix"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "last 5 default-branch commits all by Andrew Burke (human), most recent 6 days before capture"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived: false; pushed_at 2026-09-16 (6 days before capture)"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: []; comment from acordero4852 (author_association: NONE, a classmate) saying 'I'd like to take this one on' — house rule: student claim comments do not block; no linked PRs"},
      {"name": "ai-contribution-allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no mention of AI-generated/AI-assisted contributions"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "body names two exact files, a specific xfail test id (H-01), and gives a 2-4h effort estimate"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/47",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "last 5 default-branch commits all by Andrew Burke (human), most recent 6 days before capture"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived: false; pushed_at 2026-09-16 (6 days before capture)"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: []; issue comments: none; PR search for #47 returns 0 results"},
      {"name": "ai-contribution-allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md contains no mention of AI-generated/AI-assisted contributions"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "single-file doc addition (docs/API.md), 2-3h estimate, no ambiguity in scope"}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]
- Smoke test (`--limit 3`, initial rubric): "agreement: 2/3 scored items" —
  issue-01 disagreed (gold `accept`, rubric `reject`, failed `scope-bounded`).
- Retest after revising `scope-bounded` (`--only issue-01`): "agreement: 1/1
  scored items."
- Full confirming run (`--save-run eval-run.txt`): "agreement: 18/20 scored
  items  (bar: 18/20: PASS)" — categories: claimed 4/4, clear-accept 7/8,
  dead-repo 3/3, policy 1/1, scope 3/4.

**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]

issue-09 (source: conda/conda#7617). Gold label: `accept`. My rubric's
verdict: `reject`, failed on `unclaimed`. The eval table records this as:
"issue-09  accept  reject   NO     failed: unclaimed"

My rubric's `unclaimed` check fails on any comment thread claim a
maintainer "acknowledged or didn't push back on," with no time bound. The
bundle shows a claim from 2022-01-20 ("I'd like to take this as my first
open-source contribution") that jakirkham (a maintainer) acknowledged the
same day. But the thread continues past that: a stale-bot notice in 2023
("automatically marked as stale because it has not had recent activity"),
followed by jakirkham's own one-word comment, "(bump)" — the maintainer
re-soliciting help because the original claimant never followed through.
My check has no way to read that sequence as abandonment; it only checks
whether a claim was ever acknowledged, so a four-year-dead claim still
fails the issue.

**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]

The `unclaimed` check, as currently written in `tools/issue-select/rubric.md`:
"Fails if any of: (a) assignees is non-empty; (b) any linked PR is open;
(c) the comment thread contains a claim ("I'll take this" / "working on
this" / "can I work on this") that a maintainer acknowledged or didn't
push back on. A closed, unmerged linked PR counts as an abandoned attempt,
not a current claim. Where the assignees/linked-PR fields and the thread
disagree, the thread wins"

I wrote condition (c) to require maintainer acknowledgment — not just any
commenter's claim — because an unanswered "I'll take this" from a random
account is weak evidence of a real claim, while a maintainer replying
means the issue is genuinely spoken for. I also wrote the tiebreaker
("the thread wins") directly into the check because the evidence guide
states this explicitly: "when the sidebar and the thread disagree, believe
the thread."

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

This is a case I accept the check will miss: issue-09. The check's
condition (c) has no expiration or abandonment clause, so it treats a
claim acknowledged in 2022 the same as one acknowledged last week — even
though the same thread shows a stale-bot flag and the maintainer's own
"(bump)" comment, both of which are direct evidence the original claim was
abandoned. I considered adding a fixed day-count threshold instead, but
rejected it: an arbitrary cutoff (say, 180 days) would be just as wrong in
the opposite direction, wrongly rejecting a genuinely slow-moving but
still-active claim. The check currently has no way to distinguish "old" from
"abandoned," and I chose not to revise it before this submission, so
issue-09 remains a known miss.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
3. The anticipated difficulty in claiming it.]

i. Fit to interests and time: #56 is a single-function bug in a document
   chunker, with a runnable reproduction snippet and a pre-existing failing
   test (`test_document_with_no_headings`) already pinning the expected
   fix — no exploratory scoping needed before I can start. I have roughly
   4-6 hours available for this, which comfortably fits an issue this
   tightly bounded.

ii. What the verdict identified correctly, and what I weighed beyond it: the
   skill correctly established the check-level facts — repo is active
   (commits 6 days before capture), not archived, unclaimed (no assignees,
   comments, or linked PRs), scope bounded to one function. What it
   couldn't weigh: its own ranking was admittedly generic, since
   `scope.md`'s fit-profile section is still an unfilled placeholder — so
   the "best fit for me personally" judgment is mine, not the skill's. I
   also weighed that #68 (equally well-scoped) already had a classmate
   express intent to work it; even though the house rule says student
   claims don't block, I'd rather not duplicate someone else's work if I
   can pick an equally good, uncontested issue instead.

iii. Anticipated difficulty in claiming: low on the process side — no
   assignees, no linked PRs, and the repo's CONTRIBUTING.md is silent on
   AI-assisted contributions (no disclosure requirement to navigate). I'm
   going in cold on the actual code, though, so the real difficulty will
   show up once I open the chunker source behind the failing test — the
   issue description and the pinned test tell me what's expected, not yet
   how the current code fails to produce it.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
