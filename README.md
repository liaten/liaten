# [Руководство] Создание Cydia репозитория с помощью Github Pages (20.12.2018)
Ссылка на оригинал: https://www.reddit.com/r/jailbreak/comments/90gpli/tutorial_create_a_cydia_repository_using_github/

## Создание Cydia репозитория с использованием Github Pages

В этом руководстве я вам буду показывать, как создать Github Pages. Моя цель в этом руководстве - создание Cydia репозитория и объяснение настройки этого репозитория как можно простым способом.

## Часть 0: Для чего используется Cydia репозиторий?
Cydia репозиторий  может использоваться для множества вещей, от создания настроек (твиков `от англ. tweaks`) и тем до их размещения. Я создал это руководство и доверил его вам, чтобы вы не использовали его для создания пиратских репозиториев.

## Подготовка

Вот несколько важных компонентов, необходимых для установки репозитория:
1) Учетная запись Github с подтвержденным адресом электронной почты, не отмеченная или не имеющая разрешения на использование страниц Github.
2) Git или приложение Github Desktop
3) Программа архивации, поддерживающая архивацию bzip2, например 7-Zip (https://www.7-zip.org/download.html)
4) Взломанное устройство, на котором вы можете протестировать свое репо (необязательно, но рекомендуется) (https://http://canijailbreak.com/)
5) Notepad ++ или подобный (Я использую visual studio (либо vscode))

## Часть 1: Настраиваем ваш репозиторий Github
Теперь, если вы уже создали Github репозиторий или знаете, как его создать, то вам не нужно читать оставшуюся часть 1-й части, если нет, то вам стоит прочитать эту часть.

Первый шаг - очевидно, войти в свою учетную запись Github и нажать на "+" -> "New Repository"

На странице создания нового репозитория, в разделе «имя репозитория» вы должны указать имя своего репозитория, это может быть что угодно, что в настоящее время не используется в вашей учетной записи Github.

Если вы хотите, то вы можете установить описание, чтобы объяснить, чем занимается этот репозиторий, если нет, то вы можете пропустить поле описания.

Если у вас есть платная учетная запись Github, то вы можете сделать репозиторий частным, если хотите. Я не знаю, конфликтует ли это со страницами Github, поскольку у меня нет платной учетной записи Github. Если вы не знаете, что такое частный репозиторий или что такое платная учетная запись Github, вам не нужно об этом беспокоиться. По умолчанию он должен быть публичным.

Далее идет «Initialize this repository with a README», это зависит от вас, я лично не использую его, но если вы предпочитаете использовать README.md или используете онлайн-загрузчик (что, кстати, я НЕ рекомендую) тогда нет большой проблемы в отсутствии файла README.md.

Последняя часть создания репозитория - это .gitignore и License, если у вас нет лицензии на репо (т.е. лицензии MIT или GNU), вы можете игнорировать их. .gitignore не используется для Cydia репозитория, поскольку .gitignore обычно используется для размещения в проектах.

Наконец, вы можете нажать «Create Repository».

## Часть 2: Клонирование репозитория
Если вы знаете, как клонировать репозиторий, то вы можете пропустить Часть 2, я объясняю это людям, которые плохо знакомы с Git и/или Github.

В Git вам понадобится ссылка git, поэтому вы захотите нажать `Clone` или `Download`, и он должен сказать `Clone with HTTPS`, скопируйте предоставленную ссылку. Если у вас нет файла README.md, он должен показать ссылку посередине страницы. Откройте Git Bash, если в Windows, в любом другом случае откройте свой терминал. Перейдите в каталог, в который вы хотите его клонировать, введите ``git clone``, затем ссылку git, которую вы получили ранее. Так склонируется репозиторий в вашу систему, где позже вы разместите его в репозиторий.

In the Github Desktop App, sign into your account and go to File > Clone Repository, select the repo you chose earlier, keep the "Local path" in mind, and press "Clone".

В Github Desktop войдите в свою учетную запись и перейдите в меню `File` > `Clone Repository`, выберите репозиторий, который вы выбрали ранее, запомните `Local path` и нажмите `Clone`.

Откройте файловый браузер и перейдите в каталог.

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
### Part 4: Adding a tweak/theme
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
### Part 5: Commit the changes and enable Github pages
The final step is to commit the changes and enable Github pages.

Using Git to commit the changes: open git like you did earlier and go to the directory you cloned it to, type `git add .` then `git commit -m "Initial Commit"` then `git push` then sign into github.

Using the Github Desktop App to commit the changes: select all the modified files in the Github app (if they aren't already) and create a message on the bottom left (i.e. Initial Commit) and hit commit to master. then on the top middle-ish you will see a button with a down arrow or a cloud looking thing (Your turn to figure it out ;) ) The changes have been saved.

To enable Github Pages go to your repo, Find Settings and scroll down to Github Pages, under source you will see none, change that to Master branch press the save button and then the page will refresh. Scroll down again and it should say The site is published or something (I forgot ;) ) that link is the link for your repo. Add it via. Cydia and there you go! It should work! Please feel free to post any issues in the comments. Thanks for reading this <3

EDIT: If you want an example of what it should look like or add a Cydia Icon or HTML depictions. Go to https://github.com/bigbadevan/cydia

You should also add my repo: cydia.bigbadevan.xyz
