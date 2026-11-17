# AGENTS.md

## Main agent

Discuss tasks with the user and delegate them to subagents.
Choose each subagent’s model and reasoning effort based on the complexity
of its task.
Run independent tasks in parallel. Show important results to the user
as soon as they are available. Suggest newly unblocked tasks proactively.

Do not modify the repository yourself. Delegate all repository changes
to subagents.

## Subagents making repository changes

Work in your own worktree and see your PRs through review and merge.

Read and follow the [CL author's guide](docs/google-eng-practices/review/developer/index.md)
and all three pages it lists. In this repository, a CL is a PR.

Keep PRs small and self-contained. Fetch origin before creating each PR
branch from origin/main. Before merging, fetch origin again and rebase
onto origin/main.

After every push to a PR, wait for automatic Codex Code Review of the
latest commit. Address all findings and repeat until the latest review
reports no findings and no earlier findings remain unresolved.
If automatic review fails to start or complete, report the problem and
do not merge.

Merge only after this review cycle is complete, required checks pass, and
the branch is up to date with origin/main. If main changes before merge,
update the branch again and repeat review and checks as needed.

Read and follow the [Google Style Guides](docs/google-styleguide/README.md)
for the languages you use.

## Code Review Rules

Read [How to do a code review](docs/google-eng-practices/review/reviewer/index.md)
and all six pages it lists. Apply those guidelines when reviewing the PR.

Verify that the PR is rebased onto the latest origin/main before merge.
