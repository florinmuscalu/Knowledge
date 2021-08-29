- ## [Configuration](#config)
- ## [Create a project](#createproject)
- ## [Creating commits]($createcommit)
- ## [Collaborate](#collab)
- ## [Verifying commits](#verify)
- ## [Branching](#branch)
- ## [Moving commits](#move)
- ## [Rewriting history](#rewrite)
- ## [Getting out of risky situations](#risky)

<br><br><br>

## <a name="config"></a>Configuration
- Configure the name to be included in your commits:
```bash
$ git config --global user.name "Your Name"
```
- Configure the email to be included in your commits:
```bash
$ git config --global user.email "you@mail.com"
```
- Enable colorized output (for status, diff, log, ...):
```bash
$ git config --global color.ui auto
```
- Configure your default editor:
```bash
$ git config --global core.editor vim
```
- Configure merge tool for solving merge conflicts:
```bash
$ git config --global merge.tool meld
```
- Configure the diff tool for viewing diffs:
```bash
$ git config --global diff.tool meld
```
## <a name="createproject"></a>Create a project
- Create a new, local repository:
```bash
$ git init [project]
```
- Clone an existing repository, including history, and have a default remote repository named **origin** set:
```bash
$ git clone [repo url]
```
## <a name="createcommit"></a>Creating commits
- Stage files for the next commit
```bash
$ git add <file | directory>
```
- Stage some hunks in <file>. Use ? to get around:
```bash
$ git add -p <file>
```
- Create a new commit from all files currently staged. If no -m flag is passed, it will open your configured editor:
```bash
$ git commit [-m "Commit message"]
```
- View unstaged changes between index and working directory:
```bash
$ git diff
```
- View staged changes between index and last commit:
```bash
$ git diff -cached
```
## <a name="collab"></a>Collaborate
- Verify all currently configured remote repositories:
```bash
$ git remote -v
```
- Add a new remote repository
```bash
$ git remote add <shortname> <url>
```
- Download changes from a remote (but do not merge them into HEAD):
```bash
$ git fetch <remote>
```
- Download changes from a remote, and rebase your commits on top of remote
```bash
$ git pull -rebase
```
- Publish your changes on a remote:
```bash
$ git push <remote> <branch>
```
## <a name="verify"></a>Verifying commits:
- Display overall status of the repository:
```bash
$ git status
```
- Show the commits made in a repository, starting from the most recent:
```bash
$ git log [--all] [--graph] [--oneline] [--decorate]
```
- Print various information about supplied objects (commits, trees, blobs):
```bash
$ git show <objects>
```
- Temporarily reset all files in a repository to their state of time of a specific commit:
```bash
$ git checkout <branch | tag | commit-id>
```
- Verify who modified each line in a specified file:
```bash
$ git blame <file>
```
## <a name="branch"></a>Branching
- Display all local branches in a repository, along with their upstream remotes:
```bash
$ git branch -vv
```
- Create a new branch, pointing at the current HEAD:
```bash
$ git branch [name]
```
- Merge specified branch(es) onto the current HEAD:
```bash
$ git merge [source-branch]
```
- Delete specified branch label, only if it is already merged into any other branch:
```bash
$ git branch -d [branch]
```
- Apply changes introduced by a specified commit onto the current HEAD:
```bash
$ git cherry-pick [commit-id]
```
- Mark the current commit with a tag:
```bash
$ git tag <tag-name>
```
## <a name="move"></a>Moving commits
## <a name="rewrite"></a>Rewriting history
## <a name="risky"></a>Getting out of risky situations 