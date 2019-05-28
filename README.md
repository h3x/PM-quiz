# quiz [here](https://h3x.github.io/PM-quiz/)

# quiz [here](https://h3x.github.io/database-quiz/)


### How to contribute

First of all, fork this repo, then clone it to your local machine

Next for safety, you want to sync your fork with the upstream repo (i.e the one on my account) to allow syncing your fork with this repository.

If you havent already, sync your fork with this repo. do this by:

```git remote add upstream https://github.com/h3x/PM-quiz.git```

This will let you pull changes from the original repo, into your fork when they happen

The next thing you want to do, is create a feature branch for your changes

```git checkout -b seansquestions```

You can now go and make your additions and add your questions. when your done:

```git add .```

```git commit -m "added 7 questions"```

Now you need to push the commit and the branch, and setup upstream tracking:

the --all will tell git to push all of our changes, and all of our branches. the -u will setup upstream tracking on the branches

```git push --all -u```

Next, go over to github, switch over to your feature branch and click the 'compare and pull request' button

Because theres not that many people working on it at the same time, and you've just forked it, it should say 'able to merge' in green. This means theres been no changes in the upstream repos since you forked. So you can go ahead and click pull request, and your job is done.

If there have been changes to the repo since you forked, however, before you can create a pull request, you need to merge these changes into your fork first, and reslove any merge conflicts that may occur. In this projects case, because its small, probably wont be difficult. Youll know this has happened, because when you make your pull request, you'll get a warning saying that the 'pull request contains merge conflicts that must be resolved'. This is where you need to rebase your fork from upstream master, then update your pull request. This is much easier if you keep your master branch clean of changes until they have been merged into the project in this repository.

Checkout master:

```git checkout master```

Chen:

```git pull --rebase upstream master```

 

Now your master branch on your fork is updated to the lastest changes in the upstream master branch. Checkout your branch now

```git checkout seansquestions```

Now you want to rebase your branch

```git rebase master```

This is when you'll be warned of any merge conflicts that you need to fix

Open the file that is mentioned in the warning in your text editor and fix it up and save the file

Now re-add all files, and continue the rebase:

```git add .```

```git rebase --continue```

This should now rebase your branch. IUf it doesnt and you get another warning, then something else is conflicting and you need to look at the file again and fix up the problems again.

Now, you need to push your changes up. Your going to have to force push it, and this is why you need to make sure all merge conflicts have been resolved on your end.

```git push --force```

Now if all goes well, the pull request should automatically be updated, and ill see on my end that i can merge your pull request with no conflicts.

Once your pull request has been merged, your master branch is going to be out of sync. This is not a problem until next time you want to add or change a file. So with your master branch checked out,

```git pull --rebase upstream master```

```git push```

And now you will be in sync again on your local machine, aswell as your github repo.

Rinse and repeat.

 

The important thing, is that your local master stay a clean copy. Meaning that when you want to make changes, git pull --rebase your master, branch your master to a feature branch, do your thing in that feature branch, then follow the above steps. Our local master should be used to stay in sync with upstream master, not to make changes on.

have fun!
