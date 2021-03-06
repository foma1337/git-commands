#### Git — распределённая система контроля версий, которая даёт возможность разработчикам отслеживать изменения в файлах и работать совместно с другими разработчиками. 
#### Каждый раз, когда разработчик сохраняет состояние своего проекта в Git, система запоминает, как выглядит каждый файл в этот момент, и сохраняет ссылку на этот снимок.

#### GitHub — сервис онлайн-хостинга репозиториев.

#### Ссылки:
1. [Git Book](https://git-scm.com/book/ru/v2)
2. [Git How To](https://githowto.com/ru)

#### Первоначальная настройка (выполняется один раз)
Установить/изменить имя пользователя

    git config --global user.name "Ваше Имя"
    
Установить/изменить email пользователя

    git config --global user.email ваша@почта.com

Посмотреть значения

    git config --global user.name 
    git config --global user.email
    
--global (для пользователя) / --system (на всю систему) / без аргумента (на конкретный проект)

#### Создание гит репозитория (инициализация). Проект будет находиться под версионным контролем
Перейти в папку с проектом
    
    cd путь_к_папке

Выполнить команду

    git init

Проверить текущее состояние репозитория

    git status
    
Добавление файлов под версионный контроль / Индексация изменённых файлов
Имена файлов, которые не должны попадать под версионный контроль необходимо поместить в .gitignore файл

    git add имя_файла - добавление одного файла
    git add имя_папки/ - добавление папки со всем ее содержимым
    git add * - добавит все новые  / измененные файлы
    

Фиксация изменений (сохранение состояния)
В коммит попадут (будут сохранены) только файлы, которые были проиндексированы командой git add 
    
    git commit -m "сообщение коммита"
    git commit -a "сообщение коммита" - аналогично командам (git add * , git commit -m "сообщение коммита")
    
Добавление удалённых репозиториев
    
    git remote add <имя> <url>, например git remote add origin https://github.com/web-ifmo/project.git
    
Отправка изменений в удаленный репозиторий
    
    git push -u <имя> <ветка>, например git push -u origin master
    git push

##### Определения:
1. origin - имя (по умолчанию) удаленного репозитория (git присваивает данное имя удаленному серверу)  
2. master - имя (по умолчанию) ветки
3. HEAD - указатель на текущий коммит в текущей ветке

Получение изменений из удалённого репозитория 

Данную команду принято также выполнять каждый раз перед оправкой изменений в удаленный репозиторий

    git pull

Клонирование существующего гит репозитория

    git clone <url>, например https://github.com/web-ifmo/git-commands.git
    
Просмотр истории коммитов

    git log 
    (q для выхода)
    
Скрытие изменений
 
    git stash - скрытие изменений, возвращение в состояние последнего коммита
    git stash apply - возвращает скрытые изменения
   
Вернуться к предыдущему коммиту (только для просмотра!) 

    git checkout <хэш сумма коммита> 
    git checkout <имя ветки>, например git checkout master  - вернуться в прежнее состояние
    
Вернуться к предыдущему коммиту в новой ветки (для продолжения работы в ней)

    git checkout -b <имя новой ветки> <хэш сумма коммита>

Перейти к желаемому коммиту, отменив все последующие (работает в случае,если не был сделан push этого коммита)

    git reset --hard <хэш сумма коммита> 

Отменить опубликованные коммиты

    git revert <хэш сумма коммита> 

Ветвление:

    git branch - отображает список веток
    git branch <имя ветки> - создание ветки
    git checkout <имя_ветки> - переключение на ветку
    git push origin <имя ветки> - отправить ветку с изменениями в удаленный репозиторий
    git merge <имя другой ветки> - слияние веток
    git branch -d <имя ветки> - удаление ветки из локального репозитория
    git push origin --delete <имя ветки> - удаление ветки из удаленного репозитория
