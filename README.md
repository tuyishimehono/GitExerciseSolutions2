# GitExercise
# Challenges
## Part 1

### Missing File fix
``` bash

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise
$ git init
Initialized empty Git repository in C:/Users/honor/OneDrive/Desktop/Gitexercise/.git/

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git add README.md

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git commit -m "initial commit"
[main (root-commit) afe711f] initial commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git remote add origin git@github.com:tuyishimehono/Git_Exercise.git

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 214 bytes | 214.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:tuyishimehono/Git_Exercise.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ touch test{1..4}.md

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$                    
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main 8e857b0] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[main 1ab7318] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main 5cd75f2] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git log
commit 5cd75f28e0321a8649444c004cf8f438e2554767 (HEAD -> main)
Author: tuyishimehono <tuhonori1@gmail.com>
Date:   Mon May 20 14:28:22 2024 +0200

    chore: Create third and fourth files

commit 1ab7318bd1e8d327cf1f02d74071aa423a8882e9
Author: tuyishimehono <tuhonori1@gmail.com>
Date:   Mon May 20 14:28:22 2024 +0200

    chore: Create another file

commit 8e857b0afc6188f2ddd1a09c829af1ea722ae439
Author: tuyishimehono <tuhonori1@gmail.com>
Date:   Mon May 20 14:28:21 2024 +0200

    chore: Create initial file

commit afe711f1c92cbf8d0f14c57afc60675ef6d3ad98 (origin/main)
Author: tuyishimehono <tuhonori1@gmail.com>
Date:   Mon May 20 14:16:30 2024 +0200

    initial commit

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git add test4.md

Honorine@Tuyishime-PC MINGW64 ~/OneDrive/Desktop/Gitexercise (main)
$ git commit --amend
[main 76fba28] chore:Create initial file chore: Create another file chore: Create third file chore: Create fourth file
 Date: Mon May 20 14:28:22 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
```
### Editing Commit history
