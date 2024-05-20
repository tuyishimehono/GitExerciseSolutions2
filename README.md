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


