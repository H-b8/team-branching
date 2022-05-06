# Using Branches with a Team

## WORKING ON YOUR OWN BRANCH

1. Each person will clone the repo to their machine
2. By default you will be on the `main` branch
3. Checkout to your own branch using `git checkout -b your-branch-name`
4. TO AVOID MERGE CONFLICTS: Communicate amongst yourselves to ensure you aren't working on the same files
5. When finished with the piece you're working on, commit and push your code
    ```
    git add -A   
    git commit -m "a description of what feature you've completed"
    git push origin your-branch-name
    ``` 
6. Make a pull request on GitHub
    - Go to the pull request tab of your repo
    - Click the "New pull request" button
    - Choose your branch
    - Create pull request
    - See that there are no merge conflicts
    - Click the "Merge pull request" button
7. **VERY IMPORTANT! After you do this, alert your team that a new merge has been made**

## AFTER NEW CODE IS MERGED

1. In your terminal, save what you're working on by running `git stash`
2. Switch from your branch to main using `git checkout main`
3. Pull from main using `git pull origin main`
4. Switch back to your branch using `git checkout your-branch-name`
5. Merge the new changes from main into your own branch using `git merge origin main`
6. Run `npm i` in your terminal if they installed any new packages
7. Continue working

**This is also VERY IMPORTANT! If you forget to do this, there is a chance you could erase a teammates work from main if you commit and merge your code at a later time, that doesn't contain their work.**

## HANDLING ACCIDENTALLY OVERWRITING YOUR TEAMMATE'S WORK

The person erasing work may not be aware of what they've done! But no worries.

1. If you pull from `main` and see any of your work disappear after merging into your own branch, you should be able to CMD/CTRL+Z that file to get it back right away.
2. Commit and create a pull request, then merge your code back into `main`
3. Tell your teammates to pull `main` and merge into their branches before continuing!

## HANDLING MERGE CONFLICTS

### REVIEWING A TEAMMATE'S PULL REQUEST

1. To ensure you aren't creating any merge conflicts on your end,
    ```
    git stash
    git checkout main
    git pull origin main
    git checkout -b teammates-branch-name
    git fetch origin teammates-branch-name
    git reset --hard origin/teammates-branch-name
    ```
2. If you find any merge conflicts at this point, ask your teammate to make sure they have the latest version of `main`, to merge it into their branch and handle merge conflicts on their end before pushing up again.
3. `git pull origin teammates-branch-name`
4. Continue your review.

### AS A TEAMMATE WHO IS MERGING MAIN INTO THEIR OWN BRANCH

In the case that you and a teammate were accidentally working on the same files, and they merged before you, you'll see this when you merge main into your branch. Your code editor should highlight all merge conflicts. 

1. Call your teammate in and work together to see what code should be kept or deleted. 
2. After merge conflicts are handled, you can continue working. Remembering to remind one another what files you're currently working on!

### AS A TEAMMATE WHO SEES A MERGE CONFLICT PREVENTING THE CREATION OF A PULL REQUEST

This is usually because your code isn't up to date with what `main` was when your teammate last pulled

1. Go back to your terminal and perform the steps above for "AFTER A TEAMMATE MERGES"
2. If there are any merge conflicts, sort them out with your teammate who was working on those files
3. Commit and push again
4. Go back to your pull request, and the "Merge pulll request" button should be green now
