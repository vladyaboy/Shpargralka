
##### Содержание  
* [Основные команды git](#основные-команды-git)  
* [SSH ключи](#ssh-ключи)   
* [Связываем репозитории](#связываем-репозитории)

## Основные команды git 
`git init` - инициализация репозитория. Репозиторий создается только один раз перед дальнейшей работой.

`git add` - индексирует файлы для дальнейшего их сохранения в commit.

`git status` - отображает состояние рабочего каталога и раздела проиндексированных файлов.

`git log` - отображает историю коммитов и позволяет просматривать и фильтровать её, а также искать конкретные изменения

`git commit` - фиксирует изменеия в репозитории и записывает их как конкретную точку.

`git push` -  позволяет передать изменения из локального репозитория в удалённый.

`git rm` - удаляет отслеживаемых файлы из раздела проиндексированных.



## SSH ключи
SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 

* **Приватный ключ** (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.

* **Публичный ключ** (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.

#### Основные команды

`$ ls -la .ssh/` - вывод файлов чтобы проверить есть ли сгенерированные ключи.


Для генерации SSH-пары можно использовать программу `ssh-keygen`. Откройте терминал и введите следующую команду.

```
 $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
```
Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования `ed25519`. Ничего страшного: используйте другой алгоритм - `rsa`.

 ```
$ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
 ```

### Связываем репозитории

`git remote add` - данная команда поможет связать локальный репозиторий с репозиторием, заранее подготовленным на платформе [GitHub](github.com) созданным уже у тебя на аккаунте.


Откройте консоль, перейдите в каталог локального репозитория и введите команду `git remote add` с названием ветки `origin` и скопированной зараннее ссылкой с вашего удаленного репозитория на гитхабе.

Для SSH
```
$ cd ~/dev/first-project
$ git remote add origin git@github.com:ИМЯ_АККАУНТА/first-project.git 
```

Чтобы убедиться, что связка репозиториев сработала, введите команду `git remote -v`
