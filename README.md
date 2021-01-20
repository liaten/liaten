[Tutorial] Create a Cydia repository using Github Pages
I had to repost this because my post was showing removed, but I hope it works now.

Creating a Cydia Repository using Github Pages
In this tutorial I will be showing you how to create a Github Pages. My goal for this tutorial is for you to create a Cydia Repository and me explaining how to setup this repo as simply as possible.

Part 0: What is a Cydia repository used for?
A Cydia repository can be used for many things, from creating tweak and themes to hosting tweaks and themes. I have created this tutorial and trusted you all to not use this for creating piracy repos.

Preparations
There are a few things you will need to have before setting up a repo:
1) A Github account with a verified email and is not flagged or not permitted to use Github Pages
2) Git or the Github Desktop app
3) Archiving program that supports archiving bzip2 like 7-Zip
4) A jailbroken device in which you can test your repo (Optional but recommended)
5) Notepad++ or simillar (Optional but recommended)

Part 1: Setting up your Github repository
Now if you have already created a Github repo or know how to make one, you do not need to read the rest of Part 1, if not you should read this part.

The first step is to obviously sign into your Github account and click "Start A Project" or "New Repository"

You should be in the Create a New Repository page, under "Repository name", you will put the name of your repository, this can be anything you want that is not currently used on your Github account.

If you want, you can set a description do explain what this repo does, if not you can skip the description box.

If you have a paid Github account, then you can make the repository private if you prefer, I don't know if this conflicts with the Github pages as I do not own a paid Github account. If you do not know what a private repository is, or what a paid Github account is, then you do not need to worry about this. By default it should be public.

Next is the "Initialize this repository with a README" this is up to you, I personally do not use it, but if you prefer using a README.md or you are using the online uploader (Which I DO NOT recommend by the way) then there isn't a big problem with not having a README.md file.

The last part of creating the repository is the .gitignore and License, unless you have a license for the repo (i.e. MIT or GNU license) then you can ignore these. .gitignore isn't a use for a Cydia Repo as gitignore's are normally for putting in projects.

Finally, you can press "Create Repository".

Part 2: Cloning the repository
If you know how to clone a repository then you can skip Part 2, I am explaining this to people who are new to Git and/or Github

In Git, You will need the git link, so you will want to press Clone or Download and it should say Clone with HTTPS, copy the link provided. If you do not have the README.md file, it should show the link in the middle-ish of the page. Open Git Bash if on Windows, on anything else open your terminal. Go to a directory that you want to clone it into, type `git clone` then the git link you got earlier. It will clone the repository to your system where later you will post it to the repo.

In the Github Desktop App, sign into your account and go to File > Clone Repository, select the repo you chose earlier, keep the "Local path" in mind, and press "Clone".

Open a file browser and navigate to the directory.
