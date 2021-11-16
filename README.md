# Using Branches with a Team

## WORKING ON YOUR OWN BRANCH

1. Each person will clone the repo to their machine
2. By default you will be on the ```main``` branch
3. Checkout to your own branch using ```git checkout -b your-branch-name```
4. TO AVOID MERGE CONFLICTS: Communicate amongst yourselves to ensure you aren't working on the same files
5. When finished with the piece you're working on, commit and push your code
    ```
    git add -A   
    git commit -m "a description of what feature you've completed"
    git push origin your-branch-name
    ``` 
6. Make a pull request
    - Go to the pull request tab of your repo
    - Click the "New pull request" button
    - Choose your branch
    - Create pull request
    - See that there are no merge conflicts
    - Click the "Merge pull request" button
7. **VERY IMPORTANT! After you do this alert your team that a new merge has been made**

## AFTER A TEAMMATE MERGES

1. In VS Code, switch from your branch to main using `git checkout main`
2. Pull from main using `git pull origin main`
3. Switch back to your own branch using `git checkout your-branch`
4. Merge the new changes from main into your own branch using `git merge origin main`
5. Contine working

**This is also VERY IMPORTANT! If you forget to do this, there is a chance you could erase a teammates work from main if you commit and merge your code at a later time, that doesn't contain their work.**

## HANDLING ACCIDENTALLY OVERWRITING YOUR TEAMMATE'S WORK

The person erasing work may not be aware of what they've done! But no worries.

1. If you pull from `main` and merge and see any of your work disappear, you should be able to CMD/CTRL+Z that file to get it back right away.
2. Commit and create a pull request, and merge your code back into `main`
3. Tell your teammates to pull and merge into their branches.

## HANDLING MERGE CONFLICTS

### AS A TEAMMATE WHO IS MERGING MAIN INTO THEIR OWN BRANCH

In case you and a teammate were accidentally working on the same thing, you'll see this when you merge main into your branch. VS Code will highlight all merge conflicts. 

1. Call your teammate in and work together to see what code should be kept or deleted. 
2. After merge conflicts are handled, you can continue working.

### AS A TEAMMATE WHO SEES A MERGE CONFLICT PREVENTING A PULL REQUEST

This is usually because your code isn't up to date with `main`

1. Go back to your terminal and perform the steps above for "AFTER A TEAMMATE MERGES"
2. If there are any merge conflicts, sort them out with your teammate who was working on those files
3. Commit and push again
4. Go back to your pull request, and the "Merge pulll request" button should be green now
