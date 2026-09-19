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
| Maintainer alive | Repo-facts block: maintainer-response sample and recent maintainer activity; comment thread | Pass if the evidence shows at least one maintainer response or other maintainer activity within 90 days of the bundle snapshot date. | required |
| Repository active | Repo-facts block: last 5 default-branch commit dates and latest release date | Pass if the repository has at least one default-branch commit within 180 days or a release within 365 days of the bundle snapshot date. | required |
| Scope fits newcomer | Issue body and comment thread | Pass if the issue defines a concrete requested change and provides at least one target file, target component, reproduction, or acceptance criterion. Fail only if there is no concrete deliverable or the discussion explicitly says work must not begin until a major decision is made. Optional suggestions, future improvements, and unresolved non-blocking details do not cause failure. | required |
| Issue unclaimed | Repo-facts block: assignees and linked PRs; comment thread shown in the bundle | Pass only if there is no assignee, no open linked pull request, and every claim in the comments has been explicitly withdrawn, unassigned, or released by a later comment. Treat `@zulipbot claim`, "can I work on this?", "I started working on this", "I plan to work on this", and "my PR is pending" as claims. If the visible comments end with an unresolved claim, fail this check even when the repo-facts block currently says `assignees: none`. | required |
| Contribution permitted | Repo-facts block: stated contribution policy; issue body and comment thread for maintainer approval | Pass if the policy allows outside contributors to work on the issue, or any required maintainer approval is explicitly present. | required |

## Verdict rule

Accept only when every required check passes. Reject when any required check fails. Treat unclear or insufficient evidence as a failure for required checks. Preferred checks, if added later, may rank accepted issues but never change the final verdict.
<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
