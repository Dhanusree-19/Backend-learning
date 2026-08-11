# Git & GitHub — Learning Notes

## 1. Version Control System (VCS)

A Version Control System tracks and manages changes made to files over time.

### Why VCS?

* Track changes
* Maintain history
* Restore previous versions
* Collaboration
* Work on features separately

---

## 2. Evolution of Version Control

```text
Manual Version Management
        ↓
Local VCS
        ↓
Centralized VCS
        ↓
Distributed VCS
        ↓
Git
        ↓
GitHub
```

---

## 3. Local Version Control

Stores version history on the developer's own computer.

Examples:

* SCCS
* RCS

Limitation: Not suitable for large team collaboration.

---

## 4. Centralized Version Control (CVCS)

A central server contains the main repository and version history.

```text
             Central Server
              /     |     \
             /      |      \
        Developer Developer Developer
            A         B         C
```

Developers have local working copies, but the central server contains the authoritative repository.

Examples:

* CVS
* SVN
* Perforce

### Problems

* Depends more on central server/network
* Developers don't have independent complete repositories
* Repository history is mainly maintained centrally

---

## 5. Distributed Version Control (DVCS)

Every developer has a complete local repository and history.

```text
Developer A → Full Repository
Developer B → Full Repository
Developer C → Full Repository
```

Examples:

* Git
* Mercurial
* Bazaar

### Advantages

* Work offline
* Fast local operations
* Complete history locally
* Easy branching and merging

---

## 6. Git

**Git is a Distributed Version Control System (DVCS).**

* Created by **Linus Torvalds**
* Created in **2005**
* Created mainly for Linux kernel development

### Why Git?

* Fast
* Distributed
* Offline work
* Efficient branching and merging
* Handles large projects
* Maintains complete history

---

## 7. Git vs GitHub

### Git

Version control software used to track code changes and maintain project history.

### GitHub

Online platform used for:

* Hosting Git repositories
* Collaboration
* Pull Requests
* Code reviews
* Issues

```text
Git    = Version Control
GitHub = Hosting + Collaboration
```

Git can work without GitHub.

---

## 8. Git Repository

A Git repository is a project managed by Git.

```bash
git init
```

`git init` initializes a directory as a Git repository and creates the `.git` directory.

---

## 9. Three Main Areas of Git

```text
Working Directory
       ↓ git add
Staging Area
       ↓ git commit
Repository
```

### Working Directory

Where we create and modify files.

### Staging Area

Where we select changes for the next commit.

### Repository

Where Git stores commits and project history.

---

## 10. Commit

A commit is a recorded checkpoint of changes in the Git repository.

Example:

```text
Commit 1 → Create project
Commit 2 → Add login
Commit 3 → Add registration
```

---

## 11. Basic Git Commands

| Command      | Purpose                              |
| ------------ | ------------------------------------ |
| `git init`   | Initialize a Git repository          |
| `git status` | Check repository state               |
| `git add`    | Stage changes                        |
| `git commit` | Save staged changes to local history |
| `git log`    | View commit history                  |
| `git diff`   | View changes                         |

### Basic Workflow

```bash
git status
git add .
git commit -m "message"
```

---

## 12. Remote Repository

A remote is another Git repository connected to the local repository.

Usually the remote repository is hosted on GitHub.

```text
Local Repository
       |
     origin
       |
       ↓
Remote Repository
      GitHub
```

### `git remote -v`

Shows connected remote repositories and their URLs.

```bash
git remote -v
```

### `git remote add origin <URL>`

Connects the local repository to a remote repository.

```bash
git remote add origin <repository-url>
```

`origin` is the conventional name given to the remote.

> `origin` is not GitHub. It is the name/reference used for the remote repository.

---

## 13. Branch

A branch is an independent line of development in a Git repository.

### Why use branches?

* Develop features separately
* Fix bugs separately
* Protect main code
* Allow parallel development
* Keep unfinished work away from main

Example:

```text
main
 |
 A
 |
 B
  \
   C
   |
   D
feature-login
```

---

## 14. Branch Commands

### `git branch`

View or manage branches.

```bash
git branch
```

### `git switch`

Switch to another branch.

```bash
git switch feature-login
```

### `git switch -c`

Create and switch to a new branch.

```bash
git switch -c feature-login
```

---

## 15. Merge

Merge combines changes from one branch into another branch.

Example:

```bash
git switch main
git merge feature-login
```

### Why merge?

Used when:

* A feature is completed
* A bug fix is completed
* Changes need to be integrated into another branch

### Branch + Merge Workflow

```text
main
 ↓
Create feature branch
 ↓
Work on feature
 ↓
git add
 ↓
git commit
 ↓
Switch to main
 ↓
git merge feature-branch
 ↓
Feature integrated into main
```

---

## 16. Important Concepts Learned

```text
VCS
 ↓
Centralized vs Distributed
 ↓
Git
 ↓
Git Repository
 ↓
Working Directory
 ↓
Staging Area
 ↓
Commit
 ↓
Branch
 ↓
Merge
 ↓
GitHub Remote Repository
```

---

## 17. Key Interview Points

* **VCS:** Tracks and manages changes to files.
* **CVCS:** Central server contains the authoritative repository.
* **DVCS:** Each developer has a complete local repository.
* **Git:** Distributed Version Control System.
* **GitHub:** Online hosting and collaboration platform for Git repositories.
* **Commit:** Records changes in the local repository.
* **Branch:** Independent line of development.
* **Merge:** Combines changes from one branch into another.
* **Push:** Sends local commits to a remote repository.
* **Pull:** Gets remote changes and integrates them locally.
* **Origin:** Conventional name for a remote repository.

---

