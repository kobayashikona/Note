# Basic Commands

## Get Git Repository

### Initialize the Repository in Existing Directory

```
$ git init
```

### Clone an Existing Repository

```
$ git clone https://github.com/kobayashikona/Note.git
```

You can add the name you want to named that repository behind the command above so as to named it.

### Personal Access Token

Click your avatar on github and select options as below:

Settings -> Develpoer settings -> Personal Access Tokens -> Generate new token

Then choose expiration and scopes as you need and click "Generate token".

Copy the token and type
```
git remote set-url origin  https://<your_token>@github.com/<USERNAME>/<REPO>.git
```

After that, you can use `git pull` just like before.

Similarly, when you need to clone repository, you can type
```
git clone https://<TOKEN>@github.com/<user_name>/<repo_name>.git
``` 

## Record Each Submit in Repository

### Check Status of Files

```
$ git status
```

### Tracing New Files or Staging Modefied Files

```
$ git add newfile
```

The newfile here can be a folder which isn't empty.

### Check the Change

```
$ git diff
```

### Submit an Update

```
$ git commit -m "here is remark you want to add"
```

## Branch

### List All Branches

```
$ git branch
```

### Create a Branch

```
$ git branch branchname
```

### Switch to Another Branch

```
$ git checkout branchname
```

### Merge

```
$ git merge newbranch
```
It will merge the branch "newbranch" to the current branch you exist, so you need to switch to master branch before you merge them.

### Delete a Branch
```
$ git branch -d newbranch
```

## Remote Repository

### Upload Remote Code and Merge

```
$ git push <remote_host> <local_branch>:<remote branch>
```

### Download Remote Code and Merge
- Clone remote repository to local
```
$ git clone url
```
- Pull the specified branch of the remote host and merge it with specified local branch.
```
$ git pull <remote_host> <remote branch>:<local_branch>
```
- Use fetch to update local repository.
```
$ git fetch origin master:temp           #Download from the master branch of the remote origin repository to the local and create a new branch temp
$ git diff temp                          #Compare the difference between master branch and temp branch
$ git merge temp                         #Merge temp branch to master branch
$ git branch -d temp                     #Delete temp
```

## Submit Code

Assume you write code in a new branch.

1. check status：`git status`
2. add to staging area：`git add filename`
3. submit with comments：`git commit -m “your code comments”`
4. switch to master branch：`git checkout master`
5. merge branchs：`git merge branchname`
6. sync remote repository：`git push`