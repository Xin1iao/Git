# Git Tutorial

## 1.Introduction to Git for CS Students

Welcome to this Git tutorial! Whether you are working on a small personal project or collaborating on a large codebase, understanding version control is crucial in the world of computer science and software development. Git, a powerful and widely-used version control system, is an essential tool for developers. In this tutorial, we will explore the basics of Git, helping you to manage your coding projects more effectively.

### 1.1 What is Git?

Git is a distributed version control system created by Linus Torvalds in 2005. It allows multiple developers to work together on the same project without interfering with each other's work. Git tracks the changes you make to files, so you have a complete history and can revert to specific versions should you need to. It's also incredibly useful for managing changes to projects over time.

### 1.2 Why Use Git?

1. **Track Changes:** Git keeps a record of every modification to the code. If something goes wrong, it's easy to compare earlier versions of the code to help find the cause.

2. **Collaboration:** Multiple people can work on the same project simultaneously. Git manages changes made by multiple people efficiently, ensuring that parallel work doesn't conflict.

3. **Branching and Merging:** Git's branching feature lets you create separate branches for different features or sections of your project. Once a feature is complete, you can merge that branch back into the main project.

4. **Remote Repositories:** With Git, you can keep a local repository on your machine and a remote repository online (like on GitHub), allowing for easy backups and collaboration.

Throughout this tutorial, we'll be using a sample coding project to demonstrate various Git commands and workflows, including setting up a repository, making and tracking changes, branching, merging, and more. Our goal is to equip you with the knowledge and skills to use Git confidently in your projects.

Let's get started!

## 2.Simple Usage of Git

1. **git init**

   This command initializes a new Git repository. It creates a new subdirectory named `.git` that houses all necessary repository files – a skeletal repository. 

   ```bash
   git init
   ```

   Input the command

   ```shell
   git init
   Initialized empty Git repository in /Users/XXX(your current folder road)/.git
   ```

   The result is 
   
   <img src="assets/Screenshot 2024-02-11 at 12.54.48 AM.png" alt="Screenshot 2024-02-11 at 12.54.48 AM" style="zoom:100%;" />
   
2. **git clone [url]**: Used to copy a Git repository from an existing URL. It's a way to download and work on a project that's been shared via a Git repository (Take `https://github.com/piglei/zkpython_example` for an example).

   ```bash
   git clone https://github.com/example/repo.git
   ```

   The result is

   ```shell
   git clone https://github.com/piglei/zkpython_example.git
   Cloning into 'zkpython_example'...
   remote: Enumerating objects: 14, done.
   remote: Total 14 (delta 0), reused 0 (delta 0), pack-reused 14
   Receiving objects: 100% (14/14), 7.91 KiB | 3.96 MiB/s, done.
   Resolving deltas: 100% (2/2), done.
   ```

   <img src="assets/Screenshot 2024-02-10 at 9.43.13 PM.png" alt="Screenshot 2024-02-10 at 9.43.13 PM" style="zoom:50%;" />

3. **git status**: Displays the status of the working directory and staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.

   ```bash
   git status
   ```

   The result is

   ```shell
   cd zkpython_example
   git status
   On branch master
   Your branch is up to date with 'origin/master'.
   
   nothing to commit, working tree clean
   ```

   <img src="assets/Screenshot 2024-02-10 at 9.47.41 PM.png" alt="Screenshot 2024-02-10 at 9.47.41 PM" style="zoom:50%;" />

4. **git add [file]**: Adds a file to the staging area. It's a way to tell Git that you want to include updates to a particular file in the next commit. You can use `git add .` to add all new and changed files to the staging area. Now we first touch a py file called “example.pt”

   ```bash
   git add example.py
   ```

   If there is no hint, we success.

5. **git commit -m "[commit message]"**: Records or snapshots the file permanently in the version history with a descriptive message. The message should be clear and descriptive of the changes made.

   ```bash
   git commit -m "Initial project version"
   ```

   The result is

   ```shell
   git commit -m "Initial project version"
   [master 7761f91] Initial project version
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 example.py
   ```
   
   <img src="assets/Screenshot 2024-02-10 at 11.10.00 PM.png" alt="Screenshot 2024-02-10 at 11.10.00 PM" style="zoom:100%;" />

6. **git branch [branch-name]**: Creates a new branch. Branches are used to develop features isolated from each other.

   ```bash
   git branch new-feature
   ```

   Then we search branch

   ```shell
   * master
     new-feature
   (END)
   ```

7. **git checkout [branch-name]**: Switches to a specified branch and updates the working directory to match.

   ```bash
   git checkout new-feature
   ```

   The result is

   ```shell
   git checkout new-feature
   Switched to branch 'new-feature'
   ```
   
   <img src="assets/Screenshot 2024-02-10 at 11.10.27 PM.png" alt="Screenshot 2024-02-10 at 11.10.27 PM" style="zoom:100%;" />

8. **git merge [branch]**: Merges the specified branch’s history into the current branch. This is usually done in the main branch to bring in new features or fixes.

   ```bash
   git merge new-feature
   ```

   The result is

   ```shell
   git merge new-feature
   Already up to date.
   ```

   <img src="assets/Screenshot 2024-02-11 at 1.49.03 AM.png" alt="Screenshot 2024-02-11 at 1.49.03 AM" style="zoom:100%;" />
   
9. **git rebase [branch]**: Reapply commits on top of another base tip. It's used to integrate changes from one branch into another.

   ```bash
   git rebase master
   ```

   The result is

   ```shell
   git rebase master
   Current branch new-feature is up to date.
   ```

   <img src="assets/Screenshot 2024-02-11 at 1.51.41 AM.png" alt="Screenshot 2024-02-11 at 1.51.41 AM" style="zoom:100%;" />

10. **git stash**: Temporarily shelves or stashes changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on.

    ```bash
    git stash
    ```

    The result is 

    ```shell
    git stash
    No local changes to save
    ```

   <img src="assets/Screenshot 2024-02-11 at 1.54.09 AM.png" alt="Screenshot 2024-02-11 at 1.54.09 AM" style="zoom:100%;" />

11. **git stash pop**: Reapplies the changes that were stashed away by `git stash`.

    ```bash
    git stash pop
    ```

    <img src="assets/Screenshot 2024-02-10 at 11.14.03 PM.png" alt="Screenshot 2024-02-10 at 11.14.03 PM" style="zoom:100%;" />

12. **git log**: Shows the commit logs.

    ```bash
    git log
    ```

    <img src="assets/Screenshot 2024-02-10 at 11.14.40 PM.png" alt="Screenshot 2024-02-10 at 11.14.40 PM" style="zoom:100%;" />

13. **git pull**: Fetches and merges changes on the remote server to your working directory.

    ```bash
    git pull
    ```

14. **git push**: Pushes the changes in your local repository to a remote repository.

    ```bash
    git push origin master
    ```

    The result is

    ```shell
    ERROR: Permission to piglei/zkpython_example.git denied to username.
    fatal: Could not read from remote repository.
    
    Please make sure you have the correct access rights
    and the repository exists.
    ```

    This typically indicates an issue with access permissions to the Git repository. The most common cause is that the user `username` does not have permission to access the `piglei/zkpython_example.git` repository. If we are the repository owner, we need to add `username` as a collaborator. If we are `username`, you should request access from the repository owner.
