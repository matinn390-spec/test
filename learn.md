# GIT 
    - is a verison control system.
    - tracking file changes
    - move between versions of our codes.

---

# Initialize
    - git init
    
---

# Add a file to git (satge for commit)
    - git add . 


# Status 
    - git status 

# Commit 
    - git commit -m 'this is first text'


# log - commit lists 
    - git log 

# get back to another commit
    - git checkout <hash>

# get back to last verison
    - git checkout master

# Branch 
    - git branch <name>
    - git branch # branch lists
    - git checkout <name>
        - add new changes.
        - git add .
        - git commit -m ''
    - git chechout master 
        - changes on another branch is not here :)
    
# Merger changes :)
    - git checkout master
    - git merge <another_branch_name>

# Merge Confilict 
    - one place modify on both branch, then merge togather => confilict.

    - select current or incoming 
    - git add .
    - git commit -m 'resolve confilict...'

# Delete Branch 
    - git branch -d <name>

-------------


# github / gitlab - work on specific project :)

    - git remote add origin https://github.com/matinn390-spec/test.git
    - git branch -M main (master to main)
    - git push -u origin main


# push another modifications to remote server 
    - git push origin main

# github pull request 
    - request to owner of project for merge branch to main branch.

# git pull - command
    - last changes from remote server to local. 

==========================================================
PR = "Please review my changes before they go into main."
Local merge = "I trust myself, merging directly."
==========================================================


# Clone 
    - git clone https://...
    - clone specific branch: git clone -b dev https://github.com/user/project.git

# Difference
    - see what changes between your changes and last commit 
    - git diff                 # unstaged changes (working dir vs staged)
    - git diff --staged        # staged changes (what's about to be committed)
    - git diff main dev        # difference between two branches
    - git diff HEAD~1          # what changed since last commit

# Stash 
    git stash          # کارهای نیمه‌کاره رو می‌ذاره کنار
    git checkout main  # برو باگ رو درست کن
    # ... باگ رو درست می‌کنی و commit می‌کنی ...
    git checkout feature-branch
    git stash pop      # کارهای نیمه‌کاره برمی‌گرده سر جاش
    git stash list
    git stash apply #  برمی‌گردونه ولی توی لیست می‌مونه.

# Reset 
    - we commit some changes. 
    - but wrong commit and we need changes be stay. just commit back.

    - git log --oneline
    - git reset HEAD~1  # یه commit به عقب، ولی تغییرات می‌مونه
    
    - git reset --soft HEAD~1         # commit=remove, staging=stay, files=stay
    - git reset --mixed HEAD~1        # commit=remove, staging=remove, files=stay
    - git reset --hard HEAD~1         # commit=remove, staging=remove, files=remove


# Revert 
    - push commit to server => commit have bug.
    - reset => change teammate commit history
    - revert help us.

        commit A : hello
        commit B : how are you? 
        commit C : Bye 
        git revert B 
        commit D : hello, Bye

    - git log --oneline
    - git revert a1b2c3d


# gitignore
    - tell git to do not track these files!

# When to commit? 
    - after create or midify a functionality. 

# What write in commit message? 
    - add - something
    - delete - something
    - modify - something
    - fix  - something

# Branch name 
    - based on feature.
    - loginPage -> for login page codes. 

# GIT Flow
    - main branch 
        - dev branch (all codes here)
            - branch loginPage
            - branch product
            - branch SearchBar
        - merge to dev
    - merge to main

    - applicaiton in production but have a bug. 
        - we can not wait to dev is compelete, then create new branch.
        - on main => hot-fix branch => fix code => merge with main .

