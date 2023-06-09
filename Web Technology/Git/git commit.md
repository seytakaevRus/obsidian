### Для чего
`git commit` - добавляет файлы и папки в дерево коммитов.

### Использование
`git commit` - открывает редактор, где можно указать сообщение для коммита (если задать в `edition` `"code --wait"`, то будет открыт VSCode). 
`git commit -m "Initial commit"` - создаёт коммит с переданным сообщением.
`git commit -am "Message"` - изменения не попадают в индекс, а создаётся сразу коммит.
`git commit --amend -m "Some message"` - изменение последнего коммита.

### Изменение последнего коммита
1. Делаем изменения и индексируем их (можно не индексировать изменения, если добавить флаг `-a`);
2. Пишем `git commit --amend -m "Some message"` ;
3. Последний коммит удаляется и создаётся новый коммит с изменениями и сообщением.

> Хорошей практикой является использования в сообщениях коммита либо Present Simple, либо Past Simple, всё зависит от кампании.

> В `VSCode` можно использовать встроенные средства для создания коммитов.

---
Теги: #git