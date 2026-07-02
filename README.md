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



