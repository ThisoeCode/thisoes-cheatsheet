# [PINNED]
```bat
git commit -am "[0.1.8.16] "

git checkout app-route
git reset --hard main
git commit --amend -m "0.2.1"
git push origin app-route --force

git log --oneline
```



# Maven
### clean hook
```bat
./mvnw clean
./mvnw clean <default-phases>
```

### [default]
```bat
./mvnw compile
./mvnw clean test
./mvnw clean package
./mvnw clean verify
```

### something like `npm run dev` on `localhost8080`
```bat
./mvnw spring-boot:run
```



# npm
### NextJS preview & test on `localhost:3000`
```bat
npm run dev

npm run build
npm run start
```

### Modify version **_after committed_**
```bat
npm version 0.1.7
```



# Git
### Initialize / Create a repo
```bat
git init
git add .
git commit -am "[0.0.0] "
git remote add origin <https://github.com/ThisoeCode/REPO.git>
git push -u origin main
```

### Use previous commit to create branch
```bat
git checkout -b new_branch_name commit_hash
```

### Create empty orphan branch
```bat
git checkout --orphan new_branch_name
git rm -rf .
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

### Force push & push all
```bat
git push --force origin <branch-name>
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

### ...







