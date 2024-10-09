# Git Setup

Many developers maintain accounts with popular Git providers such as [Bitbucket](https://bitbucket.org) and [GitHub](https://github.com). This guide will focus on setting up an account on GitHub, but the principles apply equally if you use Bitbucket.

Begin by enabling [Two-Factor Authentication (2FA)](https://github.com/settings/security) to enhance the security of your GitHub account.


To streamline your workflow and eliminate the need to enter your password each time you push or pull code, it’s advisable to set up an [SSH key](https://help.github.com/articles/generating-ssh-keys). 

To create your SSH key, you can refer to the [YouTube tutorial](https://www.youtube.com/watch?v=snCP3c7wXw0) or simply follow the detailed steps outlined below.

<br />

## Generating a new SSH key

* Open Terminal.
* Paste the text below, replacing the email used in the example with your GitHub email address.

```zsh
ssh-keygen -t ed25519 -C "github-email@mail.com"
```

* Copy the SSH public key to your clipboard.

```zsh
pbcopy < ~/.ssh/id_ed25519.pub
```

* In the upper-right corner of any page on GitHub, click your profile photo, then click  Settings.
* In the "Access" section of the sidebar, click  SSH and GPG keys.
* Click New SSH key or Add SSH key.
* In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".
* Select the type of key and Authentication from dropdown menu.
* In the "Key" field, paste your public key.
* Click Add SSH key.
* If prompted, confirm access to your account on GitHub.

### Import Repositories to Github

Leverage the [GitHub Importer tool](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/importing-a-repository-with-github-importer) to migrate your repository from Bitbucket to GitHub seamlessly.

<br />

## Git Dotfiles

I have created the Git config, and Git ignores dotfiles, which are available for download within this directory.

<br />

## Learn Git and Github

Discover the essential Git command line commands by [clicking here](https://quickref.me/git.html). Dive into  comprehensive series on [Git and GitHub](https://www.youtube.com/watch?v=HGJ4eb5A4Yo&list=PLbGui_ZYuhigWA1mNWzwErSBIZvgOJbNc), or if you don't like the command line, then learn Git with user-friendly [GUI clients](https://www.youtube.com/watch?v=S7XpTAnSDL4).

<br />

## Frequently used Git Commands

The following are the most commonly used Git commands.

### Git Configuration

```zsh
System settings are stored in: /etc/gitconfig
Global settings are stored in: ~/.gitconfig
Local settings are stored in: .git/config
```

To show configuration file output on command line

```zsh
cat.gitconfig
```

To setup username and email address

```zsh
git config --global user.name "Khurram Alvi"
git config --global user.email "github-email@mail.com"
```

### Git Aliases

[Tips](http://githowto.com/aliases) for creating aliases

Setup aliases and shortcuts for git commands:

```zsh
git config --global alias.b branch
git config --global alias.s status
git config --global alias.d diff
git config --global alias.m merge
git config --global alias.ci commit
git config --global alias.co checkout
```

Which will return below shortcuts:

```zsh
b = branch
s = status
d = diff
m = merge
co = checkout
ci = commit
```

You can also create aliases in .zshrc file:

```zsh
alias ga='git add'
```

To update feature branch from the main

```zsh
function update(){
  git checkout main && git fetch && git pull && git checkout - && git rebase main
}
```

### Git Diff

To compare the difference between staged and working directory:

```zsh
git diff --staged filename
```

To compare the difference between working directory and stage:

```zsh
git diff HEAD filename
```

To compare different branches:

```zsh
git diff --name-status master..branch
```

Git Log

Review local and remote commits:

```zsh
git log
```

Review local commits:

```zsh
git reflog
```

Review local and remote commits with stats:

```zsh
git log --stat
```

Review local commits with stats:

```zsh
git reflog --stat
```

Review last local commits:

```zsh
git log -p
git show
```

To see pretty git log:

```zsh
dl = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''%C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
```

or

```zsh
bl = log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
```

### Git Branches

To switch branch:

```zsh
git checkout branch-name
```

To create a feature branch:

```zsh
git checkout -b feature-branch-name
```

To view all local and remote branches:

```zsh
git branch -a
```

To view all local and remote branches:

```zsh
git branch -a
```

To delete a local branch:

```zsh
git branch -d the_local_branch
```

To delete a remote branch (if you know what you are doing!):

```zsh
git push origin --delete the_local_branch
```

When you get the error: unable to push to unqualified destination: **the_remote_branch**

The destination refspec neither matches an existing ref on the remote nor begins with refs/, and we are unable to guess a prefix based on the source ref.

error: failed to push some refs to 'git@repository_name'

Perhaps anyone else has already deleted the branch. Try to synchronise your branch list with:

```zsh
git fetch -p
```

### Git Add

Stage all changes in &#60;file&#62; for the next commit:

```zsh
git add file-name
```
    
Stage all changes in &#60;directory&#62; for the next commit:

```zsh
git add <directory>
```

Stage all changes for the next commit:
    
```zsh
git add .
```

Begin an interactive staging session that lets you choose portions of a file to add to the next commit. This will present you with a chunk of changes and prompt you for a command. Use y to stage the chunk, n to ignore the chunk, s to split it into smaller chunks, e to manually edit the chunk, and q to exit.

```zsh
git add -p
```

### Git Commit

Commit the staged snapshot, but instead of launching a text editor, use &#60;message&#62; as the commit message.

```zsh
git commit -m "<message>"
```

Commit a snapshot of all changes in the working directory. This only includes modifications to tracked files (those that have been added with git add at some point in their history).

```zsh
git commit -a
```

You can also combine flags:

```zsh
git commit -am
```

To see all last commits on GitHub:

```zsh
https://github.com/khurramalvi/gitPlayground/commit/commit/
```
    
### Git Revert

Revert some existing commits. To be on safe side branch out from master:

```zsh
git checkout master
```

Get all commit IDs you want to revert:

```zsh
git reflog
```

Revert all commits:

```zsh
git revert --no-commit wxyz789
git revert --no-commit abcz789
git revert --no-commit yzdb789
git revert --no-commit yges789
git commit --amend -m "New commit message"
```

### Git Status

List which files are staged, unstaged, and untracked:

```zsh
git status
```

### Git Ignore

To ignore files, folder or file extension, create .gitignore file:

```zsh
touch .gitignore
open .gitignore
```
Specify files, folder and extensions you want to ignore:

```zsh
temp
test/*.txt
*.php
```

However we can watch any specific under .gitignore by simply adding bang "!" character:

```zsh
!test/master.txt
```

To ignore file permanently. This will keep the file in the repository but won't track changes:

```zsh
git update-index --assume-unchanged db/schema.rb
```

You can switch the tracking anytime by using:

```zsh
git update-index --no-assume-unchanged db/schema.rb
```

### Git Merge

To merge feature branch into master:

```zsh
git merge feature-branch-name
```

To rebase feature branch into master for maintain pretty log file:

```zsh
git rebase feature-branch-name
```

To view repository/origin url:

```zsh
git config --get remote.origin.url
```

After fetching, remove any remote-tracking branches which no longer exist on the remote.

### Git Stash

To stash file:

```zsh
git stash
```

To see files in stash:

```zsh
git stash list
```

To apply stash:

```zsh
git stash apply
```

This will stash everything that you haven't previously added. Just git add the things you want to keep, then run it.

```zsh
git stash --keep-index
```

### Git Undo

Update all files in the working directory to match the specified commit. You can use either a commit hash or a tag as the &#60;commit&#62; argument. This will put you in a detached HEAD state.

```zsh
git checkout a1e8fb5
```

If you’re only interested in a single file, you can also use git checkout to fetch an old version of it. For example, if you only wanted to see the hello.py file from the old commit, you could use the following command:

```zsh
git checkout a1e8fb5 hello.py
```

If you decide you don’t want to keep the old version, you can check out the most recent version with the following:

```zsh
git checkout HEAD hello.py
```

### Git Reset

To make local directory same as remote repository. It will overwrite all local commits:

```zsh
git reset --hard origin/main
```

If you have uncommitted changes that you want to discard, use this:

```zsh
git reset --hard
```

which is equivalent to:

```zsh
git reset --hard HEAD
```

This removes all the local uncommitted changes. If you want to remove some offending commits from your local branch, try rewinding it:

```zsh
git reset --hard HEAD^ #moves HEAD back by one commit
```

or e.g.

```zsh
git reset --hard HEAD~3 #moves HEAD back by 3 commits
```

Use these with caution, as you won't be able to undo these operations. Once you're done cleaning up your local branch, use git pull to get the latest code.

### Remote Repositories

Fetch the specified remote’s copy of the current branch and immediately merge it into the local copy:

```zsh
git pull origin main
```

Same as the above command, but instead of using git merge to integrate the remote branch with the local one, use git rebase:

```zsh
git pull --rebase origin main
```

Dedicated configuration option for pulling with --rebase

```zsh
git config --global branch.autosetuprebase always
```

Push the specified branch to &#60;remote&#62;, along with all of the necessary commits and internal objects. This creates a local branch in the destination repository. To prevent you from overwriting commits, Git won’t let you push when it results in a non-fast-forward merge in the destination repository

```zsh
git push origin main
```

Push all of your local branches to the specified remote:

```zsh
git push <remote> --all
```

Tags are not automatically pushed when you push a branch or use the --all option. The --tags flag sends all of your local tags to the remote repository:

```zsh
git push <remote> --tags
```

List the remote connections you have to other repositories:

```zsh
git remote
```

Same as the above command, but include the URL of each connection:

```zsh
git remote -v
```

Fetch all of the branches from the repository. This also downloads all of the required commits and files from the other repository:

```zsh
git fetch
```

Same as the above command, but only fetch the specified branch:

```zsh
git fetch <remote> <branch>
```