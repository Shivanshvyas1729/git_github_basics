# git_github_basics
<img width="551" height="298" alt="image" src="https://github.com/user-attachments/assets/bc6882a0-31e2-4205-9c39-46bbce6ac906" />



<img width="1000" height="510" alt="image" src="https://github.com/user-attachments/assets/2c419479-b51b-4b2f-8030-53cf944ea089" />



- The Git Workflow FlowchartWorking Directory:
- You modify your files here.Staging Area: 
- You run git add to prepare files for a commit.
- Local Repository: You run git commit.
- Your files are now safely stored in Git's history.


<img width="654" height="228" alt="image" src="https://github.com/user-attachments/assets/c22ff853-5bec-48f4-8bdd-c12530b24f74" />


<img width="644" height="233" alt="image" src="https://github.com/user-attachments/assets/dcecd4bc-3858-4c1c-b121-53ceabb9da94" />

<img width="535" height="229" alt="image" src="https://github.com/user-attachments/assets/492d0e20-febe-4f1e-bfdb-6f8cd0b6aab1" />


<img width="782" height="218" alt="image" src="https://github.com/user-attachments/assets/5aee8492-255b-4bfd-9fbc-092946f4172c" />


<img width="772" height="282" alt="image" src="https://github.com/user-attachments/assets/88eea5ab-ac3f-4268-b1e2-da62c45c7661" />


----------------------------------------------------------------------
## TO CREATE AND CHECKOUT AT SAME TIME

### git checkout -b [yourbranchname]




<details>
<summary>Merge vs Rebase</summary>

This content is hidden by default.


### Git Merge — Definition

**Git Merge** is a command that combines changes from one branch into another by creating a new commit (called a **merge commit**) when necessary, while preserving the complete history of both branches.

**Example:**

```bash
git checkout main
git merge feature
```

**Key point:** It keeps the original branch structure and history intact.

---

### Git Rebase — Definition

**Git Rebase** is a command that moves or reapplies commits from one branch onto another branch, creating a linear commit history by rewriting commit history.

**Example:**

```bash
git checkout feature
git rebase main
```

**Key point:** It makes the project history cleaner and linear by replaying commits on top of the target branch.

---

### One-Line Difference

* **Merge:** Combines branches and preserves branch history.
* **Rebase:** Reapplies commits onto another branch to create a linear history.

</details>





<details>
<summary>Deattaching Head</summary>

### What is **Detaching HEAD** in Git?


### Easy Definition

> **Detached HEAD** means that `HEAD` points directly to a specific commit instead of pointing to a branch. You can view or experiment with that commit, but any new commits won't belong to a branch unless you create one.




### Why would you do this?

To:

* View old versions of the project
* Test code at a previous commit
* Debug issues in historical commits
* Explore history without affecting branches


Example:

git checkout a1b2c3d

or

<img width="1534" height="771" alt="image" src="https://github.com/user-attachments/assets/ee4d7e93-b713-47fc-891e-3f629011f5e9" />

</details>





<details>
<summary>Relative References (Relative Refs) in Git</summary>



Using full commit hashes to move around in Git can be inconvenient because hashes are long and difficult to remember. Instead, Git provides **relative references**, which let you navigate the commit history relative to a known location such as a branch name or `HEAD`.

### 1. Caret (`^`) Operator

The `^` operator refers to the **parent commit** of a commit.

Example:

```text
A --- B --- C (main)
```

* `main` → commit `C`
* `main^` → commit `B` (parent of `C`)
* `main^^` → commit `A` (grandparent of `C`)

Each additional `^` moves one commit further back in history.

Example:

```bash
git checkout main^
```

This checks out the parent of the commit pointed to by `main`.

---

### 2. Tilde (`~`) Operator

The `~` operator moves back a specified number of commits.

Example:

```text
A --- B --- C --- D (main)
```

* `main~1` → `C`
* `main~2` → `B`
* `main~3` → `A`

Example:

```bash
git checkout main~2
```

This checks out the commit that is two generations before `main`.

---

### Why Use Relative References?

Instead of remembering long commit hashes like:

```text
fed2da64c0efc5293610bdd892f82a58e8cbc5d8
```

you can simply use:

```bash
git checkout main^
git checkout HEAD~3
```

Relative references make navigating Git history much easier and more readable.

### Summary

* `^` = Move to the parent commit.
* `^^` = Move to the grandparent commit.
* `~n` = Move back `n` commits.
* Works with branch names (`main`, `feature`) and `HEAD`.

Examples:

```bash
git checkout main^
git checkout main~3
git checkout HEAD^^
git checkout HEAD~5
```

</details>
