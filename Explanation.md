
--> Complete setup with remote

cd your-folder-name
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/repository-name.git
git push -u origin main




--> Create and switch to new branch
git checkout -b [branch_name]
git switch -c [branch]

--> Switch to branch
git checkout [branch]
git switch [branch]


--> Branch Management commands
git branch                  --> List branches
git branch [branch]         --> Create new branch
git branch -m [branch]      --> Rename current branch
git branch -d [branch]      --> Delete a branch
git branch -D [branch]      --> force delete a branch
git branch -a               --> List all branches (remote + local)
git branch -r               --> List remote branches


--> Fetch commands
git fetch                  --> Fetch from all remotes
git fetch [remote]         --> Fetch from specific remote
git fetch --all            --> Fetch all remotes
git fetch --prune          --> Remove deleted remote branches


# Configuring Git
git config --global user.name "Name"
git config --global user.email "email"
git config --list  # Check the configurations

# Git clone on local machine
git clone [git repo link]

# Push command - upload local repo code to remote
git push
git push -u origin [branch]
git push origin main

# Git init - used to create a new git repo
git init
git remote add origin <link>
git remote -v  # To verify remote
git branch
git branch -M main  (Rename branch)
git push origin main

# Diff and merge
git diff [branch]
git merge [branch]