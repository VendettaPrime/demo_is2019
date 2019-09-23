# Демо репозиторий для доклада на конференции Infostart Event 2019

Этот репозиторий содержит демо проект, для демонстрации принципов, озвученных на указанной конференции.

## Использование

Для работы статического анализа BSLLS необходимо прописать расположение jar файла в переменной jenkins `BSLLS_PATH`.

Необходимо скопировать файлы и создать 3 репозитория:

1. Каталог `jenkinslib` содержит библиотеку. Необходимо создать репозиторий и прописать в настройках jenkins shared library 
   1. Name = demo-onec-ci-cd
   2. Default version = master
   3. Load implicitly = true
   4. Allow default version to be overridden = true
   5. Source Code Management = git, указать адрес и учетный данные для созданного репозитория библиотеки
2. Каталог `onecprj1` содержит конфигурацию 1с в формате EDT. Необходимо создать репозиторий и
   1. Создать multibranch pipeline задачу, где указать получение исходных кодов из созданного репозитория, указать имя файла `jenkinsfile`
   2. Добавить webhook для репозитория на событие push `https://<myjenkins.server>/project/<myjobname>`
3. Каталог `onecprj2` содержит вторюу конфигурацию 1с в формате EDT с другими настройками. Необходимо повторить действия п.2.

## Лицензирование

Библиотека, находящяя в каталоге `jenkinslib`, используемые ею конфигурационные файлы, опубликованы под лицензией [LGPL v3](LICENSE). Файлы конфигураций (каталоги `onecprj1` и `onecprj2`) - опубликованы для примера, лицензия на них не распространяется.
