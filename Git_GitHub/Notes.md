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


- so here you are adding https link of remote repository not the ssh link if you want you can add ssh link as well if you have private and public key. so its not like you can add only https link you can add ssh
   link as well if you want and have private-public key

## git push origin master >>>>this will send local master branch to git1 because origin is corresponding to git 1

## git push git2 master >>>> this will send local master branch to remote git2 repo 

## git push git3 master >>>this will send local master branch to remote git3 repo 



################################################

- lets consider I have local rep git_practice_folder which has branch master , dev, sbc, and cucm , total 4 branch. and remote repo Git_1 having branch master, feature-1, feature-2
  consider below push scenario:
  - local master branch to remote master, feature-1, feature-2
  - local dev branch to remote master, feature-1, feature-2

![image](https://github.com/user-attachments/assets/36cc84e8-064c-411b-813c-9e250eaf9fa7)


- likewise you can switch to dev branch and you use above command to send files in desired remote branch

 - ## Push local dev to remote master
   - git push origin dev:master

-  ## Push local dev to remote feature-1
   - git push origin dev:feature-1

-  ## Push local dev to remote feature-2
   - git push origin dev:feature-2
 

Lets say if you just giving the 
  - git push origin dev  >>>>>>>“Push the local branch dev to the remote origin( ie: Git_1 because it added as origin), and create (or update) a branch named dev there.” means if there are already dev branch on origin Git_1
    then it will push under that if not then git will create branch of same name dev and push uder that. so it means  git also sets an upstream tracking relationship: Local dev ↔ origin/dev and so on.
    so in short:
    
    ## git push       # Git knows to push local dev → origin/dev
    ## git pull       # Git knows pulls from origin/dev into local dev



# 😵When you created some repository in local and also have some repository on remote  and each having some commit so facing issue when doing first time push on remote
 - ## lets say in my local repository I did three commit A, B, C on 22 April at 10 am 11 am 12 PM IST and in remote repository git_1 dit commit D at 7 PM IST and in git_2 did commit E at 10 PM IST on same day now explain 
      w.r.t

  ![image](https://github.com/user-attachments/assets/2a7e4593-5dac-4e72-ab27-ce95c6e1c384)

  ![image](https://github.com/user-attachments/assets/7d41e614-4d43-449a-8eee-c0194d6c5069)

  - ## SOLUTION

    ![image](https://github.com/user-attachments/assets/536d12c8-d221-44ee-8d98-dfa44d6a74a7)

    ![image](https://github.com/user-attachments/assets/b5645115-7a8d-4baf-ac4b-ae4f2db5b6af)

    ![image](https://github.com/user-attachments/assets/6b82baf7-8e87-4d29-a157-ffd48b897f74)

    ![image](https://github.com/user-attachments/assets/2d7a8a96-d052-42c7-9ab9-c76342ecec58)

    ![image](https://github.com/user-attachments/assets/8ef0c590-61e7-429d-88d1-321c679bf40a)




so depending on your situation once you added those thing then do pull git pull origin master/or branch name 


- ## 💭 you can clone anywhere its not necessary that folder should be repository

  


   
