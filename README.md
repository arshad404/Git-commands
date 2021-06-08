# Git All You Need✨

### 1. Creation of repo and pushing your "Hello world" there

###### When you wants to create a repo and push your code:

1. Create a repository on github and attach a readme file which contains the information about the project.
2. Then clone the repository on your local desktop and do changes as you want.
3. To check the changes in the repository, check the changes by using command: - [ git status ]
4. After changes, to push the updated code you need to follow few steps: 
	- [ git add . ] (To add all the file that you changed, after using the command your code is still on your computer, you code is in staging area) 
	- [ git add `file_name` ] (To add the only file that you want to add)
	- [ git commit -m "message regarding this commit" ] (code is still on your computer, but in the version database)
	- [ git push ] (Now your code has been pushed on the cloud and you can see the changes on your github profile)
5. If you commit something and don't know what is commited then we will use [ git log ] command to check the commited file.

### 2. Undoing Reverting Resetting

###### a. Undo uncommited changes [ git checkout -- ]

1. If you change something wrong and want to remove those changes from your local computer the use [ git checkout -- file_name.extension ]

2. And if there are multiple files to undo the change then we can use the command [ git checkout -- . ] this will undo all the file changes on your local computer.

###### b. Undo commited changes [ git revert ]

If you want to undo the commited code then you need the commit id which you get from the [ git log ] command.

1. After getting the commit id we will use command [ git revert commit_id ] and [ :q ] to close the ui. Finally the commit is deleted and it directly undo the commit.

2. If you want to undo the commit explicitely then you need to type [ git revert -n commit_id ] and finally commit the changes using [ git commit -m 'your comment' ] and you are done.

###### c. Resetting changes [ git reset ]

Now you realise that the changes you commited are wrong or the commits that you undo are wrong and want the code as before as it was then you need to copy the commit id from where you want to reset all the changes and follow the command [ git reset --hard commit_id ]. 

### 3. Branches

What is the use of branches, why we use this?
Suppose you want to do some experiment with your file then what we generally do is just make a duplicate copy of the file in which you want to make changes, so this can also be done on the cloud by the help of branches in git.

1. To check the branches on your repository use the command [ git branch ]

2. The default branch is master branch, and the active branch is represented by the star in front of the branch.

3. To create a new branch use the command [ git branch new_branch_name ]

4. To switch from the current branch to the new_branch we use the command [ git checkout new_branch ]

5. Now add that particular file which you want to change by using command [ git add filename ] and [ git commit -m 'comment' ]

6. Now you have two separate branches in which you can edit the changes as you want.

7. Supppose you are done and want to MERGE the changes in the desired_branch then make sure you are in the that branch and if you are not then use the command [ git checkout branch_name ] and then you have to pull [ git pull ] your code before final push [ git push ] of the code.

8. Now your code has been pushed but your branch is not shown on the github because you still not pushed the branch. So, to push the branch you need to switch on that branch [ git checkout branch_name ] and then [ git push ] in the description of the git push command there must be a command which you have to copy and paste in the terminal to push that branch.

9. To create a new active branch we use the command [ git commit -b branch_name ]

10. Now if you want to DELETE the branch then first checkout your master branch then use the command [ git branch -d branch_name ]

### 4. Head

1. Head is the reference to the most recent commit in the current branch. When you do [ git log ] then the first commit you see in the list is reference by the HEAD. It works like a linked list in which head is reference as the initial added commit.

2. If you want to see the initial commit then use the command [ git show HEAD ] and suppose you want to see the second last commit then use the command [ git show HEAD~1 ] and third last by using [ git show HEAD~2 ]

### 4- .gitignore

1. Sometimes your project file size is too big (Node modules) that you can't upload or it will take extra time to get uploaded on the cloud and surely it is not a good idea.

2. So, to ignore the files what we do is make a file name [ .gitignore ] which is a text file and put the folder name which you want to ignore.

3. Inside the file of .gitignore
	```sh
    node_modules
	*.pdf  [ it will exclude all the pdf files ]
	```

### 6. Pull Request

Most commonly it is used in the open source world.
How is it worked?
1. First you have to open the repository which you want to pull and then fork that repository [ fork option is shown on the right corner of the open repository ] into your github account [ private repo will be created ]
2. Then you make the changes in that code and push that on your private repo, and then click on the pull requests option then then add the meaningful comment there and create the pull request.
