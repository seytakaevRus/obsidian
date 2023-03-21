### Для чего
`git restore` - позволяет восстанавливать файлы/директории в рабочем дереве или в дереве индексации или и там, и там к определенному комиту, по умолчанию используется коммит, на который ссылается `HEAD`.

### Использование
`git restore --worktree example.txt` - восстанавливает `example.txt` в рабочем дереве до того состояния, которое лежит в последнем коммите.
`git restore --staged --worktree example.txt` - восстанавливает `example.txt` в рабочем дереве и дереве индексации до того состояния, которое лежит в последнем коммите.
`git restore --source=HEAD~1 --worktree --staged 666.txt` - восстанавливает `example.txt` в рабочем дереве и дереве индексации до того состояния, которое лежит в первом с конца (предпоследнем) коммите.

> В `VSCode` можно использовать встроенные средства для восстановление файлов. 

---
Теги: #git