# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Repo facts: "last 5 default-branch commits" (author + date) and "maintainer first-response sample" (responder's author_association) | Passes if at least one of the last 5 default-branch commits was authored by a human (not a `[bot]` account, unless it merged a human's PR) within 90 days of the bundle's capture date, OR the maintainer first-response sample shows a reply from someone with Owner/Member/Collaborator association within 30 days of the issue opening | required |
| repo-in-use | Repo facts: "archived:" flag, "last push to any branch" date, "latest release" date | Fails immediately if `archived: true` — that's a hard, unconditional dead end regardless of anything else. Otherwise passes if last push to any branch is within 180 days of the bundle's capture date, OR the latest release is within 365 days | required |
| unclaimed | Repo facts: "this issue: assignees:" and "linked PRs:" with state per PR; issue Comments section | Fails if any of: (a) assignees is non-empty; (b) any linked PR is open; (c) the comment thread contains a claim ("I'll take this" / "working on this" / "can I work on this") that a maintainer acknowledged or didn't push back on. A closed, unmerged linked PR counts as an abandoned attempt, not a current claim, and does not fail this check on its own. Where the assignees/linked-PR fields and the comment thread disagree, the thread wins, per the evidence guide | required |
| ai-contribution-allowed | Repo facts: "contribution policy" line (drawn from `CONTRIBUTING.md`, `.github/`, or dedicated files like `AI_POLICY.md`/`AI_USAGE_POLICY.md`; also PR/issue template AI-disclosure checkboxes) | Fails only if the policy contains an explicit, outright ban on AI-generated or AI-assisted contributions. Passes if the policy instead states conditions to follow (disclosure, personal understanding and testing, human review), if it says nothing about AI at all, or if an `AGENTS.md` file is present | required |
| scope-bounded | Issue body and full comment thread | Fails if any of: (a) the issue explicitly states it is a tracking/meta issue meant to be split into separate issues, or bundles multiple genuinely unrelated features/bugs under one issue — a single coherent deliverable that touches several files (e.g. one new doc page plus small updates to related existing pages, or one feature spanning a few modules) is NOT unscoped merely for listing its parts; (b) an active design debate in the thread with no maintainer decision recorded; (c) a maintainer states the fix requires changes to core/internal systems; (d) the issue is a pure "how do I use this" support question with no bug or feature described; (e) the issue's history shows multiple closed, unmerged PR attempts. Passes otherwise | required |


## Verdict rule
Accept if maintainer-alive, repo-in-use, scope-bounded, unclaimed, and
ai-contribution-allowed all pass. Reject if any one of them fails.
A check graded `unclear` counts as a fail for that check, not as a pass —
so an issue with unclear evidence on any required check is rejected,
not accepted by default.
