# Шпаргалка по Git

## Основные понятия
- `Ветка` - параллельная версия репозитория
- `Коммит` - фиксация изменений в локальный репозиторий
- `Рабочее дерево` - иерархия папок и файлов репозитория, относящихся к проекту
- `Репозиторий` - папка с файлами проекта, изменения в которой записываются и отслеживаются Git

## Основные команды
- `git init` - создать репозиторий
```bash
cd ~/dev/first-project # перешли в нужную папку
git init # создали репозиторий
```
- `rm -rf .git` - «разгитить» папку
```bash
cd ~/dev/first-project # перешли в нужную папку
rm -rf .git # удалили скрытую подпапку .git
```
- `git status` - проверить состояние репозитория
- `git add` - добавить изменённые файлы к коммиту
```bash
git add readme.txt # подготовить файл readme.txt к сохранению в репозитории
git add . # подготовить все файлы текущей папки к сохранению в репозитории
git add --all # подготовить все файлы рабочего дерева к сохранению в репозитории
```
- `git commit` - сохранить подготовленные изменения в репозитории
```bash
git commit -m 'Комментарий к коммиту'
```
- `git log ` - посмотреть историю коммитов
- `git config --global user.name "[имя]"` - установить имя автора для выполняемых коммитов
- `git config --global user.email "email address"` - установить адрес электронной почты автора для выполняемых коммитов

## Работа с удалённым репозиторием на GitHub
### Первичное связывание локального и удалённого репозиториев
1. Связать репозитории
```bash
cd ~/dev/first-project
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
```
`origin` (англ. «источник») — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию.

2. Переименовать основную ветку в локальном репозитории
```bash
git branch -M main
```

3. Связать ветки
```bash
git push -u origin main # Если команда приведёт к ошибке, попробуйте заменить main на master
```
### Синхронизация изменений между локальным на удалённым репозиториями
- `git push` - синхронизировать изменения из локального репозитория на удалённый
```bash
git add .
git commit -m 'COMMENT'
git push # краткая форма, поразумевается текущий удалённый репозиторий и текущая ветка
git push origin main # полная комманда, с указанием удалённого репозитория и ветки
```
- `git pull` - синхронизировать изменения из удалённого репозитория на локальный
