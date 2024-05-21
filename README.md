# GitExercise
# Challenges
## Part 1

### 1. Missing File fix
``` bash

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise
$ git init
$ git add README.md
$ git commit -m "initial commit"
$ git remote add origin git@github.com:tuyishimehono/Git_Exercise.git
$ git push -u origin main
$ touch test{1..4}.md
$                    
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
$ git status
$ git log
$ git add test4.md
$ git commit --amend

```
### 2. Editing Commit history
```bash

$ git log
$ git rebase -i HEAD~2
$ git commit --amend
$ git rebase --continue
Successfully rebased and updated refs/heads/main.
```

### 3. Keeping History Tidy - Squashing Commits
```bash
$ git rebase -i HEAD~3
$ git log

```

### 4. Splitting a Commit
```bash
$ git status
$ git reset HEAD~
$ git add test3.md && git commit -m "Create third file"
$ git add test4.md && git commit -m "Create fourth file"

```
### 5. Advanced Squashing
```bash

$ git rebase -i HEAD~3
$ git log
```

### 6. Dropping a Commit
```bash
$ git add unwanted.txt && git commit -m "Unwanted commit"
$ git rebase -i
Successfully rebased and updated refs/heads/main.
```
### 7. Reordering Commits
``` bash
$ git rebase -i HEAD~2
$ git log
```

### 8. Cherry-Picking Commits
```bash

$ git add test5.md
$ git commit -m "Implemented Test 5"
$ git log
$ git checkout main
$ git cherry-pick 674c9c13550eb916a43ce12cfbe200daf267f6fe

```
### 9. Visualizing Commit History (Bonus)
```bash
git log --graph
```

### 10. Understanding Reflogs (Bonus)
```bash
git reflog
```

## Part 2

### 1. Feature branch creation
```bash
$ git checkout -b ft/new-feature
```
### 2. Working on the Feature Branch
```bash
$ touch feature.txt
$ git add feature.txt && git commit -m "Implemented core functionality for new feature"
```
### 3. Switching Back and Making More Changes
```bash
$ git checkout main
$ touch readme.txt
$ git add readme.txt && git commit -m "Updated project readme"
```
### 4. Local vs. Remote Branches
```bash
$ git checkout main
$ git merge ft/new-feature
$ git push origin main
```
### 5. Branch Deletion
```bash
$ git branch -d ft/new-feature
```

### 6. Creating a Branch from a Commit
```bash
$ git log -1 --pretty=format:%H HEAD~2
f3e3fabd4520e37a623aedae2a2d06f9544345ef

$ git checkout -b ft/new-branch-from-commit f3e3fabd4520e37a623aedae2a2d06f9544345ef
Switched to a new branch 'ft/new-branch-from-commit'

```
### 7. Branch Merging
```bash
$ git checkout main
$ git merge ft/new-branch-from-commit
Already up to date.
```

### 8. Branch rebasing
```bash
$ git checkout ft/new-branch-from-commit
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
```
### 9. Renaming Branches
```bash
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name
~/OneDrive/Desktop/Gitexercise (ft/improved-branch-name)
```
## Part 3

### 1. Stashing Changes
```bash
$ git stash
Saved working directory and index state WIP on main: bd921fa Merge branch 'ft/new-feature'
```

### 2. Retrieving Stashed Changes
```bash
$ git stash list
$ git stash pop

```

### 3. Branch Merging Conflicts (Continued)
```bash
$ git add readme.txt && git commit -m "Main branch commit"
[main 754ab1a] Main branch commit
 1 file changed, 1 insertion(+), 1 deletion(-)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (ft/improved-branch-name)
$ git add readme.txt && git commit -m "feature branch commit"
[ft/improved-branch-name a3dac37] feature branch commit
 1 file changed, 2 insertions(+), 1 deletion(-)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (ft/improved-branch-name)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git merge ft/improved-branch-name
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git merge ft/improved-branch-name
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git add readme.txt

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git merge ft/improved-branch-name
fatal: You have not concluded your merge (MERGE_HEAD exists).
Please, commit your changes before you merge.

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git commit -m "conflict resolved"
[main e775c31] conflict resolved

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git merge ft/improved-branch-name
Already up to date.
```

### 4. Resolving Merge Conflicts with a Merge Tool
```bash
$ git add readme.txt && git commit -m "Updated readme.txt"
[main 1a09983] Updated readme.txt
 1 file changed, 1 insertion(+), 1 deletion(-)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (ft/improved-branch-name)
$ git add readme.txt && git commit -m "Updated readme in feature"
[ft/improved-branch-name 4caa310] Updated readme in feature
 1 file changed, 1 insertion(+), 1 deletion(-)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (ft/improved-branch-name)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
No files need merging

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
Introductory content
$ git merge ft/improved-branch-name
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc codecompare smerge emerge vimdiff nvimdiff
Merging:
readme.txt

Normal merge conflict for 'readme.txt':
  {local}: modified file
  {remote}: modified file
Hit return to start merge resolution tool (vimdiff):
4 files to edit

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git add readme.txt

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main|MERGING)
$ git commit -m "Resolved conflict"
[main 07f8a82] Resolved conflict

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git merge ft/improved-branch-name
Already up to date.
