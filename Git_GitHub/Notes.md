## 🚀Once file is staged but not commited and  you deleted that file then still you can restore via git restore file-name
## 🚀 once file is commited and you deleted that will show in git status output and can be restored once then will not show under any untracked list means came back to tracked list

![image](https://github.com/user-attachments/assets/a755d985-05ad-4d74-80af-758d6967ddc2)

## 🚀 to see how many files as of now tracked in git

- ubuntu@ip-172-31-25-24:~/git_practice_folder$ **git ls-files**
   - a.txt


#######################################################
## when you create one folder and make repository . after commit you wont seee anuthing in git status so actually where those file went. when you create repo it create hidden folder .git
so those file saved under .git/objects folder as objects. basiclly those files are saved as compressed hash file using sha-1 not like notmal file. basiclly those are saved as compressed data blob(binary logical objects :internal objects in git)

## when you create the branch those are stored as files under .git/refs/heads




