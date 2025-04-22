## 🚀Once file is staged but not commited and  you deleted that file then still you can restore via git restore file-name
## 🚀 once file is commited and you deleted that will show in git status output and can be restored once then will not show under any untracked list means came back to tracked list

![image](https://github.com/user-attachments/assets/a755d985-05ad-4d74-80af-758d6967ddc2)

## 🚀 to see how many files as of now tracked in git

- ubuntu@ip-172-31-25-24:~/git_practice_folder$ **git ls-files**
   - a.txt


#######################################################
- when you create one folder and make repository . after commit you wont seee anuthing in git status so actually where those file went. when you create repo it create hidden folder .git
  so those file saved under .git/objects folder as objects. basiclly those files are saved as compressed hash file using sha-1 not like notmal file. basiclly those are saved as compressed data blob(binary logical objects 
  :internal objects in git). so when u delete and restore git unzip and store from here only.

- when you create the branch those are stored as files under .git/refs/heads


###########################################

- Lets say on GitHub we have multiple repository like Git_1, Git_2, Git_3 and so on and on local repository we have git_practice_folder if I want to send file from local to remote repository how it will be differentiated 
  that I am sending that to Git_1, or Git_2, or Git_3 remote repository. so you have to add them on local

   ## Add GitHub repository Git_1
   - git remote add origin https://github.com/your-username/Git_1.git >>>>>>here origin is default so giving to first remote repository. if you adding first time only one remote repo so we give that 

   ## Add second remote
   - git remote add git2 https://github.com/your-username/Git_2.git

   ## Add third remote
   - git remote add git3 https://github.com/your-username/Git_3.git
 
![image](https://github.com/user-attachments/assets/f746e9af-b573-45d9-93b7-5567719b581d)

## git push origin master >>>>this will send local master branch to git1 because origin is corresponding to git 1

## git push git2 master >>>> this will send local master branch to remote git2 repo 

## git push git3 master >>>this will send local master branch to remote git3 repo 



################################################

- lets consider I have local rep git_practice_folder which has branch master , dev, sbc, and cucm , total 4 branch. and remote repo Git_1 having branch master, feature-1, feature-2
  consider below push scenario:
  - local master branch to remote master, feature-1, feature-2
  - local dev branch to remote master, feature-1, feature-2

![image](https://github.com/user-attachments/assets/36cc84e8-064c-411b-813c-9e250eaf9fa7)

