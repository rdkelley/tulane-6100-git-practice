# tulane-6100-git-practice
A repository for practicing Git/Github operations for CMPS 6100.

Use this repository to practice cloning, branching, pulling, pushing and opening a pull request.

Much of what you do in this class will involve pushing code you write on your own computer to Github, and perhaps syncing it with code you wrote on another computer. Git and Github together are very good for not only keeping a copy of your code in a safe place online, but also allowing you to merge code from different computers and (later) from other people. Try doing this to get a feel for working with Github and Git:

1. Clone this repository to create a local version of the repository on your computer. Changes to this local version will not affect the code online until we specifically **push** our code back to the online repository. To clone, find the green button on the repository page that says "**<> Code**" and copy the link that is shown in the box.

2. On your computer, using the terminal or Git Bash (a command-line program installed with Git if you are using Windows), type `git clone <paste the link from step 1>`.

3. Cloning will create a copy of the repository files on your computer, stored in a folder with the same name as the repository. Find this folder and open its contents in a code editor such as VS Code.

4. Make some changes to the file `main.py`. It doesn't need to work or make sense -- this is just to see the process of adding code.

5. Add your code to the ledger of changes that will be processed by the next commit (I know, this is confusing... but you'll get the hang of it). In the terminal opened to the respoitory's directory type `git add .`

6. Commit your changes. This is essentially Git's way of saving. In the terminal, type `git commit -m "--some message--"` Replace "**--some message--**" with a description of the changes you made. Usually we type these in present tense, such as "Add unit test for login API call".

7. Now you have officially committed your changes to your local computer, but this has not affected the online version of the repository on Github. To **push** these changes to Github, type `git push origin main`. The **origin** refers to the place on the internet you are pushing to and **main** refers to the branch. We'll learn more about branches later.

8. Repeat steps 4 - 6 anytime you significantly change your code. The frequency of commits you make is up to you, but the general advice is commit early and often.

As you progress to working on a software project with many other people, there needs to be a way to ensure that code introduced to the `main` branch is (generally) free of bugs and works well with the existing version. Usually this means that, as a protective measure, no one writes code directly to the `main` branch -- instead everyone works on a separate branch, and then adds code to the `main` branch through a **pull request**. You can practice this process here.

For this exercise, pretend you are working with other people on a project, and the code on Github is your combined work.

1. Assuming you have the repository cloned to your computer (Step 1 above), open the terminal to the respoitory's directory and type `git branch new-branch` (You can replace new-branch with your name some other branch name).  This will create a seperate branch with the name "new-branch" or whatever name you picked. 

Note: Usually, we wouldn't name a branch something as vague as "new branch" -- usually you would give the branch a name that would indicate what you were working on in that branch. For example, if you were adding the movement controls for a video game, you might name the branch "add-movement".

2. Switch to that branch by typing `git checkout new-branch`. Now any changes committed to this branch will be committed only to this branch.

3. Repeat steps 4 through 6 from the first part (**add** and ***commit** your changes).

4. Now it's time to merge your code with the main branch. We could do this by switching back to the `main` branch, typing `git merge new-branch` and then pushing the code to Github. But that's not how it is usually done in a professional setting -- instead, we want to avoid touching the `main` branch unless it's done in way where everyone else on the project can see those changes and approve them. This is called a **pull request** and it done through Github.

To open a **pull request**, let's do the following:

1. Make sure you are in the branch you created -- Git will indicate `new-branch` rather than `main`. From the terminal, push your new branch to Github with `git push origin new-branch`

2. From here, we can switch to our browser and go to Github -- specifically, the repsoitory page for this project. This is where we'll open a PR. From the top menu, select "Pull Requests" and then, "New Pull Request".

3. At the top of the new pull request screen, you'll see a graphic displaying what branch will be merged into the `main` branch. Make sure it indicates that `new-branch` is being merged into `main`. Click "Create Pull Request".

4. 


