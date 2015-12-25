# 
HeadHunterSchool homework: 1. Git, task #1
---------

##### 01. create repo (repo A)
```
git clone https://github.com/Iskuskov/hh_git_1_repoA.git
```

##### 02. repo A: create 1st commit with some files (file A, file B)
```
cd hh_git_1_repoA/
echo "line1 in file A" > file_A.txt
echo "line1 in file B" > file_B.txt
git add .
git commit -m "First commit"
```

##### 03. repo A: create branch branch1 from master
```
git branch branch1
```

##### 04. clone the current repo (repo B)
```
cd ..
git clone hh_git_1_repoA hh_git_1_repoB
```

##### 05. repo B, branch1: create 2nd commit containing new file (file C)
```
cd hh_git_1_repoB
git checkout branch1
echo "line1 in file C" > file_C.txt
git add file_C.txt
git commit -m "Second commit"
```

##### 06. repo B: push changes to repo A
```
git push origin branch1
```

##### 07. repo A, branch1: modify line#1 in file C and commit
```
cd ../hh_git_1_repoA
git checkout branch1
echo "line1 in file C (modified in repo A)" > file_C.txt
git commit -am "Modified file C in repo A"
```

##### 08. repo B, branch1: modify line#1 in file C and commit
```
cd ../hh_git_1_repoB
echo "line1 in file C (modified in repo B)" > file_C.txt
git commit -am "Modified file C in repo B"
```

##### 09. repo B, branch1: fetch changes from repo A
```
git fetch origin
```

##### 10. repo B, branch1: merge in repoA's branch1 (resolve conflict)
```
git merge origin/branch1
echo "line1 in file C (resolved conflict)" > file_C.txt
git commit -am "Merge: resolved conflict in file C"
```

##### 11. repo A: add repoB as new remote
```
cd ../hh_git_1_repoA
git remote add hh_git_1_repoB ../hh_git_1_repoB
```

##### 12. repo A, branch1: merge in repoB's branch1
```
git pull hh_git_1_repoB branch1
```

##### Push repo A
```
git push origin --all
```

##### Push repo B
```
cd ../hh_git_1_repoB
git remote add github https://github.com/Iskuskov/hh_git_1_repoB.git
git push github --all
```
