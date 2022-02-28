# How I've done my hometask
Делаю форк репозитория и перехожу в созданную папку 

```
$ git clone https://github.com/Kotlin-Polytech/KotlinAsFirst2020
$ cd KotlinAsFirst2020/
```

Добавляю свой репозиторий и загружаю оттуда коммиты

```
$ git remote add upstream-my https://github.com/TheDark1ord/KotlinAsFirst2021
$ git fetch upstream-my
```

Создаю ветку backport и перехожу в нее

```
$ git branch add backport
$ git checkout backport
```

Добавляю в backport все коммиты из моего репозитория

```
$ git cherry-pick d535f3592006b8f2593c9f881d72c05164aadc13...FETCH_HEAD
```

Добавляю репозиторий моего коллеги (Писарик Максим Владславович) и загружаю оттуда коммиты

```
$ git remote add upstream-theirs https://github.com/mmrgnl/KotlinAsFirst2021
$ git fetch upstream-theirs
```

Мерджу этот репозиторий в ветку backport, в случае конфликтов выбираю свою версию

```
$ git merge -X ours upstream-theirs/master
```

Помещаю вывод git remote в отдельный файл и делаю коммит в master

```
$ git remotes -v > remotes
$ git checkout master
$ git add remotes
$ git commit -m "Added remotes"
```
Описываю решение задания в howto.md

По тому же принципу добавляю этот файл в master и делаю push в origin

```
$ git push origin
```

Отправляю решение преподователю
