# First login with Credentials and verify the same:
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

```bash
git config --global --list
```

### Explanation
- `git config` --global sets your Git identity for all repositories on your machine.
- `user.name` is the name attached to commits.
- `user.email` is the email attached to commits.

# Question 1: Project Initialization & First Push

## - Create a new folder for your project

- First Create a directory

```bash
mkdir python-git-assessment
```

- Then go inside the directory

```bash
cd python-git-assessment
```

- Use the `ls -a` command to verify the contents of the directory.
- The `.git` folder will not appear because the repository has not been initialized yet.
- Initialize the repository by running the `git init` command as shown below:
  <br></br>
<img width="1533" height="622" alt="Question-1 2" src="https://github.com/user-attachments/assets/25fd8ea4-4df5-4b67-8266-5af4d097a5a8" />
<br></br>

- Without this, Git will not know your folder is a version-controlled project.
- From here `Git` starts tracking changes in this project


## Create app.py and add Python code

- echo prints the text `>` writes that text into a file `app.py`.
- If app.py does not exist, it gets created
- use `python3 app.py` to run the code
- Run `git status` to show the current state of the repository. It tells which files are untracked, modified, or staged
> 
```bash
echo 'print("Hello, Git and GitHub!")' > app.py
python3 app.py
git status
```

<img width="1533" height="467" alt="Question-1 3" src="https://github.com/user-attachments/assets/aa4009c7-8141-4d60-8f62-b94dd0543f67" />
<br></br>


## Stage the file and check the status

```bash
git add app.py
git status
```
<img width="1010" height="372" alt="Question-1 4" src="https://github.com/user-attachments/assets/233d9015-c2ba-4a00-aca5-ea0af2318913" />
<br></br>

- `git add` moves changes into the staging area.


## Commit with a meaningful message
- `git commit` saves a snapshot of your staged changes
- `-m` lets you write the commit message directly in the command

<img width="1428" height="189" alt="Question-1 5" src="https://github.com/user-attachments/assets/a8ddaa2e-3f67-4036-a3e1-21ea4a714ce6" />
<br></br>

## Either login to `github UI` or use `gh` to login

<img width="1652" height="523" alt="Question-1 6" src="https://github.com/user-attachments/assets/66a07530-d4d1-4447-8010-2812c26a7bad" />
<br></br>

## Create a remote repository on GitHub and then adde the remote repository as `origin`
- Using GitHub CLI
  - `gh` is the GitHub CLI
  - Here `repo create` creates a repository on GitHub
  - `--public` makes it public acces
```bash
gh repo create python-git-assessment --public
```

- Add the remote repository as origin
  - `git remote add` connects your local repo to a remote repo
  - `origin` is the common default name for the main remote
  - The URL is your GitHub repository URL
```bash
git remote add origin https://github.com/<your-github-username>/python-git-assessment.git
```

## Verify the remote configuration
- This confirms Git is linked to the correct GitHub repository.
```bash
git remote -v
```

- Rename branch to main because most GitHub repos use `main` as the default branch instread of `master`.
```bash
git branch -M main
```

<img width="1113" height="206" alt="Question-1 9" src="https://github.com/user-attachments/assets/49946fba-8ed5-4b11-a42b-04fcf1c20817" />
<br></br>

## Push code to GitHub
- This uploads your local code to GitHub.
```bash
git push -u origin main
```
- `git push` sends local commits to the remote repository
- `-u` sets upstream tracking
- `origin` is the remote name
- `main` is the branch name

<img width="1131" height="256" alt="Question-1 10" src="https://github.com/user-attachments/assets/e277ce8c-9a6a-4796-9ee3-a18e53635b4f" />
<br></br>



# Question 2: Working with Changes & History
## Modify `app.py` by adding new functionality
```bash
echo 'def greet(name):
    return f"Hello, {name}!"
' >> app.py
```


## Check what changes were made before staging

<img width="1153" height="367" alt="Question-2 1" src="https://github.com/user-attachments/assets/a0332396-0ef0-4e64-949b-1ce4c6e1f8a4" />
<br></br>

## View differences in the file `git diff`
- Shows line-by-line changes
- Lines with + are additions
- Lines with - are removals  

<img width="901" height="425" alt="Question-2 2" src="https://github.com/user-attachments/assets/2728637c-44ca-4525-9581-3e2cd07646bd" />
<br></br>

## Stage only specific changes `-p` means patch mode
- This is useful when you changed many things but only want to commit some of them.
```bash
git add -p
```
<img width="920" height="783" alt="Question-2 3" src="https://github.com/user-attachments/assets/6253ccf0-5e67-4007-896a-ec85d2be1cc3" />
<br></br>

##  Commit with a clear message
```bash
git commit -m "Add greet function"
```


## Make another change in `app.py` and stage all the changes
```bash
echo 'print(greet("Mithilesh"))' >> app.py
```
```bash
git add .
```


## Commit again
```bash
git commit -m "Call greet function in app"
```
<img width="1042" height="179" alt="Question-2 5" src="https://github.com/user-attachments/assets/8346217d-8057-48ab-b79a-90c36eede7a9" />
<br></br>

# Question 3: Branching & Feature Development
## Create a new branch
```bash
git branch feature-update
```
<img width="1158" height="174" alt="Question-3 1" src="https://github.com/user-attachments/assets/916fe5d8-dd66-4283-a25f-878a6f0e76ef" />
<br></br>

## Switch to the new branch
```bash
git checkout feature-update
```
<img width="1207" height="200" alt="Question-3 2" src="https://github.com/user-attachments/assets/727f23e7-bd3f-48a0-bbe7-8e74c250a4e0" />
<br></br>

## Modify `app.py` with new feature logic stage and commit the changes
```bash
echo 'def add(a, b):
    return a + b
' >> app.py

git add app.py
git commit -m "Add add function on feature branch"
```

<img width="1087" height="209" alt="Question-3 4" src="https://github.com/user-attachments/assets/05dea4d3-b038-49da-8cbb-508e94313163" />
<br></br>

## Switch back to the main branch and Merge the feature branch into main
- This will bring the commits from feature-update into main.
```bash
git checkout main
git merge feature-update
```
<img width="1128" height="778" alt="Question-3 5" src="https://github.com/user-attachments/assets/d725ecf7-3792-4aa2-8c9b-672a6e08159d" />
<br></br>

## Delete the branch safely
```bash
git branch -d feature-update
```

<img width="1214" height="176" alt="Question-3 6" src="https://github.com/user-attachments/assets/2154ba2e-5db1-4faf-b988-8372bdeb6374" />
<br></br>

# Question 4: Handling Errors (Stash, Reset, Revert)
## Make changes to app.py but do not commit and also create new untracked file `notes.txt`
```bash
echo 'temp_var = "work in progress"
' >> app.py

touch notes.txt
```


##  Stash the changes including untracked files
```bash
git stash push -u -m "WIP changes"
```

<img width="1299" height="293" alt="Question-4 2" src="https://github.com/user-attachments/assets/a25986fe-d3c8-4851-a35d-f2bd238c0487" />
<br></br>

## Check the stash list by running following command:
```bash
git stash list
```

<img width="979" height="108" alt="Question-4 3" src="https://github.com/user-attachments/assets/3c1a36f2-6b5b-48ae-9444-5f83fe601bbb" />
<br></br>

## Apply the stashed changes back
- Restores the most recent stash into your working directory.
```bash
git stash apply
```


## Commit the restored changes
```bash
git add .
git commit -m "Restore stashed work"
```


## Make another commit with incorrect code
```bash
echo 'def broken():
    return 1 / 0
' >> app.py
```
```bash
git add app.py
git commit -m "Add incorrect code"
```


## Undo the last commit using reset
- We can use this when the commit was wrong but you want to keep the code for editing/recommitting.
```bash
git reset --soft HEAD~1
```
- `git reset` moves the current branch backward
- `--soft` removes the commit but keeps the changes staged
- `HEAD~1` means “go back one commit”


## Make another commit
```bash
git commit -m "Add another change after reset"
```

<img width="1332" height="449" alt="Question-4 5" src="https://github.com/user-attachments/assets/5ec7c44f-9d13-4ee4-8c5a-374c2050df20" />
<br></br>

## Make one more commit to revert
```bash
echo 'def another_feature():
    return "ok"
' >> app.py
```
```bash
git add app.py
git commit -m "Add another feature"
```

<img width="1042" height="302" alt="Question-4 7" src="https://github.com/user-attachments/assets/7b09741c-f0ba-4ab5-bc7e-7ae1a18182f3" />
<br></br>

##  Undo a commit using revert and Verify the commit history
```bash
git revert HEAD
```
<img width="1113" height="388" alt="Question-4 8" src="https://github.com/user-attachments/assets/388fa4ab-72e9-46f1-a70e-58943fcc0556" />
<br></br>
