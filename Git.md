# Git

<img src="Git.png" width="100" height="100">

> Git - *"the stupid content tracker"*
>
> — From the official Git documentation

[:arrow_left: Return to Main README](README.md)

---

## Sections

> * [The Workflow](#the-workflow)
>     * [The Basic Cycle](#the-basic-cycle)
> * [Repository](#repository)
>     * [Initialize Repository](#initialize-repository)
>     * [Clone Repository](#clone-repository)
> * [Commits](#commits)
> * [Branches](#branches)
> * [Merge](#merge)
> * [Remote Repositories](#remote-repositories)
> * [Logs & History](#logs--history)
> * [Undoing Changes](#undoing-changes)
>     * [Unstage a File](#unstage-a-file)
>     * [Discard Local Changes](#discard-local-changes)
>     * [Soft Reset](#soft-reset-undo-last-commit-keep-code-changes)
>     * [Hard Reset](#hard-reset-delete-last-commit--destroy-code-changes)
>     * [Revert a Commit](#revert-a-commit)
> * [Stashing](#stashing)

---

### [The Workflow](#sections)

Git tracks **snapshots of a project**.

* **Working Directory**: Where you modify your files.
* **Staging Area**: A preview repository layout of what will go into your next commit.
* **Local Repository**: Where Git permanently saves your project history.
* **Remote Repository**: The shared version of the project hosted on platforms like GitHub or GitLab.

---

#### [The Basic Cycle](#the-workflow)

```txt
Modify
  │
  ▼
Working Directory
  │
  │ git add
  ▼
Staging Area
  │
  │ git commit
  ▼
Local Repository
  │
  │ git push
  ▼
Remote Repository
```

---

### [Repository](#sections)

> * [Intitialize Repository](#initialize-repository)
> * [Clone Repository](#clone-repository)

#### [Initialize Repository](#repository)

***Syntax:***
```bash
git init
```
***Result:***
> Initialized empty Git repository in /path/to/project/.git/

#### [Clone Repository](#repository)

***Syntax:***
```bash
git clone https://github.com/JaehoChoi00/Github-basics.git
```
***Result:***
> Cloning into 'repo'...
> remote: Enumerating objects: 10, done.
> Unpacking objects: 100% (10/10), done.

---

### [Commits](#sections)

***Syntax:***
```bash
git status
git add index.html
git commit -m "feat: add main structural layout"
```

***Result:***
> On branch main
> Changes to be committed:
> (use "git restore --staged <file>..." to unstage)
> new file:   index.html
>
> [main 4a2b1c3] feat: add main structural layout
> 1 file changed, 12 insertions(+)
> create mode 100644 index.html

***Syntax:***
```bash
git status
git add index.html
git commit -m "feat: add main structural layout" -m "Body message"
```

***The message:***
> feat: add main structural layout
>
> Body message

---

### [Branches](#sections)

***Syntax:***
```bash
# List branches
git branch

# Create and switch to branch
git checkout -b feature-login # Old

git switch -c feature-login # New
```

***Result:***
> main
> 
> Switched to a new branch 'feature-login'

---

### [Merge](#sections)

***Syntax:***
```bash
git switch main
git merge feature-login
git branch -d feature-login
```

***Result:***
> Switched to branch 'main'
> Updating 4a2b1c3..7d8e9f0
> Fast-forward
> index.html | 5 +++++
> 1 file changed, 5 insertions(+)
>
> Deleted branch feature-login (was 7d8e9f0).

---

### [Remote Repositories](#sections)

***Syntax:***
```bash
git remote add origin https://github.com
git push -u origin main
git pull
```

***Result:***
> Branch 'main' set up to track remote branch 'main' from 'origin'.
> Everything up-to-date
> 
> Already up to date.

---

## Logs & History

***Syntax:***
```bash
git log
```

***Syntax:***
```bash
git log --oneline --graph --all
```

***Result:***
> * 7d8e9f0 (HEAD -> main, origin/main) feat: add authentication forms
> * 4a2b1c3 feat: add main structural layout
> * 1a2b3c4 Initial commit

---

### [Undoing Changes](#sections)

> * [Unstage a File](#unstage-a-file)
> * [Discard Local Changes](#discard-local-changes)
> * [Soft Reset](#soft-reset-undo-last-commit-keep-code-changes)
> * [Hard Reset](#hard-reset-delete-last-commit--destroy-code-changes)
> * [Revert a Commit](#revert-a-commit)

#### [Unstage a File](#undoing-changes)

***Syntax:***
```bash
git restore --staged config.json

# Older equivalent
git reset --staged config.json
```
***Result:***
> Changes to be committed:
> M config.json


#### [Discard Local Changes](#undoing-changes)

***Syntax:***
```bash
git restore config.json
```
***Result:***
> The uncommitted changes to config.json are discarded.

#### [Soft Reset (Undo Last Commit, Keep Code Changes)](#undoing-changes)

Removes the previous commit entirely but leaves all modified files staged in your workspace.

***Syntax:***
```bash
git reset --soft HEAD~1
```
***Result:***
> (The last commit is erased from history. Changes remain in the staging area.)

<br>

#### [Hard Reset (Delete Last Commit & Destroy Code Changes)](#undoing-changes)
Permanently erases the last commit **AND** throws away any code changes tracking along with it.

> [!WARNING]
> This command completely wipes uncommitted work. It cannot be recovered.

***Syntax:***
```bash
git reset --hard HEAD~1
```
***Result:***
> HEAD is now at 4a2b1c3 feat: add main structural layout

<br>

#### [Revert a Commit](#undoing-changes)

***Syntax:***
```bash
git revert 7d8e9f0
```
***Result:***
> [main 9b8c7d6] Revert "feat: add authentication forms"
>  1 file changed, 5 deletions(-)


```text
git reset --soft HEAD~1
        │
        └── Deletes the last commit
            KEEPS code changes staged


git reset --hard HEAD~1
        │
        └── Deletes the last commit
            DESTROYS all code changes


git revert <commit>
        │
        └── Undoes a past commit
            CREATES a brand-new commit
```
---

### [Stashing](#sections)

***Syntax:***
```bash
git stash
git stash list
git stash pop
```

***Result:***
> Saved working directory and index state WIP on main: 9b8c7d6 Revert...
> 
> stash@{0}: WIP on main: 9b8c7d6 Revert "feat: add authentication forms"
> 
> On branch main
> Switched to branch 'main'
> Dropped refs/stash@{0} (e3b2a1c...)

[:arrow_up: Return to Top](#git)