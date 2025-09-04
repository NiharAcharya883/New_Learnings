# Git
--> Version Control System is a tool that helps to track changes in code.

# Github
--> Website that allows developers to store and manage their code using git.

--> Clone a git repo in a folder after opeining that folder in the terminal
git clone [URL]
cd <folder-name>

--> If you want to clone a git repo in a new device, it will ask to sign-in unless the repo is public. (works for pulling/cloning)

--> If you want to push the code, you have to sigin.
--> If you dont want to signin then do these steps.
1. Generate a personal access token (PAT) from github.
2. run this command - git remote set-url origin https://<your-username>@github.com/<your-username>/<repo-name>.git
3. git push origin main
--> You will be prompted for a password, but use PAT.