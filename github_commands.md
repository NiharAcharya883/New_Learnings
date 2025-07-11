# Complete GitHub Commands Reference

## Table of Contents
- [Repository Setup and Configuration](#repository-setup-and-configuration)
- [Basic Commands](#basic-commands)
- [Branching and Merging](#branching-and-merging)
- [Remote Repository Operations](#remote-repository-operations)
- [Inspection and Comparison](#inspection-and-comparison)
- [Updates and Patching](#updates-and-patching)
- [History and Data Recovery](#history-and-data-recovery)
- [Advanced Operations](#advanced-operations)
- [Configuration and Setup](#configuration-and-setup)

## Repository Setup and Configuration

### Initialize a Repository
```bash
git init                    # Initialize a new Git repository
git init [directory]        # Initialize a repository in a specific directory
```

### Cloning
```bash
git clone [url]                    # Clone a repository
git clone [url] [directory]        # Clone into specific directory
git clone --depth [depth] [url]    # Shallow clone with specified depth
git clone --branch [branch] [url]  # Clone specific branch
```

## Basic Commands

### Adding Files
```bash
git add [file]          # Add a file to staging
git add .               # Add all changes to staging
git add -A              # Add all changes including deletions
git add -p             # Add changes interactively
git add -u             # Add modified and deleted files, exclude untracked
```

### Committing
```bash
git commit -m "[message]"    # Commit with a message
git commit -a -m "[message]" # Add modified files and commit
git commit --amend          # Modify the last commit
git commit --no-edit        # Commit using previous commit message
```

### Status and Info
```bash
git status              # Show working tree status
git status -s           # Give simplified status output
git status -v           # Show detailed status with diff
```

## Branching and Merging

### Branch Management
```bash
git branch                  # List branches
git branch [branch-name]    # Create new branch
git branch -d [branch]      # Delete branch
git branch -D [branch]      # Force delete branch
git branch -m [new-name]    # Rename current branch
git branch -a               # List all branches (local and remote)
git branch -r               # List remote branches
```

### Switching Branches
```bash
git checkout [branch]           # Switch to branch
git checkout -b [new-branch]    # Create and switch to new branch
git switch [branch]             # Switch to branch (new command)
git switch -c [new-branch]      # Create and switch to new branch
```

### Merging
```bash
git merge [branch]              # Merge branch into current branch
git merge --no-ff [branch]      # Create merge commit even if fast-forward possible
git merge --squash [branch]     # Squash merge
git merge --abort              # Abort merge in case of conflicts
```

### Rebasing
```bash
git rebase [branch]            # Rebase current branch onto another
git rebase -i HEAD~[n]         # Interactive rebase
git rebase --abort            # Abort rebase
git rebase --continue         # Continue rebase after resolving conflicts
```

## Remote Repository Operations

### Remote Management
```bash
git remote                      # List remotes
git remote -v                   # List remotes with URLs
git remote add [name] [url]     # Add remote
git remote remove [name]        # Remove remote
git remote rename [old] [new]   # Rename remote
git remote set-url [name] [url] # Change remote URL
```

### Fetching and Pulling
```bash
git fetch                       # Fetch from all remotes
git fetch [remote]             # Fetch from specific remote
git fetch --all                # Fetch all remotes
git fetch --prune              # Remove deleted remote branches
git pull                       # Fetch and merge from remote
git pull --rebase              # Fetch and rebase from remote
```

### Pushing
```bash
git push                       # Push to remote
git push [remote] [branch]     # Push branch to remote
git push -u origin [branch]    # Push and set upstream
git push --force              # Force push (use with caution)
git push --force-with-lease   # Safer force push
git push --all                # Push all branches
git push --tags               # Push all tags
```

## Inspection and Comparison

### Logging
```bash
git log                        # Show commit logs
git log --oneline             # Compact log view
git log --graph               # Show branch graph
git log --follow [file]       # Show file history
git log -p                    # Show diffs in log
git log -n [number]           # Show limited number of commits
git shortlog                  # Summarize git log
```

### Diffing
```bash
git diff                      # Show unstaged changes
git diff --staged            # Show staged changes
git diff [commit1] [commit2] # Compare two commits
git diff [branch1]..[branch2] # Compare two branches
git diff --name-only         # Show only names of changed files
```

### Inspection
```bash
git show [commit]            # Show commit details
git show [commit]:[file]     # Show file from specific commit
git blame [file]            # Show who changed what and when
git grep [pattern]          # Search working directory
```

## Updates and Patching

### Stashing
```bash
git stash                    # Stash changes
git stash save "[message]"   # Stash with message
git stash list              # List stashes
git stash pop               # Apply and remove stash
git stash apply             # Apply but keep stash
git stash drop              # Remove stash
git stash clear             # Remove all stashes
```

### Updating
```bash
git fetch origin            # Update remote refs
git reset --hard [commit]   # Reset to commit, discarding changes
git reset --soft [commit]   # Reset to commit, keeping changes staged
git reset --mixed [commit]  # Reset to commit, keeping changes unstaged
```

### Patching
```bash
git apply [patch]           # Apply patch file
git cherry-pick [commit]    # Apply specific commit
git revert [commit]         # Create new commit that undoes changes
```

## History and Data Recovery

### Reflog
```bash
git reflog                  # Show reference logs
git reflog show [branch]    # Show branch reflog
git reflog delete           # Delete reflog entries
```

### Recovery
```bash
git fsck                    # Check repository integrity
git gc                      # Clean up repository
git prune                  # Remove unreachable objects
git archive                # Create archive of repository
```

## Advanced Operations

### Submodules
```bash
git submodule add [url]     # Add submodule
git submodule init         # Initialize submodules
git submodule update       # Update submodules
git submodule sync        # Sync submodule URLs
```

### Worktree
```bash
git worktree add [path]     # Create new worktree
git worktree list          # List worktrees
git worktree remove [path]  # Remove worktree
```

### Bisect
```bash
git bisect start           # Start binary search
git bisect good [commit]   # Mark commit as good
git bisect bad [commit]    # Mark commit as bad
git bisect reset          # End binary search
```

## Configuration and Setup

### Global Configuration
```bash
git config --global user.name "[name]"      # Set global username
git config --global user.email "[email]"    # Set global email
git config --list                          # List all settings
git config --global core.editor "[editor]"  # Set default editor
```

### Repository Configuration
```bash
git config user.name "[name]"               # Set repository username
git config user.email "[email]"             # Set repository email
git config core.ignorecase [true/false]     # Set case sensitivity
```

### Aliases
```bash
git config --global alias.[shortcut] [command]  # Create command alias
```

### Ignore Files
```bash
git check-ignore [file]     # Check if file is ignored
git update-index --skip-worktree [file]  # Ignore changes to tracked file
git update-index --no-skip-worktree [file]  # Resume tracking changes
```

## Additional GitHub-Specific Commands

### GitHub CLI
```bash
gh repo create             # Create a new repository
gh repo fork              # Fork a repository
gh repo clone             # Clone a repository
gh pr create              # Create a pull request
gh pr checkout            # Check out a pull request
gh pr list               # List pull requests
gh issue create          # Create an issue
gh issue list           # List issues
gh auth login           # Authenticate with GitHub
```

### GitHub Actions
```bash
gh workflow list         # List workflows
gh workflow run         # Run a workflow
gh workflow disable     # Disable a workflow
gh workflow enable      # Enable a workflow
```

### Security
```bash
gh secret set           # Set a secret
gh secret list         # List secrets
gh secret remove       # Remove a secret
```

---

**Note**: This is a comprehensive list of Git and GitHub commands. Remember to:
- Always check the documentation for the most up-to-date information
- Use `git help [command]` for detailed information about specific commands
- Be careful with destructive commands like `--force` and `reset --hard`
- Keep your Git installation updated for access to the latest features 