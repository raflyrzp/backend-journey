## 📖 What is Git?

**Git** is a **distributed version control system** that allows you to keep a complete history of your project and manage your source code efficiently.

- ✅ Distributed: Every developer has a full copy of the project history.
- ✅ Local-first: You can commit and manage versions without Internet access.
- ✅ Fast: Git is optimized for performance.

Whether you're working solo or in a team, Git ensures you can:

- Go back to previous versions
- Work on multiple features at once
- Collaborate without breaking each other's code

---

## 📦 What is Git Used For?

| Purpose         | Description                            |
| --------------- | -------------------------------------- |
| Track changes   | Log who changed what, when, and why    |
| Undo mistakes   | Revert to previous versions            |
| Collaboration   | Merge code from multiple people safely |
| Experimentation | Test new ideas in isolated branches    |

---

## 🔀 Key Git Concepts

| Term       | Meaning                                                                  |
| ---------- | ------------------------------------------------------------------------ |
| Repository | A project tracked by Git (also called “repo”)                            |
| Commit     | A snapshot of your code and changes at a specific moment                 |
| Branch     | A parallel version of your code to develop features or fix bugs          |
| Merge      | Combine changes from one branch into another                             |
| Clone      | Create a copy of a remote repository                                     |
| Push       | Send your local commits to a remote repository                           |
| Pull       | Fetch and merge changes from the remote repository to your local machine |

---

## 🧪 Git Command Cheat Sheet

### 🔧 Basic Git Commands

| Command                   | Description                                      |
| ------------------------- | ------------------------------------------------ |
| `git init`                | Initialize a new Git repository                  |
| `git status`              | Show the current state of your working directory |
| `git add .`               | Stage all changes for commit                     |
| `git commit -m "message"` | Create a commit with a message                   |
| `git log`                 | View commit history                              |

---

### 🌿 Branching & Merging

| Command               | Description                                    |
| --------------------- | ---------------------------------------------- |
| `git branch`          | List all local branches                        |
| `git checkout -b dev` | Create and switch to a new branch `dev`        |
| `git merge dev`       | Merge the `dev` branch into the current branch |

---

### 🌍 Remote Operations (e.g., GitHub)

| Command                       | Description                                   |
| ----------------------------- | --------------------------------------------- |
| `git remote add origin <url>` | Connect local repo to a remote GitHub repo    |
| `git push -u origin main`     | Push `main` branch and set tracking to remote |
| `git pull`                    | Pull latest changes from remote to local      |

---

## 🌐 Git vs GitHub

| Git                    | GitHub                              |
| ---------------------- | ----------------------------------- |
| A version control tool | A platform to host Git repositories |
| Works offline          | Works online                        |
| CLI-based tool         | Web-based + CLI support             |

Think of **Git** as the engine, and **GitHub** as the garage to share and store your engine 🚗

---

## 💡 Best Practices

- Write meaningful commit messages
- Commit often and in small chunks
- Use `.gitignore` to exclude sensitive or unnecessary files
- Use branches for features or bug fixes
- Pull before you push to avoid conflicts

---

## 🧠 Summary

- Git helps track code changes and collaborate with others.
- You use commits, branches, and remotes to manage project history.
- Git works locally, and tools like GitHub help you sync and share your work online.

---
