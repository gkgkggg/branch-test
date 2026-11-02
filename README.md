# Lecture 9: Remote Branch and Collaboration

This repository contains the Lecture 9 Git exercise. Two local working copies
were used to simulate one developer and a teammate working on the same public
GitHub repository. Both roles belong to the same account.

## Completed workflow

1. Pushed the six-commit branching and merging example to this new repository.
2. Cloned the GitHub repository into separate developer and team working copies.
3. Committed `hotfix my solution` locally without pushing it.
4. Pushed `Hotfix team's solution` from the second working copy.
5. Attempted the developer push and received an actual GitHub rejection.
6. Ran `git fetch origin`, then `git merge origin/main`; `edition.txt` conflicted.
7. Resolved the conflict by retaining the team's fix, then committed the merge.
8. Added `New function added` and successfully pushed the result to GitHub.
9. Pushed `Team upgraded` from the second working copy.
10. Ran `git pull --ff-only origin main` and verified synchronization.

The exercise produced 11 commits, including two merge commits. A final
documentation commit adds this explanation, ignore rules, and execution evidence.

## Files

- `edition.txt`: the final content after conflict resolution and synchronization.
- `new_feature.txt`: the feature file from the initial branching exercise.
- `lab9-evidence.txt`: actual command output from the remote collaboration exercise.
- `.gitignore`: exclusions for local configuration, credentials, and temporary files.

## Inspect the result

```bash
git clone https://github.com/gkgkggg/branch-test.git
cd branch-test
git log --oneline --decorate --graph --all
git status --short --branch
```

`git fetch` updates remote-tracking references without merging into the current
branch. `git pull` fetches and integrates changes. This exercise uses `--ff-only`
for the final pull because the local branch has no additional divergent commit.

Commit authors use a GitHub noreply address. No tokens or private configuration
files are included. Authentication is handled by the installed Git credential helper.
