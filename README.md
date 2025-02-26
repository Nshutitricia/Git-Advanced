# Git Exercises

## Part 1 Refining Git History

### Ex1 Missing File fix
```bash
gymumuco@umucos-iMac-2 Git-Advanced-Draft % git status && git log
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
commit 2604602c96316d1216a70bebf8b7b216b4ae2e69 (HEAD -> main)
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create third and fourth files

commit 895f12290246e840530481acf1be215a6bc382c5
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create another file

commit 3520fdf6499c8ccae245ec955a03f315312452c6
:...skipping...
commit 2604602c96316d1216a70bebf8b7b216b4ae2e69 (HEAD -> main)
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create third and fourth files

commit 895f12290246e840530481acf1be215a6bc382c5
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create another file

commit 3520fdf6499c8ccae245ec955a03f315312452c6
Author: Nshutitricia <nshutricia@gmail.com>
:...skipping...
commit 2604602c96316d1216a70bebf8b7b216b4ae2e69 (HEAD -> main)
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create third and fourth files

commit 895f12290246e840530481acf1be215a6bc382c5
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create another file

commit 3520fdf6499c8ccae245ec955a03f315312452c6
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200
:...skipping...
commit 2604602c96316d1216a70bebf8b7b216b4ae2e69 (HEAD -> main)
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create third and fourth files

commit 895f12290246e840530481acf1be215a6bc382c5
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create another file

commit 3520fdf6499c8ccae245ec955a03f315312452c6
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

:...skipping...
commit 2604602c96316d1216a70bebf8b7b216b4ae2e69 (HEAD -> main)
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create third and fourth files

commit 895f12290246e840530481acf1be215a6bc382c5
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create another file

commit 3520fdf6499c8ccae245ec955a03f315312452c6
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create initial file
:...skipping...
commit 2604602c96316d1216a70bebf8b7b216b4ae2e69 (HEAD -> main)
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create third and fourth files

commit 895f12290246e840530481acf1be215a6bc382c5
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create another file

commit 3520fdf6499c8ccae245ec955a03f315312452c6
Author: Nshutitricia <nshutricia@gmail.com>
Date:   Wed Feb 26 13:10:45 2025 +0200

    chore: Create initial file
~
```

#### Commit
```bash
 gymumuco@umucos-iMac-2 Git-Advanced-Draft % git add test4.md && git commit -m "chore: Create fourth file"
[main c74d7cf] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

```
### Ex2 Edit commit History
```bash
gymumuco@umucos-iMac-2 Git-Advanced-Draft % rm -fr ".git/rebase-merge"
gymumuco@umucos-iMac-2 Git-Advanced-Draft % git rebase -i HEAD~3      
[detached HEAD f71bba0] chore: Create second file
 Date: Wed Feb 26 13:10:45 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
```

### Ex3 Keeping History Tidy - Squashing Commits
```bash
gymumuco@umucos-iMac-2 Git-Advanced-Draft % git rebase -i HEAD~3
[detached HEAD 0a7a6fd] This is the squash file
 Date: Wed Feb 26 13:10:45 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
 create mode 100644 test3.md
Successfully rebased and updated refs/heads/main.
gymumuco@umucos-iMac-2 Git-Advanced-Draft % git log --oneline
74f7954 (HEAD -> main) chore: Create fourth file
0a7a6fd This is the squash file
3520fdf chore: Create initial file
```