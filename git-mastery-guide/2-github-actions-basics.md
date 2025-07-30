
🛠️ Manual Git Commands
Here, we are learning basic Git commands that every developer should know.
These commands are used for version control on your local system — such as tracking changes, saving them, and uploading them to GitHub.

📋 Commands Table
Git Command

What It Does?

Example Use

git init

Initializes a new local Git project

git init

git clone <url>

Downloads a project from GitHub to your computer

git clone https://github.com/xyz

git add .

Stages all your changes, preparing them for commit

git add .

git commit -m "msg"

Saves a new version (snapshot) of your project

git commit -m "login added"

git push

Uploads your local changes to the online repository (GitHub)

git push origin main

git status

Shows which files have been changed, which are not staged, and which are not committed

git status

git diff

Displays the changes you've made to your files (before adding them to the staging area)

git diff

git log

Shows the entire commit history of your project

git log

git branch

Lists all branches and shows which branch you are currently on

git branch

git branch <name>

Creates a new branch

git branch feature-x

git checkout <name>

Switches to another branch or a specific commit

git checkout develop

git pull

Downloads the latest changes from the remote repository to your local system

git pull origin main

git merge <branch>

Integrates changes from one branch into another

git merge feature-x

git rm <file>

Removes a file from the staging area and the working directory

git rm old-file.txt

git reset <file>

Unstages a file from the staging area, but keeps the changes in the working directory

git reset HEAD file.txt

git revert <commit-hash>

Undoes the changes of a specific commit by creating a new commit

git revert abc123def

🚀 Basic Git Workflow (How to Work?)
Here's a simple workflow you can follow when working on a project:

Project Start/Clone:

If it's a new project: git init

If cloning from GitHub: git clone <repository-url>

Making Changes:

Make changes to your files (write code, add/delete files).

Viewing Changes:

See what changes have occurred: git status

View detailed changes: git diff

Adding Changes to Staging Area:

Add all changes: git add .

Add a specific file: git add <file-name>

Committing Changes:

Commit with a meaningful message: git commit -m "What you changed"

Uploading Changes (to GitHub):

Send your local changes to GitHub: git push origin <branch-name> (usually main or master)

Getting Latest Changes (If working in a team):

Download changes from other team members: git pull origin <branch-name>

✨ Pro Tips & Best Practices (Some Important Points)
Commit Messages: Always write clear and descriptive commit messages. Explain what you changed and why.

Bad: git commit -m "changes"

Good: git commit -m "Add user login functionality with form validation"

Frequent Commits: Make small, frequent commits. Each commit should represent a single logical change. This makes debugging and reverting easier.

Use Branches: Always create a new branch for new features or bug fixes. Keep the main branch stable.

git branch feature/new-dashboard

git checkout feature/new-dashboard

Pull/Fetch Regularly: When working in a team, git pull or git fetch regularly so you're working on the latest code and to minimize merge conflicts.

.gitignore File: Add files you don't want to include in version control (like node_modules, .env files, build output) to the .gitignore file.
