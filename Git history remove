# Complete Guide to Permanently Removing Files from Git History

When you need to remove sensitive or unwanted files from your Git history, there are two main tools you can use: BFG Repo-Cleaner and git-filter-repo. Both tools have their own advantages and considerations. This guide will walk you through both methods and include important safety considerations to keep in mind.

## Table of Contents
1. [Safety Considerations](#safety-considerations)
2. [Using BFG Repo-Cleaner](#using-bfg-repo-cleaner)
    - [Installing BFG](#installing-bfg)
    - [Removing Files with BFG](#removing-files-with-bfg)
3. [Using git-filter-repo](#using-git-filter-repo)
    - [Installing git-filter-repo](#installing-git-filter-repo)
    - [Removing Files with git-filter-repo](#removing-files-with-git-filter-repo)
4. [Post-Processing Steps](#post-processing-steps)
5. [Conclusion](#conclusion)

## Safety Considerations

Before you start removing files from your Git history, consider the following safety tips:
- **Backup Your Repository**: Always make a backup of your repository before performing history rewrites. This ensures you can recover if something goes wrong.
- **Communicate with Your Team**: Inform your team about the history rewrite. They will need to re-clone the repository after the changes.
- **Understand the Consequences**: History rewrites change commit hashes, which can affect branches, tags, and pull requests. Be prepared for potential disruptions.

## Using BFG Repo-Cleaner

### Installing BFG

BFG Repo-Cleaner is a simpler, faster alternative to git-filter-branch for removing unwanted data from your Git repository history.

1. **Download BFG Repo-Cleaner**:
   You can download the latest version of BFG from the official [BFG Repo-Cleaner GitHub page](https://github.com/rtyley/bfg-repo-cleaner/releases).

2. **Install BFG**:
   Place the downloaded `bfg.jar` file in a directory of your choice and make sure you have Java installed.

### Removing Files with BFG

1. **Clone Your Repository**:
   Clone your repository using the `--mirror` option:
   ```sh
   git clone --mirror https://github.com/your-repo.git
   ```

2. **Run BFG to Remove Files**:
   Use BFG to remove specific files. For example, to remove all `.log` files:
   ```sh
   java -jar bfg.jar --delete-files *.log your-repo.git
   ```

3. **Clean Up and Repack**:
   After BFG has made the changes, perform a cleanup and repack the repository:
   ```sh
   cd your-repo.git
   git reflog expire --expire=now --all && git gc --prune=now --aggressive
   ```

4. **Push Changes**:
   Push the changes back to your remote repository:
   ```sh
   git push --force
   ```

## Using git-filter-repo

### Installing git-filter-repo

`git-filter-repo` is a versatile tool that allows for more complex and flexible history rewriting than BFG.

1. **Install git-filter-repo**:
   You can install `git-filter-repo` using pip:
   ```sh
   pip install git-filter-repo
   ```

### Removing Files with git-filter-repo

1. **Clone Your Repository**:
   Clone your repository to a local directory:
   ```sh
   git clone https://github.com/your-repo.git
   cd your-repo
   ```

2. **Run git-filter-repo to Remove Files**:
   Use `git-filter-repo` to remove specific files. For example, to remove all `.log` files:
   ```sh
   git filter-repo --path '*.log' --invert-paths
   ```

3. **Push Changes**:
   Push the changes back to your remote repository:
   ```sh
   git push --force
   ```

## Post-Processing Steps

After using either BFG or git-filter-repo, follow these additional steps:

1. **Inform Your Team**:
   Let your team know about the history rewrite. They will need to re-clone the repository:
   ```sh
   git clone https://github.com/your-repo.git
   ```

2. **Update References**:
   Ensure all branches and tags are updated:
   ```sh
   git fetch --all
   ```

3. **Verify Repository Integrity**:
   Check the integrity of your repository to ensure everything is correct:
   ```sh
   git fsck
   ```

4. **Update CI/CD Pipelines**:
   If you have CI/CD pipelines, make sure they are updated to reflect the new commit hashes.

## Conclusion

Removing files from your Git history is a powerful but potentially disruptive action. Always take precautions, such as backing up your repository and informing your team. Whether you use BFG Repo-Cleaner or git-filter-repo, follow the steps carefully and verify your repository's integrity afterward.

Happy coding!
