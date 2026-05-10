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

## Either login to `github UI` or use `gh` to login

<img width="1652" height="523" alt="Question-1 6" src="https://github.com/user-attachments/assets/66a07530-d4d1-4447-8010-2812c26a7bad" />

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






