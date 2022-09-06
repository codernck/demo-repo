## Git basics
**Source**

<https://www.youtube.com/watch?v=RGOj5yH7evk>

**Add SSH to github**

<https://www.youtube.com/watch?v=lV5mrUYsucU>

**How to resove conflicts**

<https://www.youtube.com/watch?v=xNVM5UxlFSA>

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


>Wehenver you make any changes to the files locally, you need to call
>```
>git add 
>```
>to let the git know that it should register these changes
>than we do 
>```
>git commit
>```
>to make this changes permanent locally
>than we do 
>```
>git push
>```
>to publish these changes


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

**To see the available branches inside the git repo we can use the below command**
```
git branch
```
>If we see the * symbol beside the branches it means we are in that branch

**To create a new branch we use the command**
```
git checkout -b <branch_name>
``` 

>The git checkout is also used to switch between the branches

>Suppose you pass like this,
>```
>git checkout -b feature-readme-instructions
>```
>>Now if we run
>>```
>>git branch
>>```
>we can see that the current branch is change to the newly created branch indicated tieh the * symbol. It also shows the master branch (now there are two branches master and feature-readme-instructions)

**To change our branch to the master, we need to pass**
```
git checkout master
```

>Here your master branch can be main instead of master here you need to pass as 
>```
>git checkout main
>```

**Now we change the branch to the newly created branch**
```
git checkout <new_branch>
```
than to the changes, then we notify the git by using the add
```
git add
```

>We can check the git status
>```
>git status
>```

than we do the
```
git commit -m "comments"
```

This will change only in the new_branch

if we do git checkout master and check we donot see these changes

**To sync the changes of new_branch we use the command
```
git merge
```

**To see the changes, we can use**
```
git diff new_branch
```

**Now inside the new_branch, we do**
```
git add
```
**than
```
git commit -m "comments"
```

**Now we call the merge command**
```
git merge
```

**But this is not a best practise**
**Instead we need to call the push on new_branch**
```
git checkout new_branch
git status
git push
```
>This git push will give error as we dont have new_branch inside the github till now

**So to resolve the error we use set-upstream feature as below
```
git push --set-upstream origin new_branch
```
>--set-upstream is same as -u
>```
>git push -u origin new_branch
>```

This will show also the pull request and how to use it

The pull request will request your code to be reviewed who can add comments to your code or they can approve for merge.

Once the code is merged you can delete your newly created branches

Now we can goto github.com, check the pull request, we can make the comments at line level or entire code level.

then we can resolve the comments then if all is well we can merge.
Now we are in the master branch. In github you can see tha new changes.

**Now if we switch to the master repo**
```
git checkout master
```
>here ``` git checkout main ```


Now we are in the master branch in our local system. But we wll not see any changes that are pushed from the branch to the master.
**To get these changes we need to use**
```
git pull origin master
```
>If we have upstream ser we can call ```git pull`` instead

**To delete the feature branch we use the below command**
```
git branch -d new_branch
```

**Also to create a new branch we can use**
```
git branch <new_branch>
```

**As already seen we can change the branch using the checkout**
```
git checkout <new_branch>
```

**We can add and commit the modified files in one shot using**
```
git commit -am "message"

```
>Note that ```git commit -am``` will not work for new files will only work for the modified files

**If we are in bran called aaa and we have some changes of bbb which need to be brought into aaa**
```
aaa> git merge bbb
```
>This is telling that we need to bring bbb repo changes to aaa

**Supppose we have made some hages and we made**
```
git add filename
```

**Now we dont want to use these chages or push these changes than we can call below command**
```
git reset filename
// or also we can call
git reset  => to apply to all the changes (all files changed)
```

This is called unstaging the file

**How to undo a commit**
```
git reset HEAD~1  // HEAD is last commit 
// HEAD~1 is last but one commit 
// and it will go there - undo till there
```

**To see the log of all the commits made**
```
git log
```

**To go back to particular commit need to copy the hash of the required commit**
```
git reset copied_hash
```

>this will unstage the commit

**To completely remove the commit changes**
```
git reset --hard copied_hash
```

**Fork=> will make a complete copy of the code**
**To clone the code in our repo**
