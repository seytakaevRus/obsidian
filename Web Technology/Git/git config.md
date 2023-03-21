### Для чего
`git config` - настраивает файл конфигурации, так можно настроить почту, отображаемое имя в коде и многое другое. 

### Уровни конфигурации
1. `--local` - настройки задаются для текущего репозитория;
2. `--global` - настройки задаются для всех репозиториев конкретного пользователя;
3. `--system `- настройки задаются для всех пользователей.

### Использование
`git config --global user.name "Ruslan Seit-Akaev"` - задаем отображаемое имя в коде.
`git config --global user.email "iigrem@bk.ru"` - задает почту.
`git config --global core.edition "code --wait"` -   задаёт VSCode как редактор для git.
`git config --global core.autocrlf true/input` - задаёт правильные символа окончания строки для конкретной ОС, причём `true` используется в `Windows`, а `input` в `Mac/Linux`.
`git config --global -e` - открыть файл с конфигурации для области `--global`.
`git config --global alias.lg "log --pretty=format:'%Cgreen%an%Creset committed %Cblue%h%Creset on %cd'"` - задает псевдоним, если ввести `git lg`, то выполнится команда выше.

---
Теги: #git

