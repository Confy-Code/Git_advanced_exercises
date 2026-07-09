# Git_advanced_exercises
---

#### PART 1REFINING GIT HISTORY
---
**1. Missing file fix**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git commit --amend "Create third file"
error: pathspec 'Create third file' did not match any file(s) known to git

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git commit --amend -m "Create third file"
[main 206d258] Create third file
 Date: Thu Jul 2 14:34:34 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit 206d2582095ad54895628d0f3d05cf1aa2da9c13 (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third file

commit 867b467f8b7e06c9c3781cf536834c343b1bc89d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:04 2026 +0200

    chore: Create another file

commit be61e6d13a91220e6e7964b17a8fc5c11bdf2ade
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:33:39 2026 +0200

    chore: Create initial file

commit ed054ee8a40806ced09a75fa2c0ed85acf3e962b (origin/main, origin/HEAD)
Author: Confiance <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:27:35 2026 +0200

    Initial commit

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git add test4.md && git commit -m "Create fourth file"
[main d1e6206] Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit d1e6206178338f6ced6c1edd25e2762385b5cb14 (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:38:48 2026 +0200

    Create fourth file

commit 206d2582095ad54895628d0f3d05cf1aa2da9c13
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third file

commit 867b467f8b7e06c9c3781cf536834c343b1bc89d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:04 2026 +0200

    chore: Create another file

commit be61e6d13a91220e6e7964b17a8fc5c11bdf2ade
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:33:39 2026 +0200

    chore: Create initial file
:
```
**2. Editing commit history**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git rebase -i HEAD~3
[detached HEAD cf9f513] chore: Create second file
 Date: Thu Jul 2 14:34:04 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit c7d941e551027548e67b1cc7249700c4ed7de984 (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:38:48 2026 +0200

    Create fourth file

commit 6e83e68649c35b22893354350d23120e1e3baebc
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third file

commit cf9f513e6f188b72a33f80b6b6e980ce3377812f
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:04 2026 +0200

    chore: Create second file

commit be61e6d13a91220e6e7964b17a8fc5c11bdf2ade
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:33:39 2026 +0200

    chore: Create initial file

commit ed054ee8a40806ced09a75fa2c0ed85acf3e962b (origin/main, origin/HEAD)
Author: Confiance <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:27:35 2026 +0200

    Initial commit
```

**3. Keeping History tidy**
```bash
pick be61e6d chore: Create initial file
chore: Create initial and second files.























[detached HEAD 57a7b9d] chore: Create initial and second files.
 Date: Thu Jul 2 14:33:39 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit 899edbd2feabb4ca11a55199c48296f2f5fbe272 (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:38:48 2026 +0200

    Create fourth file

commit 3e8f6eed343833e728f0b4422ed79222342cc7ca
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third file

commit 57a7b9d83d903f08bbc71a7a3172f1ca1c446f5d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:33:39 2026 +0200

    chore: Create initial and second files.

commit ed054ee8a40806ced09a75fa2c0ed85acf3e962b (origin/main, origin/HEAD)
Author: Confiance <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:27:35 2026 +0200

    Initial commit
:
```
---


**4. Splitting commits**
```bash
Stopped at 57a7b9d...  chore: Create initial and second files.
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main|REBASE 1/3)
$ git reset HEAD^

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main|REBASE 1/3)
$ git add test1.md && git commit -m "chore: Create initial file"
[detached HEAD e04d4b1] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main|REBASE 1/3)
$ git add test2.md && git commit -m "chore: Create second file"
[detached HEAD 943e2ef] chore: Create second file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main|REBASE 1/3)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit 47d0228d1aa47cdc905dad31f71ec719cd2f0d60 (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:38:48 2026 +0200

    Create fourth file

commit 58ad63774537757dda68ba0c5a1653ea64fe4dcd
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third file

commit 943e2ef3ae18bdaf4aae4c6d8135bfa1c9b68d5d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:24 2026 +0200

    chore: Create second file

commit e04d4b114d0ce640ed5b4a42623047b543bba648
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:15 2026 +0200

    chore: Create initial file
:
```
---

**5. Advanced Squashing**
```bash
[detached HEAD 553422a] Create third and fourth files.
 Date: Thu Jul 2 14:34:34 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit 553422a489c4563475200f100a6f4a5f3bdc56ae (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third and fourth files.

commit 943e2ef3ae18bdaf4aae4c6d8135bfa1c9b68d5d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:24 2026 +0200

    chore: Create second file

commit e04d4b114d0ce640ed5b4a42623047b543bba648
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:15 2026 +0200

    chore: Create initial file

commit ed054ee8a40806ced09a75fa2c0ed85acf3e962b (origin/main, origin/HEAD)
Author: Confiance <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:27:35 2026 +0200

    Initial commit
:
```
---

**6. Dropping a commit**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ touch unwanted.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git add unwanted.txt && git commit -m "Unwanted commit"
[main d083100] Unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git rebase -i HEAD~3

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit 553422a489c4563475200f100a6f4a5f3bdc56ae (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third and fourth files.

commit 943e2ef3ae18bdaf4aae4c6d8135bfa1c9b68d5d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:24 2026 +0200

    chore: Create second file

commit e04d4b114d0ce640ed5b4a42623047b543bba648
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:15 2026 +0200

    chore: Create initial file

commit ed054ee8a40806ced09a75fa2c0ed85acf3e962b (origin/main, origin/HEAD)
Author: Confiance <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:27:35 2026 +0200

    Initial commit
:
```

**7. Re-ordering the commits**
> This was done by simply swapping the commit lines inside the vim file.
---

**8. Cherry-picking commits**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ touch test5.d

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ git rm test5.d
fatal: pathspec 'test5.d' did not match any files

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ ls
README.md  test1.md  test2.md  test3.md  test4.md  test5.d

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ git rm test5.d
fatal: pathspec 'test5.d' did not match any files

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ rm test5.d

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ ls
README.md  test1.md  test2.md  test3.md  test4.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ touch test5.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ git add test5.md && git commit -m "Implemented test 5"
[ft/branch ae16ecd] Implemented test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ git log --oneline
ae16ecd (HEAD -> ft/branch) Implemented test 5
553422a (main) Create third and fourth files.
943e2ef chore: Create second file
e04d4b1 chore: Create initial file
ed054ee (origin/main, origin/HEAD) Initial commit

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (ft/branch)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git cherry-pick ae16ecd
[main 44b4941] Implemented test 5
 Date: Thu Jul 2 23:18:33 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git log
commit 44b494189e89624add23f6192007e6d06a7f316f (HEAD -> main)
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 23:18:33 2026 +0200

    Implemented test 5

commit 553422a489c4563475200f100a6f4a5f3bdc56ae
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 14:34:34 2026 +0200

    Create third and fourth files.

commit 943e2ef3ae18bdaf4aae4c6d8135bfa1c9b68d5d
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:24 2026 +0200

    chore: Create second file

commit e04d4b114d0ce640ed5b4a42623047b543bba648
Author: Confy-Code <isingizweconfy@gmail.com>
Date:   Thu Jul 2 22:56:15 2026 +0200

    chore: Create initial file
:

```
---

**Bonus: Git reflog**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git_advanced_exercises (main)
$ git reflog
44b4941 (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
553422a HEAD@{1}: checkout: moving from ft/branch to main
ae16ecd (ft/branch) HEAD@{2}: commit: Implemented test 5
553422a HEAD@{3}: checkout: moving from main to ft/branch
553422a HEAD@{4}: rebase (finish): returning to refs/heads/main
553422a HEAD@{5}: rebase (start): checkout HEAD~3
d083100 HEAD@{6}: commit: Unwanted commit
553422a HEAD@{7}: rebase (finish): returning to refs/heads/main
553422a HEAD@{8}: rebase (squash): Create third and fourth files.
58ad637 HEAD@{9}: rebase (start): checkout HEAD~3
47d0228 HEAD@{10}: rebase (finish): returning to refs/heads/main
47d0228 HEAD@{11}: rebase (pick): Create fourth file
58ad637 HEAD@{12}: rebase (pick): Create third file
943e2ef HEAD@{13}: commit: chore: Create second file
e04d4b1 HEAD@{14}: commit: chore: Create initial file
ed054ee (origin/main, origin/HEAD) HEAD@{15}: reset: moving to HEAD^
57a7b9d HEAD@{16}: rebase: fast-forward
ed054ee (origin/main, origin/HEAD) HEAD@{17}: rebase (start): checkout HEAD~3
899edbd HEAD@{18}: rebase (finish): returning to refs/heads/main
899edbd HEAD@{19}: rebase: fast-forward
3e8f6ee HEAD@{20}: rebase: fast-forward
57a7b9d HEAD@{21}: rebase: fast-forward
ed054ee (origin/main, origin/HEAD) HEAD@{22}: rebase (start): checkout HEAD~3
:
```
---

**PART2 : BRANCHING BASICS**
1. Feature Branch Creation
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e
$ cd Git-exercise/

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
```
---

2. Working on the Feature Branch

```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ touch feature.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ ls
README.md  feature.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ nano filename.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ ls
README.md  feature.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ nano feature.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ nano feature.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ git add feature.txt
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the n
ext time Git touches it

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ git commit -m "Implemented core functionality for new feature"
[ft/new-feature fd64098] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```
---

3.  Switching branches

```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ touch readme.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ nano readme.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git commit -m "Updated project readme"
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        readme.txt

nothing added to commit but untracked files present (use "git add" to track)

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git add readme.txt
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the ne
xt time Git touches it

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git commit -m "Updated project readme"
[main 3e92123] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```
---

5. Branch deletion

```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch -d ft/new-feature
error: the branch 'ft/new-feature' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D ft/new-feature'
hint: Disable this message with "git config advice.forceDeleteBranch false"

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ ls
README.md  readme.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git checkout ft/new-feature
Switched to branch 'ft/new-feature'

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ git branch -d ft/new-feature
error: cannot delete branch 'ft/new-feature' used by worktree at 'E:/Git-exercis
e'

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch -d ft/new-feature
error: the branch 'ft/new-feature' is not fully merged
hint: If you are sure you want to delete it, run 'git branch -D ft/new-feature'
hint: Disable this message with "git config advice.forceDeleteBranch false"

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ ^C

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch -D ft/new-feature
Deleted branch ft/new-feature (was fd64098).
```
---

6. Creating a branch from a commit
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git log --oneline
3e92123 (HEAD -> main) Updated project readme
e4744a0 (origin/main, origin/HEAD) Update README.md
3083f66 Update README
826eba3 Update README
86ec50c refactor: update README
be0f35c Update README.md
6483bd6 Update README.md
9dbca11 Update README.md
7cd7a29 Merge pull request #1 from HIRWA13/chore/refine-exercises
bf8e72c Update README.md
e632651 refactor: clean and update exercise structure
aabb257 refactor: create branch from a commit
4f71b9f refactor: update exercises
6448eeb refactor: update readme file
013976b refactor: update exercises
23ea742 refactor: update and remove mistakes
248fb71 refactor: Update Exercises
6e0e33f refactor: Update README.md
82125a9 refactor: Update README.md
2ceafa5 refactor: update README
ea7834e chore: add part one exercises

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git checkout -b ft/new-branch-from-commit 308f66
fatal: '308f66' is not a commit and a branch 'ft/new-branch-from-commit' cannot
be created from it

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git checkout -b ft/new-branch-from-commit 3083f66
Switched to a new branch 'ft/new-branch-from-commit'
```
---

7. Branch merging
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git merge ft/new-branch-from-commit
Already up to date.

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch --list
  ft/new-branch-from-commit
* main

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch --merged
  ft/new-branch-from-commit
* main

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch --no-merged
```
---

8. .....
9. Renaming branches
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch -m ft/new-branch-from-commit ft/improved-branc-name

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch --list
  ft/improved-branc-name
* main

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch -m ft/improved-branc-name ft/improved-branch-name

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git branch --list
  ft/improved-branch-name
* main
```
---

10. Checking out detached HEAD
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git checkout 3083f66
Note: switching to '3083f66'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 3083f66 Update README

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise ((3083f66...))
```
---

### PART 3: ADVANCED WORKFLOWS

**1. Stashing changes**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git stash list

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git stash save "Saved my current changes to main"
No local changes to save

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ ls
README.md  readme.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ nano readme.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git stash save "Stached the unsaved changes in readme.txt"
Saved working directory and index state On main: Stached the unsaved changes in
readme.txt

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git stash list
stash@{0}: On main: Stached the unsaved changes in readme.txt
```
---

**2. Retrieving the stashed changes**
> You can use `git stash apply` to keep a copy of the changes into the stash drawer, or you can use `git stash pop` 
if you want nothing in the stash drawer.
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git stash pop
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (461b842d94e0e6b4bb3af9c77bd47e88e7b764a9)

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git stash list

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$
```
---

**3. Branch Merging conflicts (continued)**
**4.**
**5. Understanding the DETACHED HEAD state**
```bash
newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise ((3083f66...))
$ git log --oneline
3083f66 (HEAD, ft/improved-branch-name) Update README
826eba3 Update README
86ec50c refactor: update README
be0f35c Update README.md
6483bd6 Update README.md
9dbca11 Update README.md
7cd7a29 Merge pull request #1 from HIRWA13/chore/refine-exercises
bf8e72c Update README.md
e632651 refactor: clean and update exercise structure
aabb257 refactor: create branch from a commit
4f71b9f refactor: update exercises
6448eeb refactor: update readme file
013976b refactor: update exercises
23ea742 refactor: update and remove mistakes
248fb71 refactor: Update Exercises
6e0e33f refactor: Update README.md
82125a9 refactor: Update README.md
2ceafa5 refactor: update README
ea7834e chore: add part one exercises

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise ((3083f66...))
$ git reset

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise ((3083f66...))
$ git checkout main
Previous HEAD position was 3083f66 Update README
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

newuser123@DESKTOP-CRGBPJ0 MINGW64 /e/Git-exercise (main)
$ git log --oneline
3e92123 (HEAD -> main) Updated project readme
e4744a0 (origin/main, origin/HEAD) Update README.md
3083f66 (ft/improved-branch-name) Update README
826eba3 Update README
86ec50c refactor: update README
be0f35c Update README.md
6483bd6 Update README.md
9dbca11 Update README.md
7cd7a29 Merge pull request #1 from HIRWA13/chore/refine-exercises
bf8e72c Update README.md
e632651 refactor: clean and update exercise structure
aabb257 refactor: create branch from a commit
4f71b9f refactor: update exercises
6448eeb refactor: update readme file
013976b refactor: update exercises
23ea742 refactor: update and remove mistakes
248fb71 refactor: Update Exercises
6e0e33f refactor: Update README.md
82125a9 refactor: Update README.md
2ceafa5 refactor: update README
ea7834e chore: add part one exercises
```
---

**6. Ignoring files/ directories**














