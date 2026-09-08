# GitHub

<img src = "GitHub_Invertocat_White.png" width = "100" height="100">

[:arrow_left: Return to Main README](README.md)

Learning [Resource](https://docs.github.com/en/get-started)

---

## Sections

> * [The Platform](#the-platform)
> * [Identity & Configuration](#identity--configuration)
>     * [View Global Identity](#view-global-identity)
>     * [Update Global Identity](#update-global-identity)
>     * [Update Repository Specific Identity](#update-repository-specific-identity)
> * [Repository Setup](#repository-setup)
>     * [Forking Remote Upstreams](#forking-remote-upstreams)
>     * [Tracking Multiple Remotes](#tracking-multiple-remotes)
> * [Issue Management](#issue-management)
>     * [Task List Interactivity](#task-list-interactivity)
>     * [Autolink References](#autolink-references)
> * [Pull Requests](#pull-requests)
>     * [Automated Closing Keywords](#automated-closing-keywords)
>     * [Review Lifecycles](#review-lifecycles)
> * [GitHub Shortcuts](#github-shortcuts)

---

## [The Platform](#sections)

```text
Local Machine             GitHub Cloud Hub
┌──────────────┐          ┌──────────────────────┐
│  Local Repo  │ ──push──>│ Remote Repo (origin) │
└──────────────┘          │                      │
       ▲                  │  ─ Pull Requests     │
       └─────────pull─────│  ─ Issues & Boards   │
                          └──────────────────────┘
```

---

## [Identity & Configuration](#sections)

#### [View Global Identity](#identity--configuration)

***Syntax: Terminal Bash***
```bash
git config --global user.name
git config --global user.email
```

***Result: Terminal Output***

```txt
User Name
user.email@example.com
```

#### [Update Global Identity](#identity--configuration)

***Syntax: Terminal Bash***
```bash
git config --global user.name "New Name"
git config --global user.email "new-email@example.com"
```

#### [Update Repository Specific Identity](#identity--configuration)

***Syntax: Terminal Bash***
```bash
git config user.name "Work Identity"
git config user.email "work-email@company.com"
```

---

## [Repository Setup](#sections)

#### [Forking Remote Upstreams](#repository-setup)

***Syntax: GitHub Website UI***
```text
Original Repo (Owner/Project)
        │
        └── Click [Fork] Button
                │
                ▼
  Your Copy (YourName/Project)
```

#### [Tracking Multiple Remotes](#repository-setup)

***Syntax: Terminal Bash***
```bash
git clone https://github.com
git remote add upstream https://github.com
git remote -v
```

***Result: Terminal Output***

```txt
origin    https://github.com (fetch)
origin    https://github.com (push)
upstream  https://github.com (fetch)
upstream  https://github.com (push)
```

---

## [Issue Management](#sections)

#### [Task List Interactivity](#issue-management)

***Syntax: Markdown Text Entry***
```text
- [ ] Task list items can be checked off inside an issue description
- [x] This item is completed
```

#### [Autolink References](#issue-management)

***Syntax: Markdown Text Entry***
* **Mentions:** `@username`
* **Issue Link:** `#12`

---

## [Pull Requests](#sections)

#### [Automated Closing Keywords](#pull-requests)

***Syntax: Markdown Text Entry***
```text
Closes #15
Fixes #22
```

#### [Review Lifecycles](#pull-requests)

***Syntax: GitHub Website UI***
```text
PR (Pull Request) Submitted ──> Code Review ──> Request Changes ──> LGTM (Looks Good To Me)──> Merged
```

---

## [GitHub Shortcuts](#sections)

***Syntax: Keyboard Press***

|  Key | Action |
| :--- | :----- |
| **`.`** | Opens repository in web-based VS Code (`github.dev`) |
| **`t`** | Activates File Finder search bar |
| **`w`** | Toggles branch and tag selection dropdown |
| **`s`** or **`/`** | Focuses repository search input |

