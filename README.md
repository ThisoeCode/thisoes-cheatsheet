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
1. clean hook
```bat
./mvnw clean
./mvnw clean <default-phases>
```

2. default ()
```bat
./mvnw compile
./mvnw clean test
./mvnw clean package
./mvnw clean verify
```

3. something like `npm run dev`
./mvnw spring-boot:run




# npm
1. NextJS run dev on http://localhost:3000
```bat
npm run dev

npm run build
npm run start
```

2. Modify version **after committed**
```bat
npm version 0.1.7
```



# git
1. Initialize / Create a repo
```bat
git init
git add .
git commit -am "[0.0.0] "
git remote add origin https://github.com/ThisoeCode/springboot-tut_following-devtiro.git
git push -u origin main
```

2. Use previous commit to create branch
```bat
git checkout -b new_branch_name commit_hash
```

3. Create empty orphan branch
```bat
git checkout --orphan new_branch_name
git rm -rf .
```

4. Merge from <branch-name> to "main" branch
```bat
git checkout main
git merge <branch-name>
git checkout app-router
```

5. Modify the comment message of last commit
```bat
git commit --amend -m "New message"
```

7. List all branch names / List all remote names
```bat
git branch -a
git remote
```

8. Delete branch
```bat
git branch -d <branch-name>
git push origin --delete <branch-name>
```

10. Find (and switch to) which branch a commit is on using its hash
```bat
git branch --contains <commit-hash>
```

11. Force push & push all
```bat
git push --force origin <branch-name>
git push --all
```

14. Commit current status in a new branch `temp` and recover `main` branch
```bat
git checkout -b temp
git add .
git commit -m "Temporary commit before reverting errors"
git checkout main
git reset --hard HEAD
:: git push origin temp
```

15. Go back to previous commit
```bat
git reset <hash> --hard
git reset bc5ca7 --hard
```

16. Move `file.txt` from sub-branch to `main` branch (CAUTION: overwrite)
```bat
git checkout <branch-name> -- <file.txt>
```










