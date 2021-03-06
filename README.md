# TaskBot

TaskBot - это [Telegram][]-бот для управления задачами.

## Установка

Проект сопровождается файлом [composer.json][], что позволяет использовать 
[Composer][] для его инсталляции и автозагрузки.

Процесс установки бота:
* `git clone https://github.com/Bashka/taskbot.git TaskBotDir`
* `cd TaskBotDir`
* `composer install`
* `cat database/telegrambot.sql database/remarkbot.sql | mysql -uuser -ppass task_bot`
* Зарегистрируйте вашего ногово бота, с помощью [BotFather][]
* Скопируйте файл `config/global.php` в файл `config/local.php` и выполните 
  конфигурацию
* `./start.sh`

## Поддержка

Если у вас возникли сложности или вопросы по использованию пакета, создайте 
[обсуждение][] в данном репозитории или напишите на электронную почту 
<Artur-Mamedbekov@yandex.ru>.

## Документация

Основные команды:
* Метки (`/marks` или `/ms`):
  * `/marks` - список текущих меток
  * `/marks *` - список всех используемых в системе меток
  * `/marks <метка> ...` - установка текущих меток
* Список задач (`/tasks` или `/ts`):
  * `/tasks` - список всех задач, помеченных текущими метками
  * `/tasks <метка> ...` - список всех задач, помеченных данными метками
* Работа с задачей (`/task` или `/t`)
  * `/task <title>` - создание новой задачи. С новой строки можно записать 
    описание задачи. Задаче будут присвоены те метки, которые являлись на момент 
    ее создания текущими для автора
  * `/task <id>` - просмотр задачи
  * `/task <id> t` - редактирование заголовка задачи. С новой строки указывается 
    новый заголовок
  * `/task <id> d` - редактирование описание задачи. С новой строки указывается 
    новое описание
  * `/task <id> m` - редактирование меток задачи. С новой строки указываются 
    новые метки (через пробел)
  * `/task <id> c` - добавление комменария. С новой строки указывается текст 
    комментария
  * `/task <id> s` - подписка на события задачи. С новой строки могут 
    указываться целевые пользователи
  * `/task <id> us` - отписка от событий задачи. С новой строки могут 
    указываться целевые пользователи

Более подробную документацию можно получить по [ссылке][].

[Telegram]: http://telegram.org/
[composer.json]: ./composer.json
[Composer]: http://getcomposer.org/
[BotFather]: https://web.telegram.org/#/im?p=@BotFather
[обсуждение]: https://github.com/Bashka/taskbot/issues
[ссылке]: https://github.com/Bashka/taskbot/wiki
