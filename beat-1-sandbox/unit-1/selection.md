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

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61

**Verdict output**


**Mode:** live. **Scope:** `scope.md` names `codepath/pathreview-ai301-fa26-s1`; issue #61 is in that repo, so it is in scope. No fit profile is filled in and there is only one candidate, so no ranking applies. Recency thresholds measured against today, 2026-09-19.

| Check | Grade | Evidence |
|---|---|---|
| Maintainer alive | pass | Aburke225 (COLLABORATOR) pushed to `main` 2026-09-16 (3 days ago) and opened/labeled #61 on 2026-09-10 — well inside 90 days. |
| Repository active | pass | Last `main` commit 2026-09-16 (3 days), `archived: false`. No releases exist, but the commit clause alone satisfies the condition. |
| Scope fits newcomer | pass | Body names `api/routes/health.py`, and I confirmed the line in the live file: `await db.execute("SELECT 1")`. It gives reproduction steps and the exact expected error. |
| Issue unclaimed | pass | `assignees: []`, `comments: 0`, timeline holds only four `labeled` events, and the repo has zero pull requests of any state. |
| Contribution permitted | pass | `docs/CONTRIBUTING.md` documents a fork-and-PR flow for outside contributors; no AI ban, no `AI_POLICY.md`, and the PR template requires no AI disclosure. |

Verdict: **accept** — every required check passes.

Two things worth knowing before you start, neither of which the rubric grades:

- There is no `tests/unit/test_health.py`, so unlike many seeded bugs here there is no `@pytest.mark.xfail` marker waiting for you to delete. `CONTRIBUTING.md` asks that every code change carry a test, so writing that file is part of the work.
- `CONTRIBUTING.md` notes that `api/routes/health.py`'s `attr-defined` mypy suppression in `pyproject.toml` is issue **#62**, a separate bug in the same file. Keep your diff on the `text()` wrapping and leave #62's suppression alone.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/61",
  "checks": [
    {"name": "Maintainer alive", "grade": "pass",
     "evidence": "Collaborator Aburke225 pushed to main on 2026-09-16 and labeled this issue on 2026-09-10, both within 90 days of 2026-09-19."},
    {"name": "Repository active", "grade": "pass",
     "evidence": "Latest default-branch commit 2026-09-16, 3 days before today; repo not archived (no releases exist, but the 180-day commit clause is met)."},
    {"name": "Scope fits newcomer", "grade": "pass",
     "evidence": "Body names target file api/routes/health.py plus reproduction; live file confirms the defect line `await db.execute(\"SELECT 1\")`."},
    {"name": "Issue unclaimed", "grade": "pass",
     "evidence": "assignees: [], comments: 0, timeline has only 4 'labeled' events, and the repo has zero pull requests in any state."},
    {"name": "Contribution permitted", "grade": "pass",
     "evidence": "docs/CONTRIBUTING.md documents a fork-and-PR flow for contributors; no AI policy file, ban, or disclosure checkbox anywhere in the repo."}
  ],
  "verdict": "accept"
}


---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.
categories: claimed 4/4  clear-accept 7/8  dead-repo 3/3  policy 1/1  scope 3/4
agreement: 18/20 scored items  (bar: 18/20: PASS)

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

**Issue analysis**

For `issue-15`, my final rubric returned `reject`, matching the gold label of `reject`. The deciding evidence was the comment `@zulipbot claim`. The provided comment thread did not show a later withdrawal or unassignment for that claim. Therefore, the issue failed my required Issue unclaimed check even though the repo-facts block listed no current assignee and only closed linked pull requests.


**Check rationale**

| Issue unclaimed | Repo-facts block: assignees and linked PRs; comment thread shown in the bundle | Pass only if there is no assignee, no open linked pull request, and every claim in the comments has been explicitly withdrawn, unassigned, or released by a later comment. Treat `@zulipbot claim`, "can I work on this?", "I started working on this", "I plan to work on this", and "my PR is pending" as claims. If the visible comments end with an unresolved claim, fail this check even when the repo-facts block currently says `assignees: none`. | required |


**Trade-offs**

This strict claim check can reject an issue when an old claim appears in a truncated comment thread but its later release is not visible. It can also miss claim signals outside the three sources named in the check. During live mode, issues #62 and #72 had references from other students’ course-repository commits, but my rubric still accepted them because those references were not assignees, open linked pull requests, or comment claims. I avoided that risk by selecting issue #61, which had no such contention signal.
---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. This issue fits my interest in backend development because it involves an API health endpoint, database access, SQLAlchemy, and testing. Although it uses Python/FastAPI rather than Spring Boot, the database and health-check concepts transfer to Java backend development. Its limited scope—one defect in one route plus a test—also fits the time available.

2. The verdict correctly identified that the repository is active, the maintainer is active, the defect has clear reproduction steps, outside contributions are permitted, and nobody appears to be working on the issue. My rubric could not weigh my preference for backend work or the fact that I will need to create a new health-check test rather than update an existing test.

3. I expect claiming it to be straightforward because issue #61 has no assignee, comments, pull requests, or other visible selection signal. However, this is a shared course repository, so I will check its current status again immediately before posting the claim comment in Unit 2.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
