# Тестовое задание для разработчика C#

## Задача
Реализовать приложение плеер для проигрывания видео файлов по расписанию.

## Технологии
C# net core

## Пример дизайна приложения
![test player](https://github.com/MarketPlayer/HR_csharp_desktop/blob/master/mm_test_video_player.png "Test player")

## Основные требования к плееру
### Требования к расписанию
* Расписание должно содержать в себе список событий, где каждый элемент включает в себя название папки для проигрывания и время начала и окончания его проигрывания
Формат расписания: на каждой строчке одна запись (событие) в формате: 
`hh:mm hh:mm folder_path`
*[время начала] [время завершения] [путь к папке]*
, например:

     10:00 11:00 \Cats    
     10:01 C:\Test\Dogs
* [путь к папке] - может быть абсолютным или относительным. 
* Отностельный путь - относительно файла с расписанием. Который в свою очередь может находиться в любой папке.
* Файл с расписанием должен быть в текстовом формате, чтобы можно было редактировать в текстовом редакторе.
* Расписание должно загружаться с диска по кнопке на форме Load Schedule. С диалоговым окном выбора файла.
* При загрузке расписания нужна проверка, чтобы не было пересекающихся событий, например одно событие в 10:00-11:00, второе с 10-30 до 11-30, в таком случае выдавать ошибку. Но при этом время окончания одного события и время начала второго могут совпадать. 
* При загрузке нового файла расписания плеер должен доиграть текущий файл до конца и после этого начать воспроизведение по новому.
### Алгоритм проигрывания папки
* Файлы из папки должны воспроизводится от начала события до окончания в алфавитном порядке
* Если общая длительность файлов в папке меньше длительности события, то играем файлы по кругу.

## Требования к архитектуре
* Заложить возможность для простой реализации нового движка видео, например если необходимо выбирать движок в зависимости от версии ОС Windows  XP, Windows 10, Ubuntu то должна быть возможность сделать реализацию под новую версию не меняя уже ранее написанный код для управления воспроизведением

## Прочее
Результат выложить на GitHub в свой репозиторий. В README.md указать особенности сборки, запуска, если таковые будут.
