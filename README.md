# Работа с Git и Github

## 1. Проверка наличия установленного Git
В терминале выполнить команду **git --version**
Если Git установлен, появится сообщение о версии программы. Иначе будет сообщение об ошибки.

## 2. Установка Git
Загружаем последнюю версию файла с сайта https://git-scm.com/downloads.
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале две команды: 
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```


``` Js
while(n < 0)
{
    n++;
}
```

## 4. Инициализация репозитория
Для создания нового репозитория используется команда:
```
 git init
 ```
 
 ## 5. Запись изменений репозитория
Прежде чем делать какие либо изменения репозитория необходимо создать *commit* при помощи команд:
* git add или git --all

Добавляет все файлы проекта в наш будущий commit 

* git add <имя_файла>

Усли хотим добавить конкретный файл

* git commit -m "комментарий"

Создаем commit , обязательно указывая комментарий

* git commit -a -m "комментарий"

Комбинированная команда включающая в себя **git add** и **git commit -m** 

Для получения информаци от git о его текущем состоянии используеся команда:
```
git status
```
Для просмотра  разницы между текущим файлом и закоммиченным файлом можно воспользоваться командой:
```
 git diff
 ```

## 6. Просмотр истории коммитов 
Дя вывода на экран истории всех коммитов с их хеш-кодами используется команда
```
git log
```

## 7. Перемещение между сохранениями 
Перемещение от одного коммита к другому:
```
git checkout <первые четыре символа хеш-кода>
```
Вернуться к актуальному состоянию и продолжить работу:
```
git checkout master
```

## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания в реппозитории определенные файлы и папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответсвующие таким файлам или папкам.
Примеры шаблонов:
```
*.log - Все файлы с расширением log будут игнорированы

*.png(jpg) - Все файлы с данным расширением будут игнорированы
```

## 9. Создание веток в Git
По умолчанию имя основной ветки в git - **master** 
Создать ветку командой:
```
git branch <имя новой ветки>
```
Для создания ветки и автоматического переключения на нее используют команды:
```
git checkout -b <название ветки>

git switch -c <название ветки>
```
Список веток в репозитории можно просмотреть  с помощью команды: 
```
git branch
```
Текущая ветка будет отмечена звездочкой: **\*master**

Переключение межу ветками:
```
git switch <название ветки>

git checkout <название ветки>
```
Вернуться к актуальному состоянию и продолжить работу:
```
git checkout master
```

## 10. Слияние веток и разрешение конфликтов
Для слияния веток используется команда:
```
git merge <название ветки которую хотим присоединить>
```
При слиянии одной ветви с другой  файлы  одной ветви могут конфликтовать с изменениями в другой. В этом случае Visual Studio Code позволяет разрешать конфликты, принимая одно или оба изменения. Мы также можем вручную отредактировать результат слияния или игнорировать его. После разрешения конфликта необходимо сделать **commit** слияния.

## 11. Удаление веток
Для удалении веток используется команда:
```
git branch - d <название ветки>
```
В случае если ветвь не полностью будет объединена, удалить ее этой командой не получится, будет выдавать ошибку. Тогда для принудительного удаления нужно будет использовать команду:
```
git branch -D <название ветви>
```
## 12. Работа с удаленными репозиториями
Чтобы добавить новый удаленный репозиторий необходимо выполнить команду:
```
git remote add <Имя удаленного репозитория> <URL- адрес удаленного репозитория>
```
Чтобы автоматически получить изменения из удалённой ветки и слить их со своей текущей используют команду:
```
git pull
```
Когда мы хотим поделиться своими наработками, нам необходимо отправить их в удалённый репозиторий при помощи команды:
```
git push <имя удаленного репозитория> <имя ветки>
```
Для создания копии (удаленного) репозитория применяется команда:
```
git clone <ссылка - HTTPS, SSH, Github CLI>
```
## 13. Работа с удаленными репозиториями на **Github**
Если мы хотите внести свой вклад в чужой проект, но у вас нет доступа на запись к репозиторию, можно использовать рабочий процесс "**fork**"(вилка). Для этого необходимо:

* Переходим к проекту по адрессу AndreyBulgakov19/SCV_Git_PR
* Нажимаем кнопку Fork (вилка)
* По умолчанию вилки называются так же, как и основной репозиторий, при необходимости можно изменить имя
* Добавить описание если требуется
* Выбрать, следует ли копировать в новую вилку только ветвь по умолчанию или все ветви (по умолчанию копируется только ветвь)
* Нажимаем Create fork (создать вилку)

Мы успешно создали вилку репозитория **AndreyBulgakov19/SCV_Git_PR**. Для работы над проектом необходимо клонировать ее на свой компьютер:
* На GitHub переходим к своей вилке репозитория AndreyBulgakov19/SCV_Git_PR
* Над списком файлов нажимаем  Code
* Копируем URL-адрес репозитория
* Вводим git clone и вставляем URL-адрес, скопированный ранее:
```
git clone https://github.com/Ramzesss/SCV_Git_PR.git
```
* Создаем ветвь (git branch, git checkout -b)
* Вносим изменения в проект 
* Фиксируем и сохраняем все изменения (git add, git commit)
* Передаем изменения на Github в удаленный репозиторий (git push)
* Предлагаем изменения кода в чужом репозитории:
```
pull request
```










