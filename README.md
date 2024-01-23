# tulane-6100-git-practice
A repository for practicing Git/Github operations for CMPS 6100.

Use this repository to practice cloning, branching, pulling, pushing and opening a pull request.

## Cloning, Adding, Commiting & Pushing

Much of what you do in this class will involve pushing code you write on your own computer to Github, and perhaps syncing it with code you wrote on another computer. Git and Github together are very good for not only keeping a copy of your code in a safe place online, but also allowing you to merge code from different computers and (later) from other people. Try doing this to get a feel for working with Github and Git:

1. Clone this repository to create a local version of the repository on your computer. Changes to this local version will not affect the code online until we specifically **push** our code back to the online repository. To clone, find the green button on the repository page that says "**<> Code**" and copy the link that is shown in the box under the SSH tab.

Note: this assumes you have [generated and added an SSH key to Github](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), which will allow you to use Github without entering a password each time. If you would like to skip this, and just enter your Github password to authenticate, use the link under the HTTPS tab instead.

2. Using the terminal or Git Bash (a command-line program installed with Git, if you are using Windows), navigate to a directory that will be easy to access later (I have a folder called `projects` in my home directory where I keep all repositories). In this directory, type `git clone <paste the link from step 1>`. Cloning will create a copy of the repository files on your computer, stored in a folder with the same name as the repository. Open the respoitory folder with `cd tulane-6100-git-practice` and open its contents in a code editor such as VS Code. On most systems, with VS Code installed, typing `code .` will open the current directory in VS Code -- a very useful feature.

4. Make some changes to the file `main.py` or add a new file. Whatever you write doesn't need to work or make sense -- this is just to see the process of adding code.

5. Add your code to the ledger of changes that will be processed by the next commit. In the terminal opened to the respoitory's directory type `git add .`

6. Commit your changes. This is essentially Git's way of saving. In the terminal, type `git commit -m "--some message--"` Replace "**--some message--**" with a description of the changes you made. Usually we type these in present tense, such as "Add unit test for login API call".

7. Now you have officially committed your changes to your local computer, but this has not affected the online version of the repository on Github. To **push** these changes to Github, type `git push origin main`. The **origin** refers to the place on the internet you are pushing to and **main** refers to the branch. We'll learn more about branches later.

8. Repeat steps 4 - 6 anytime you significantly change your code. The frequency of commits you make is up to you, but the general advice is commit early and often.

## Working with Others: Branching and Pull Requests

As you progress to working on a software project with many other people, there needs to be a way to ensure that code introduced to the `main` branch is (generally) free of bugs and works well with the existing version. Usually this means that, as a protective measure, no one writes code directly to the `main` branch -- instead everyone works on a separate branch, and then adds code to the `main` branch through a **pull request**.

Ideally, the `main` branch only contains code that works -- a pull request not only allows others to review your code, it is also a good place to run automated tests to make sure no bad code is introduced to the production version of the project. Of course, software development in the real world doesn't always live up to this ideal but it's at least something to strive for!

For this exercise, pretend you are working with other people on a project, and the code on Github is your combined work.

1. Assuming you have the repository cloned to your computer (Step 1 in the first part), open the terminal to the respoitory's directory and type `git branch new-branch` (You can also replace "new-branch" with your name or some other arbitrary branch name). This will create a separate branch with the name "new-branch" or whatever name you picked.

Note: We normally wouldn't name a branch something as vague as "new branch" -- usually you would give the branch a name that would indicate what you were working on in that branch. For example, if you were adding the movement controls for a video game, you might name the branch "add-movement".

2. Switch to that branch by typing `git checkout new-branch`. Now any changes committed to this branch will be committed only to this branch.

3. Repeat steps 4 through 6 from the first part of this guide: add some code, stage the changes with `add .` and then commit the changes with `git commit -m "--some changes to note--"`.

### Opening a Pull Request

Now it's time to merge your code with the main branch. We could do this by switching back to the `main` branch, typing `git merge new-branch` and then pushing the code to Github. But that's not how it is usually done in a professional setting -- instead, we want to avoid touching the `main` branch unless it's done in a way where everyone else on the project can see those changes and approve them.

To open a **pull request**, let's do the following:

4. When working with other people, you should always **pull** any changes from `main` before you **push** your code. This will ensure that any conflicts between your branch and `main` are resolved in a controlled way that doesn't introduce breaking changes to `main` after a pull request is approved. To do this, make sure you are in the branch you created -- Git will indicate `new-branch` rather than `main` -- and type `git pull origin main`. This will take any changes from the `main` branch on Github and attempt to merge them with your code.

Note: If Git completes the merge without throwing any errors, you are all set to move on to the next step. However, if you and another person have edited the same code, you will have to tell Git whose code you would like to use. This is called a **conflict**. We won't go in depth about resolving conflicts, but briefly, you'll have to manually edit the files with conflicts, then stage the changes with `add .`, and then `commit` to resolve the issue.

5. From the terminal, push your new branch to Github with `git push origin new-branch`

6. From here, we can switch to our browser and go to Github and navigate to the [repository page for this project](https://github.com/rdkelley/tulane-6100-git-practice). This is where we'll open a pull request. From the top menu, select "Pull Requests" and then, "New Pull Request".

7. At the top of the new pull request screen, you'll see a graphic displaying what branch will be merged into the `main` branch. Make sure it indicates that `new-branch` is being merged into `main`. Github will see if a merge can be done automatically. If it can, you'll see the words "Able to merge" in green. This is an indication that your code does not conflict with `main`. If you do not see this, it probably means you forgot to **pull** from `main` before pushing. See Step 1 of this section! Click "Create Pull Request".

8. On the next screen, add a title to your PR and fill out the description. Use the title and description to describe the changes or additions made with this PR. When ready, click "Create Pull Request"

9. Now we wait. Usually this is when a team lead, manager or colleague reviews your changes and either approves them or starts asking questions. When the PR is approved, your code will be added to the `main` branch. For this tutorial, I'll act as the reviewer and approve your PR a few days after you submit (to simulate an overworked project lead).

To work on the next feature or kill the next bug, start a new branch and repeat this section!
