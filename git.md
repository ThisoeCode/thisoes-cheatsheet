# Git
*******

## [PINNED]
```bat
git commit -am "[0.1.1] "

git log --oneline

```

## Initialize / Create a repo
```bat
git init
git add .
git commit -am "init"

git remote add origin <https://github.com/ThisoeCode/REPO.git>

:: if LICENSE or README was added on GitHub repo creation
git pull origin main --allow-unrelated-histories

git push -u origin main
```



*******



### Use previous commit to create branch
```bat
git checkout -b new_branch_name commit_hash
```

### Create an empty orphan branch
(Old way)
```bat
git checkout --orphan new_branch_name
git rm -rf .
```
([New way](https://stackoverflow.com/a/34100189/23120980))
```bat
git switch --orphan <branchname>
git commit --allow-empty -m "Initial commit on orphan branch"
git push -u origin <branchname>
```

### Merge from <branch-name> to "main" branch
```bat
git checkout main
git merge <branch-name>
git checkout app-router
```

### Modify the comment message of last commit
```bat
git commit --amend -m "New message"
```

### List all branch names / List all remote names
```bat
git branch -a
git remote
```

### Delete branch
```bat
git branch -d <branch-name>
git push origin --delete <branch-name>
```

### Find (and switch to) which branch a commit is on using its hash
```bat
git branch --contains <commit-hash>
```

### Force push
```bat
git push --force origin <branch-name>
```

### See status of all branches & Push all
```bat
git branch -vv
git status -sb
git push --all
```

### Commit current status in a new branch `temp` and recover `main` branch
```bat
git checkout -b temp
git add .
git commit -m "Temporary commit before reverting errors"
git checkout main
git reset --hard HEAD
:: git push origin temp
```

### Go back to previous commit
See a [safer way](#revert-as-a-new-commit)
```bat
git reset <hash> --hard
git reset bc5ca7 --hard
```

### Move `file.txt` from sub-branch to `main` branch (CAUTION: overwrite)
```bat
git checkout <branch-name> -- <file.txt>
```

### After changing the repo name on GitHub, change local Git repo's remote URL

  1. check the current remote URL
  ```bat
  git remote -v
  ```

  2. change URL
  ```bat
  git remote set-url origin <https://github.com/ThisoeCode/NEW-REMOTE-URL.git>
  ```

### Revert (as a new commit)
```bat
git log --oneline

git revert --no-commit a1b2c3d..HEAD
git commit -m ""
```

### Unstage: Remove staged file / entire folder
```bat
git rm --cached <file_name>
git rm -r --cached <folder_name>
```

### ...


