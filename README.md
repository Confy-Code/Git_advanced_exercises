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




