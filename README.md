# tulane-6100-git-practice
A repository for practicing Git/Github operations for CMPS 6100.

Use this repository to practice cloning, branching, pulling, pushing and opening a pull request.

Much of what you do in this class will involve pushing code you write on your own computer to Github, and perhaps syncing it with code you wrote on another computer. Git and Github together are very good for not only keeping a copy of your code in a safe place online, but also allowing you to merge code from different computers and (later) from other people. Try doing this to get a feel for working with Github and Git:

1. Clone this repository to create a local version of the repository on your computer. Changes to this local version will not affect the code online until we specifically **push** our code back to the online repository. To clone, find the green button on the repository page that says "**<> Code**" and copy the link that is shown in the box.

2. On your computer, using the terminal or Git Bash (a command-line program installed with Git if you are using Windows), type `git clone <paste the link from step 1>`.

3. Cloning will create a copy of the repository files on your computer, stored in a folder with the same name as the repository. Find this folder and open its contents in a code editor such as VS Code.

4. Make some changes to the file `main.py`. It doesn't need to work or make sense -- this is just to see the process of adding code.

4. Add your code to the ledger of changes that will be processed by the next commit (I know, this is confusing... but you'll get the hang of it). In the terminal opened to the respoitory's directory type `git add .`

5. Commit your changes. This is essentially Git's way of saving. In the terminal, type `git commit -m "--some message--"` Replace "**--some message--**" with a description of the changes you made. Usually we type these in present tense, such as "Add unit test for login API call".

6. Now you have officially committed your changes to your local computer, but this has not affected the online version of the repository on Github. To **push** these changes to Github, type `git push origin main`. The **origin** refers to the place on the internet you are pushing to and **main** refers to the branch. We'll learn more about branches later.

7. Repeat steps 4 - 6 anytime you significantly change your code. The frequency of commits you make is up to you, but the general advice is commit early and often.

As you progress to working on a software project with many other people, there needs to be a way to ensure that code introduced to the `main` branch is (generally) free of bugs and works well with the existing version. Usually this means that, as a protective measure, no one writes code directly to the `main` branch -- instead everyone works on a separate branch, and then adds code to the `main` branch through a **pull request**. You can practice this process here.

1.
