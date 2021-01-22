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

## Часть 3: Настройка репозитория
Теперь самое интересное - настройка репозитория, чтобы позволить обмен информацией между Cydia и репозиторием.

### Шаг 1. Создайте файл Release и Packages
Откройте текстовый редактор и сохраните 2 пустых файла: Release и Packages (УБЕДИТЕСЬ, ЧТО В КОНЦЕ НЕТ .txt!)

### Шаг 2. Создайте папку с именем debs
### Шаг 3. Создайте файл с именем index.html
Внутри этого файла напишите:
```html
<!DOCTYPE html>
<html>
<body>
<h1>Hello World!</h1>
<p>This is a Cydia repo!</p>
</body>
</html>
```
### Шаг 4: Измените Release
Внутри Release настройте текст в скобках.
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
Все они могут быть вашим именем репозитория, это не имеет значения.

## Часть 4: Добавляем твик/тему

Это наполовину сложная часть, и я объясню ее как можно проще. Внутри ваших packages (пакетов) вам нужно будет поместить это
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

Package (пакет) - это ваш ID твика (com.example.package).

Name - это имя вашего твика (Test Package).

Version - это ну версия вашего твика (10.25.1-2).

Architecture - это или iphone-os-arm или iphoneos-arm64 в большинстве случаев, если вы не знаете, что это, ставьте iphoneos-arm.

Description - это описание настройки (это тестовый пакет!).

Maintainer - это тот, кто обновляет / обслуживает пакет на репозитории (скорее всего, это будете вы - youremail@ifyouwant.com).

Author - создатель твика (Автор твика hisorheremail@ifyouwant.com).

Section - это раздел, в который он входит лучше всего (Твик) или (Тема). Зависит от того, что может быть необходимо для правильной работы.

Filename - это имя файла deb, если deb был в папке debs, это будет debs / debfilehere.deb.

Size - Размер файла в байтах (288338) MD5sum - это хэш MD5 <b> СТРОЧНЫМИ БУКВАМИ </b>. Найдите md5 на сайте или еще где-нибудь.

SHA1 - это хэш SHA1 <b> СТРОЧНЫМИ БУКВАМИ </b>. Найдите SHA1 на веб-сайте или еще где-нибудь.

SHA256 - это хэш SHA256 <b> СТРОЧНЫМИ БУКВАМИ </b>. Найдите SHA256 на веб-сайте или еще где-нибудь.

Теперь, когда это настроено, файл может выглядеть примерно так (это мой Package файл темы Pwn Respring):
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

Второе, что нужно сделать, это сохранить их и заархивировать пакеты <b> Not Release </b> в bzip2. Для этого сохраните файл Packages и щелкните его правой кнопкой мыши (при условии, что вы находитесь в Windows и используете 7zip), наведите указатель мыши на 7-Zip и нажмите «Добавить в архив» ... затем появится графический интерфейс, в разделе «Формат архива» выберите bzip2.

Если хотите, удалите пакеты.

## Часть 5: Зафиксируйте изменения и включите Github pages

Using Git to commit the changes: open git like you did earlier and go to the directory you cloned it to, type `git add .` then `git commit -m "Initial Commit"` then `git push` then sign into github.

Using the Github Desktop App to commit the changes: select all the modified files in the Github app (if they aren't already) and create a message on the bottom left (i.e. Initial Commit) and hit commit to master. then on the top middle-ish you will see a button with a down arrow or a cloud looking thing (Your turn to figure it out ;) ) The changes have been saved.

To enable Github Pages go to your repo, Find Settings and scroll down to Github Pages, under source you will see none, change that to Master branch press the save button and then the page will refresh. Scroll down again and it should say The site is published or something (I forgot ;) ) that link is the link for your repo. Add it via. Cydia and there you go! It should work! Please feel free to post any issues in the comments.
