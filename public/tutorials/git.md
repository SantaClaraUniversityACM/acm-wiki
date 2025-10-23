# Git Tutorial

Written by Jake Esperson, 2025.

Hello everyone! Git is an essential tool, whether you're making a personal project or competing in a hackathon and is the main way us developers share, ship, and manage code. In this tutorial, I'm going to show you how to set up Git, how to push and pull from Github, and how to collaborate efficiently with team members.

Also, this tutorial will NOT be using GitHub desktop, which simplifies Git operations, but is not used in the industry and isn't really practical besides simple push and pull operations, so I will be showing you how to use the CLI tool instead, as well as the VSCode built-in extension.

## Table of Contents
- [Git Tutorial](#git-tutorial)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
    - [Windows Install](#windows-install)
    - [MacOS Install](#macos-install)
    - [Both](#both)
  - [Git Setup w/ GitHub](#git-setup-w-github)
  - [Branching, Pushing, Pulling, and Collaboration](#branching-pushing-pulling-and-collaboration)
    - [Staging and Committing](#staging-and-committing)
    - [Branching](#branching)
    - [Pushing and Pulling](#pushing-and-pulling)
    - [Collaboration Tips](#collaboration-tips)

## Installation

### Windows Install

- Navigate to the [install page](https://git-scm.com/downloads/win) and click the `Git for Windows/x64 Setup` link
- Click through the installer, you don't have to change any settings in the install wizard
  - You can choose to change the default editor to VSCode if you'd like from the dropdown
- Open a new Powershell terminal and type `git version`. The version number should show up if you got it right
  - Reference this short [YouTube video](https://www.youtube.com/watch?v=t2-l3WvWvqg) for a visual guide

### MacOS Install

- Open a new terminal and install Homebrew via the following command
  - `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
  - Homebrew is a popular installer for MacOS and is good to have for any development task
- Now, you need to add brew to your PATH in order to use it properly
  - Look for `Warning: /opt/homebrew/bin is not in your PATH`
  - Under that, scroll to the `Next steps` section and enter the two commands it tells you to
    - Should be `(echo; echo 'eval...` and `eval ...`
  - Reference this short [YouTube video](https://www.youtube.com/watch?v=IWJKRmFLn-g) for a visual guide
- After this, run `brew install git`
- Also install the git credential manager with `brew install --cask git-credential-manager`
- Confirm the install worked with `git version`. The version number should show up if you got it right

### Both

- Regardless of your device, you'll need the GitHub CLI to authenticate with GitHub specifically
- Go to the [download page](https://cli.github.com/) and follow the instructions according to your device, it's a straightforward installer

## Git Setup w/ GitHub

First, we need to set up Git correctly in order to clone from GitHub, which we will do by cloning a sample ACM repo

- Make a directory for your coding projects
  - I usually recommend `C:\repos` for Windows or `~/repos` on MacOS and Linux
- Open a VSCode window in this folder and open a terminal in this folder using `Ctrl + ~`
- In that terminal, enter the following
  - `git config --global user.name "GITHUB_USERNAME"`
  - `git config --global user.email "GITHUB_EMAIL"`
- Clone our ACM sample repo using the following command
  - `git clone https://github.com/SCUACM/api-workshop-2025`
  - This URL is just the web URL of the repo, which can be found by clicking the green `Code` button and switching the tab to `HTTPS`
- You've just cloned a public repo! However, most of your repos will be private when you make them, so we need to use the GitHub CLI we installed earlier
  - In the terminal, enter `gh auth login`
    - This will take you to an interactive session controller by your arrow keys
    - Select `GitHub.com` -> `HTTPS` -> `Y` -> `Login with a web browser`
    - Copy the one-time code it gives you and press Enter
    - Select your GitHub account or sign in, then enter the code and authorize
    - Return to the terminal and see that you're now authenticated
- Now, you can clone any private repo using `gh repo clone` instead, which is the first command you see when you click the green `Code` button

## Branching, Pushing, Pulling, and Collaboration

VSCode has a built-in Git extension that makes it easy to manage your repository visually, which you can access with Source Control icon (the branch icon) on the left sidebar, or press `Ctrl+Shift+G`

### Staging and Committing

- You can view Modified, Added, and Deleted files in the panel. Click a file to see the diff between the repo copy and the copy you've edited
- Click the `+` next to a file to stage it, or click the `+` at the top to stage all
  - Enter a commit message in the input box and click the checkmark to commit

### Branching

Branches let you work on new features or fixes without affecting the main codebase. This is essential for collaboration and keeping your main branch stable.

- In VSCode, click the branch name in the bottom-left corner to create, switch, or delete branches
  - You can also use the Command Palette (`Ctrl+Shift+P`) and search for "Git: Create Branch" or "Git: Checkout to..."
- Remember to fetch often as well, which searches for new commits to your branch
  - Click the circular arrows in the bottom-left corner to sync

### Pushing and Pulling

Pushing uploads your changes to GitHub, while pulling downloads the latest changes from the remote repository.

- After committing, click the green button to push changes
  - This button will not appear if you have un-committed changes or you need to pull, both of which can be done in the bottom-left corner when they're applicable
- If you cloned a repo and made changes, always pull before you push to avoid conflicts

### Collaboration Tips

- **Pull Requests (PRs):**  
  When collaborating, don't push directly to `main`. Instead, push your branch and open a Pull Request on GitHub. This lets others review your code before merging.
- **Resolving Conflicts:**  
  If two people edit the same part of a file, you'll get a merge conflict. Git will mark the conflict in the file. Edit the file to resolve the conflict, then add and commit the resolved file.
- **Commit Messages:**  
  Write clear, concise commit messages that explain what you changed. For example:  
  `git commit -m "Add login feature"`
- **Sync Often:**  
  Regularly pull from the remote repository to keep your local copy up to date and avoid large conflicts.
- **Review Code:**  
  Use GitHub's review tools to comment on PRs, suggest changes, and approve code before merging.
