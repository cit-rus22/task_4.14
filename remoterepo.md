# Инструкция по работе с Git

---
## Содержание
1. [Главная](./readme.md)
1. [Установка Git на Windows](./install.md)
1. [Настройки по умолчанию](./defaultconfig.md)
1. [Файл .gitignore](./ignore.md)
1. [Создание репозитория](./createrepo.md)
1. [Состояние файлов](./filestatus.md)
1. [Работа с коммитами](./commit.md)
1. [Просмотр истории](./commithistory.md)
1. [Работа с удалённым репозиторием](./remoterepo.md)
1. [Ветвление в Git](gitbranch.md)
---
## Работа с удалённым репозиторием

Так как **git** это распределённая СКВ вы можете работать не только с локальными но и с внешними репозиториеми.

Удалённые репозитории представляют собой версии вашего проекта, сохранённые на внешнем сервере.

Для работы с внешними репозиториями используйте:

```Bash
git remote [<options>]
```

Если вы с клонировали репозитории через http URL то у вас уже имеется ссылка на внешний. В другом случае вы можете добавить её с помощью

```Bash
git remote add [<options>] <name> <address>
```

Для **просмотра подключённых внешних репозиториев** используйте `git remote` без аргументов или `git remote -v` для просмотра адресов на отправку и получение данных от репозитория.

Для **отслеживания веток** используйте `git branch -u <rep/br>` где rep это название репозитория, br название внешней ветки, а branch название локальной ветки. Либо `git branch --set-upstream local_br origin/br` для того что бы указать какая именно локальная ветка будет отслеживать внешнюю ветку.

Для **загрузки данных с внешнего репозитория** используйте `git pull [rep] [branch]`. Если ваши ветки отслеживают внешние, то можете не указывать их при выполнение git pull. По умолчанию вы получите данные со всех отслеживаемых веток.

Для **загрузки веток на новую ветку** используйте `git checkout -b <new_branch_name> <rep/branch>`.

Для **отправки данных на сервер** используйте `git push [<rep>] [<br>]`

Для **удаления внешних веток** используйте `git push origin --delete branch_name`

Для **получения подробной информации о внешнем репозитории** (адреса для отправки и получения, на что указывает HEAD, внешние ветки, локальные ветки настроенные для git pull и локальные ссылки настроенные для git push) `git remote show <remote_name>`

Для **переименования внешнего репозитория** используйте `git remote rename <last_name> <new_name>`

Для **удаления ссылки на внешний репозиторий* используйте `git remote rm <name>`