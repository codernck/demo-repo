## Git basics
**Add SSH to github**
https://www.youtube.com/watch?v=lV5mrUYsucU

**To clone the repo use**
```
git clone <repo-name>
```

**After you make the changes use the git status command to find the changes**
```
git status
```

**To add the files you can use the**
```
git add 
```

**If you pass as,**
```
git add .
```
 => this will monitor all the  modiefied and added files instead if you want to give the specific file pass like below,
```
git add filedir/filename
```

**After git add, you need to check the**
```
git status again
```

**Finally we do git commit along with message**
```
git commit -m "msg_heading" -m "message_description"
```

*The first -m is the message heading, the second -m is the description.*

The git commit has just and only made the changes locally (in your computer).

**To publish the code to github you need to use the command,**
```
git push
```

>Before git push you can check **git status** once

**This will push/publish the code**
```
git push origin master
```


Now to add a new project to github, 
- create the project folder and structure in your local machine first, 
- than need to navigate to the folder of the project 
- and run the command
```
git init
```


**This has creasted git repo in local machine but we cant use the below command,**
```
git push origin master
```

>This will give error as the origin is not created in github yet
>>Suppose we create a repo in github.com => repo2

**Then to map the repo to this project folder, we use the below command**
```
git remote add origin <new_repo_link.git>
```

**To verify we need to use the**
```
git remote -v
```

>this will display the repo its linked to

**To push/publish this code**
```
git push origin master
```

>if we use the -u option (upstream), now we need not use the git push origin master instead we can use the below command,
>```
>git push
>```

## Git branching:
When we create a repo we have only one master branch, all the changes we made when committed will go to this master branch.

Suppose we made a new branch called the feature branch, whatever changes we make go to the feature branch.

Now when we switch back to the master branch we cant see the changes we made in the feature branch

Each individual branch is independent, it will not know what changes or what commits we made to other branches. All changes and commits are local to the given branch.

>When we create a new feature branch the code in the master and the new feature branch are both exactly the same

>But as you make the changes in feature branch and commit these will be visible only to the feature branch

>This will be useful to make any new feature which is not stable, and you dont want these unstable code to go inside the master branch, this is like a sandbox area.

>Once this code is stable you can merge to the master branch

If after merging the feature branch of we notice any bugs in the master branch, we will create a new hotfix branch and we fix and commit in that branch(single) and then we merge to master branch














