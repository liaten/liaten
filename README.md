~~[Tutorial] Create a Cydia repository using Github Pages~~
# [Учебное пособие] Создание репозитория Cydia с помощью Github Pages (20.12.2018)
Ссылка на оригинал: https://www.reddit.com/r/jailbreak/comments/90gpli/tutorial_create_a_cydia_repository_using_github/

~~I had to repost this because my post was showing removed, but I hope it works now.~~

Мне пришлось сделать репост, потому что мой пост показывался удаленным, но я надеюсь, что теперь он работает.

~~Creating a Cydia Repository using Github Pages~~
## Создание репозитория Cydia с использованием страниц Github

~~In this tutorial I will be showing you how to create a Github Pages. My goal for this tutorial is for you to create a Cydia Repository and me explaining how to setup this repo as simply as possible.~~
В этом руководстве я вам покажу, как создать Github Pages. Моя цель в этом руководстве создание Cydia репозитория и объяснение, как настроить этот репозиторий как можно проще.

## Part 0: What is a Cydia repository used for?
A Cydia repository can be used for many things, from creating tweak and themes to hosting tweaks and themes. I have created this tutorial and trusted you all to not use this for creating piracy repos.

## Preparations
There are a few things you will need to have before setting up a repo:
1) A Github account with a verified email and is not flagged or not permitted to use Github Pages
2) Git or the Github Desktop app
3) Archiving program that supports archiving bzip2 like 7-Zip
4) A jailbroken device in which you can test your repo (Optional but recommended)
5) Notepad++ or simillar (Optional but recommended)

## Part 1: Setting up your Github repository
Now if you have already created a Github repo or know how to make one, you do not need to read the rest of Part 1, if not you should read this part.

The first step is to obviously sign into your Github account and click "Start A Project" or "New Repository"

You should be in the Create a New Repository page, under "Repository name", you will put the name of your repository, this can be anything you want that is not currently used on your Github account.

If you want, you can set a description do explain what this repo does, if not you can skip the description box.

If you have a paid Github account, then you can make the repository private if you prefer, I don't know if this conflicts with the Github pages as I do not own a paid Github account. If you do not know what a private repository is, or what a paid Github account is, then you do not need to worry about this. By default it should be public.

Next is the "Initialize this repository with a README" this is up to you, I personally do not use it, but if you prefer using a README.md or you are using the online uploader (Which I DO NOT recommend by the way) then there isn't a big problem with not having a README.md file.

The last part of creating the repository is the .gitignore and License, unless you have a license for the repo (i.e. MIT or GNU license) then you can ignore these. .gitignore isn't a use for a Cydia Repo as gitignore's are normally for putting in projects.

Finally, you can press "Create Repository".

## Part 2: Cloning the repository
If you know how to clone a repository then you can skip Part 2, I am explaining this to people who are new to Git and/or Github

In Git, You will need the git link, so you will want to press Clone or Download and it should say Clone with HTTPS, copy the link provided. If you do not have the README.md file, it should show the link in the middle-ish of the page. Open Git Bash if on Windows, on anything else open your terminal. Go to a directory that you want to clone it into, type `git clone` then the git link you got earlier. It will clone the repository to your system where later you will post it to the repo.

In the Github Desktop App, sign into your account and go to File > Clone Repository, select the repo you chose earlier, keep the "Local path" in mind, and press "Clone".

Open a file browser and navigate to the directory.

## Part 3: Setting up the repository
Now is the fun part, setting up the repository to allow Cydia and the repository to exchange information with each other.

### Step 1: Create a Release and Packages file.
Open a text editor and save 2 empty files: Release and Packages (MAKE SURE THERE IS NO .txt AT THE END!)

### Step 2: Create a folder called debs
### Step 3: Create a file called index.html
Inside that file type
```html
<!DOCTYPE html>
<html>
<body>
<h1>Hello World!</h1>
<p>This is a Cydia repo!</p>
</body>
</html>
```
### Step 4: Modify Release
Inside Release customize the text in brackets
```
Origin: (Modify)
Label: (Modify)
Suite: stable
Version: 1.0
Codename: ios
Architectures: iphoneos-arm
Components: main
Description: (Modify)
```
They can all be your repo name, it doesnt matter.
### Part 3: Adding a tweak/theme
This is a half-complicated part and I will explain it as simply as possible. Inside of your packages you will need to put this
```
Package: 
Name: 
Version: 
Architecture: 
Description: 
Maintainer: 
Author: 
Section: 
Depends: 
Filename: 
Size: 
MD5sum: 
SHA1: 
SHA256:
```
The package is your id for the tweak (com.example.package) The name is the name of your tweak (Test Package) The version is, well the version of your tweak (10.25.1-2) Architecture is either iphone-os-arm or iphoneos-arm64 in most cases, if you dont know what this is, put iphoneos-arm The description is the description of the tweak (This is a test package!) Maintainer is whoever is keeping the package updated / maintaned on the repo (most likely you youremail@ifyouwant.com) Author is the creator of the tweak (Author of the tweak hisorheremail@ifyouwant.com) Section is the category it fits into the best (Tweak) or (Theme) Depends is anything it might need to work properly Filename is the name of the deb file if the deb was in the debs folder it would be debs/debfilehere.deb Size of the file in bytes (288338) MD5sum is the MD5 hash <b>IN LOWERCASE</b>. Find the md5 on a website or something. SHA1 is the SHA1 hash <b>IN LOWERCASE</b>. Find the SHA1 on a website or something. SHA256 is the SHA256 hash <b>IN LOWERCASE</b>. Find the SHA256 on a website or something.
Now, once that is configured it might look something like this (this is my Pwn Respring themes Package file).
```
Package: xyz.bigbadevan.pwnrespring
Name: Pwn Respring
Version: 1.0
Architecture: iphoneos-arm
Description: Respring with a Pwnapple!
Maintainer: Evan <evan@bigbadevan.xyz>
Author: Evan <evan@bigbadevan.xyz>
Section: Themes
Depends: com.wizages.bae, com.anemonetheming.anemone, com.wizages.springchanger
Filename: debs/xyz.bigbadevan.pwnrespring_iphoneos-arm_1.0.deb
Size: 59498
MD5sum: a0c466f73e7b4bc4a0b6376f08b1e6f4
SHA1: 9e18235b553d27923e65c06d1046614c3b3c9f56
SHA256: 9b7398fe1bee4a25406113c860f8c6963d433d06252dbf7eba150d238b7ca9eb
```
The 2nd last thing is to save those and zip Packages <b>Not Release</b> to bzip2. To do this, save the Packages file and right click it (assuming you are on windows and using 7zip) hover over 7-Zip and press Add to archive... then a gui will appear, under Archive Format chose bzip2.
Delete Packages if you want.
### Part 4: Commit the changes and enable Github pages
The final step is to commit the changes and enable Github pages.

Using Git to commit the changes: open git like you did earlier and go to the directory you cloned it to, type `git add .` then `git commit -m "Initial Commit"` then `git push` then sign into github.

Using the Github Desktop App to commit the changes: select all the modified files in the Github app (if they aren't already) and create a message on the bottom left (i.e. Initial Commit) and hit commit to master. then on the top middle-ish you will see a button with a down arrow or a cloud looking thing (Your turn to figure it out ;) ) The changes have been saved.

To enable Github Pages go to your repo, Find Settings and scroll down to Github Pages, under source you will see none, change that to Master branch press the save button and then the page will refresh. Scroll down again and it should say The site is published or something (I forgot ;) ) that link is the link for your repo. Add it via. Cydia and there you go! It should work! Please feel free to post any issues in the comments. Thanks for reading this <3

EDIT: If you want an example of what it should look like or add a Cydia Icon or HTML depictions. Go to https://github.com/bigbadevan/cydia

You should also add my repo: cydia.bigbadevan.xyz
