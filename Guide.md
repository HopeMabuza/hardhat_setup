
# 📁 Guide: Managing Projects in ABC/Hope_Mabuza

## 🧠 Structure

```bash
ABC/
└── Hope_Mabuza/      # main git repo
    ├── README.md
    ├── Voting_System/
    ├── Escrow/
    └── Other_Project/


### Important Rules

* `Hope_Mabuza` is the **ONLY git repo**
* Projects inside are just **folders**
* ❌ NO `.git` inside project folders

---

# 🚀 Part 1: Adding a New Project

## Example

You have:

```bash
~/Documents/Blockchain-Elective/ABC/New_Project
```

You want it inside:

```bash
~/Documents/Blockchain-Elective/ABC/Hope_Mabuza/New_Project
```

## Steps

```bash
cd ~/Documents/Blockchain-Elective/ABC/Hope_Mabuza
mkdir New_Project
```

Copy project (exclude `.git`):

```bash
rsync -av --exclude='.git' ~/Documents/Blockchain-Elective/ABC/New_Project/ ~/Documents/Blockchain-Elective/ABC/Hope_Mabuza/New_Project/
```

Check:

```bash
ls -a New_Project
```

👉 Make sure `.git` is NOT there

Commit:

```bash
git add .
git commit -m "Add New_Project"
git push origin main
```

---

# 🔄 Part 2: Updating an Existing Project

## Example

Update:

```bash
~/Documents/Blockchain-Elective/ABC/Voting_System
```

Into:

```bash
~/Documents/Blockchain-Elective/ABC/Hope_Mabuza/Voting_System
```

## Steps

```bash
cd ~/Documents/Blockchain-Elective/ABC/Hope_Mabuza
```

Copy updated files:

```bash
rsync -av --exclude='.git' ~/Documents/Blockchain-Elective/ABC/Voting_System/ ~/Documents/Blockchain-Elective/ABC/Hope_Mabuza/Voting_System/
```

Check:

```bash
ls -a Voting_System
```

Commit:

```bash
git status
git add .
git commit -m "Update Voting_System"
git push origin main
```

---

# ✏️ Part 3: Updating Directly Inside Repo

If you edit files inside:

```bash
Hope_Mabuza/Voting_System
```

Then:

```bash
cd ~/Documents/Blockchain-Elective/ABC/Hope_Mabuza
git status
git add .
git commit -m "Update project"
git push origin main
```

---

# ⚠️ Part 4: Important Rules

## ❌ Never do this inside project folders

```bash
git init
```

## ❌ Never copy `.git`

Always use:

```bash
rsync -av --exclude='.git' source/ destination/
```

## ⚠️ If you see this error:

```bash
warning: adding embedded git repository
```

Fix it:

```bash
rm -rf Project_Name/.git
git rm --cached -r -f Project_Name
git add .
```

---

# 📦 Part 5: Recommended `.gitignore`

```gitignore
node_modules/
artifacts/
cache/
.env
dist/
coverage/
```

---

# ⚡ Part 6: Quick Commands Cheat Sheet

## Add new project

```bash
mkdir New_Project
rsync -av --exclude='.git' source/ New_Project/
git add .
git commit -m "Add New_Project"
git push origin main
```

## Update project

```bash
rsync -av --exclude='.git' source/ Project_Name/
git add .
git commit -m "Update Project_Name"
git push origin main
```

## Normal workflow

```bash
git status
git add .
git commit -m "Update"
git push origin main
```

---

# 🧯 Part 7: If Push is Rejected

```bash
git pull origin main --allow-unrelated-histories --no-rebase
git push origin main
```

If conflict:

```bash
git status
# fix files manually
git add .
git commit -m "Resolve conflict"
git push origin main
```

---

# ✅ Best Workflow

* Work on project outside repo
* Copy using `rsync`
* Commit from `Hope_Mabuza`

---

# 🎯 Summary

* One repo → `Hope_Mabuza`
* Many projects → folders
* Never nest git repos
* Always exclude `.git`

---

````

---

# ✅ How to use it

1. Inside your repo:
```bash
cd ~/Documents/Blockchain-Elective/ABC/Hope_Mabuza
````

2. Create the file:

```bash
nano GUIDE.md
```

3. Paste everything → save (`Ctrl + O`, `Enter`, `Ctrl + X`)

4. Push it:

```bash
git add GUIDE.md
git commit -m "Add project management guide"
git push origin main
```

---

