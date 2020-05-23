# GitHub Forking for Collaboration

## Step 1: Elect who will run the main repo

Choose one person who runs the main repo which everyone else will be contributing to, but not have control over. For these notes, we will call the main repo owner Maggie Main. What Maggie Main needs to do is create the main repo on her GitHub account as she would any repo, and likely wants to clone it or otherwise link it to a local repo she has for the project.

##### Example.
If Maggie creates a new repo on GitHub `https://github.com/MaggieMain/ForkPractice` she can then clone it to her local machine in a terminal:
```
cd <path-to-where-Maggie-wants-to-create-the-repo>
git clone https://github.com/MaggieMain/ForkPractice.git
```
Note, the repo that is cloned will appear as a directory within the working directory of the terminal during the cloning, so be sure that the working directory is not already a git repo since it is not likely you want to create nested git repos!

Instead, if she wants to link the ForkPractice GitHub repo to an already extant local repo:
```
cd <path-to-extant-repo>
git remote add origin https://github.com/MaggieMain/ForkPractice.git
git push -u origin master
```

## Step 2: Other teammates fork the main repo

Once Maggie Main has created what will be the main repo, the teammates need to direct to Maggie Main's main repo on GitHub. Once there, select **Fork**, which makes a copy of the repo to each individual teammates personal GitHub account.

## Step 3: Other teammates clone their forked copies.

After each teammate has forked the main repo, they should then **clone** that repo to their desired location on their personal machine. This creates a git repo on the local machine under the same name as the forked repo. Note, the repo that is cloned will appear as a directory within the working directory of the terminal during the cloning, so be sure that the working directory is not already a git repo since it is not likely you want to create nested git repos!

##### Example Cont'd
If Frank Fork is one of the teammates, then after he forks Maggie's GitHub repo, he will have a new repo on his GitHub account, something like `https://github.com/FrankFork/ForkPractice`. Now, from his local machine, he will clone his copy of the repo in a terminal with
```
cd <path-to-where-Frank-wants-to-create-the-repo>
git clone https://github.com/FrankFork/ForkPractice
```

## Step 4: Make non-conflicting changes

At this point, each teammate can work on their own stuff in their forked and cloned repos. Try to keep the work reasonably independent from what others are working on to prevent merge conflicts. For example, each teammate can create their own directory, work within their own directories and make a decision how to compile any work that needs to be put together.

## Step 5: Pull Request to Main

One a teammate has made changes they would like to contribute to main, they first need to make sure their forked GitHub repo is up to date with the desired changes (e.g. via `git push` from their local machine). Then, from GitHub, create a new pull request. Just like when committing, putting in a pull request will send a request to the original repo (in our example, to Maggie Main's ForkPractice repo) which can be approved and merged, or potentially other actions (request changes, or deny a merge).

## Step 6-ish: Reverse Pull Request (Updating the forked repo)

It is also possible through a pull request to update the forked repo. This works by going to New Pull Request and "switching the base" so that the direction of the pull comes from the original main repo (Maggie Main's), and directs to the teammate's forked repo. This "switched base" pull request, allows the owner of the forked repo update their forked repo.

To note, if you update your GitHub content, you will likely want to update your local repo as well. This can be done with `git pull origin master` (pulling from remote to local, the reverse of pushing which moves from local to remote).
