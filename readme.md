# Первое знакомство с Git.


## 1. Что такое Git.
Git — это система контроля версий, которая помогает отслеживать изменения в проекте. Этот инструмент можно использовать как для индивидуальной, так и для командной работы.
Git позволяет сохранять изменения локально и при необходимости возвращаться к предыдущим версиям проекта. Также можно создать удалённую копию на хостинг-платформе, которая работает с Git, и поделиться результатом с другими.<br>
___

## 2. Установка Git.
Прежде чем использовать Git, вы должны установить его на своём компьютере. Даже если он уже установлен, наверное, это хороший повод, чтобы обновиться до последней версии. Вы можете установить Git из собранного пакета или другого установщика, либо скачать исходный код и скомпилировать его самостоятельно.

**Установка в Linux** <br>
Используйте собственную систему управления пакетами дистрибутива Linux для установки и обновления Git. Например, в Ubuntu: <br><br>
```bash
sudo apt-get install git
```


**Установка в Windows**<br>
Загрузите и установите [Git для Windows](https://git-scm.com/download/win). После установки Git доступен из командной строки или PowerShell. Рекомендуется выбрать значения по умолчанию во время установки, если их не нужно изменить. Git для Windows не обновляется автоматически. Чтобы обновить Git для Windows, скачайте новую версию установщика, которая обновляет Git для Windows и сохраняет все параметры.


**Установка на Mac**<br>
macOS 10.9 (Mavericks) и выше устанавливает Git при первой попытке запустить его из терминала. Хотя этот метод является простым способом получения Git в системе, он не позволяет контролировать частоту применения обновлений или исправлений безопасности. Вместо этого рекомендуется установить Git через [Homebrew и использовать средства Homebrew](http://brew.sh/) для обновления Git. Homebrew — отличный способ установить средства разработки с открытым кодом и управлять ими в Mac из командной строки. Установите Homebrew и выполните следующую команду, чтобы установить последнюю версию Git на Mac:<br><br>
```
brew install git
```
<br>
<br> Чтобы обновить установку Git, используйте параметр обновления Homebrew:<br><br>

```
brew upgrade git
```

<br><br> Графический установщик для Git на macOS также доступен на [официальном веб-сайте](https://git-scm.com/download/mac) Git.<br><br>
___


## 3.Настройка Git.<br>
Настройте имя и адрес электронной почты перед началом работы с Git. Git присоединяет эти сведения к изменениям и позволяет другим пользователям определить, какие изменения принадлежат авторам.
<br><br>
Выполните следующие команды из командной строки после установки Git, чтобы настроить эти сведения:<br><br>
```
git config --global user.name "<First_name> <Last_name>"
```
<br><br>
```
git config --global user.email "<user_email_address>"
```
<br><br>
___


## 4.Создание Репозитория.<br>
Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием. Для этого следует переместиться в неё и ввести команду ```git-init```. (**Напоминаю вам, что все команды необходимо вводить в консоле/терминале**).
<br>
Например, создайте папку ```first-project``` и сделайте её Git-репозиторием: перейдите в неё с помощью команды ```cd``` и выполните ```git init```.<br>
```BUSH <br>
 $   cd ~/dev/first-project         # перешли в нужную папку

 $   git init                       # создали репозиторий
```
<br><br>

```git init``` выведет сообщение вида ```Initialized empty Git repository in <*ваша папка с проектом*>/.git/``` (англ. «инициализирован пустой Git-репозиторий в ```<*ваша папка*>/.git/»```). В подпапке ```.git``` Git будет хранить всю служебную информацию.<br>

Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку ```.git```.<br><br>
```BASH <br>
$ cd <папка с репозиторием>         # перешли в папку

$ rm -rf .git                       # удалили подпапку .git <br>
```
Разберём подробнее, что такое ```-rf```: <bt>
..* ключ ```-r``` (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым; <br>
..* ключ ```-f``` (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».<br>
После инициализации репозитория ```first-project``` запустите команду ```git status``` — она показывает текущее состояние репозитория. <br>
Команда ```git status``` выведет:<br>
..* название текущей ветки: ```On branch master``` или ```On branch main```<br>
..* сообщение о том, что в репозитории ещё нет коммитов: ```No commits yet```;<br>
..* сообщение, которое говорит: «чтобы что-нибудь закоммитить (то есть зафиксировать), нужно сначала это создать» — ```nothing to commit (create/copy files and use "git add" to track)```.<br>
