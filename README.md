# Тестовое задание для разработчика C#

## Задача
Реализовать приложение плеер для проигрывания видео файлов по расписанию.

## Технологии
WPF, C#.

## Пример дизайна приложения

## Основные требования к плееру
### Требования к расписанию
* Расписание должно содержать в себе список событий, где каждый элемент включает в себя название папки для проигрывания и время начала и окончания его проигрывания
Формат расписания: на каждой строчке одна запись в формате: 
`hh:mm hh:mm folder_path`
*[время начала] [время завершения] [путь к папке]*
, например

     10:00 11:00 \TestFolder    
     11:00 11:30 C:\Test\TestFolder
    
* Расписание должно быть в текстовом формате, чтобы можно было редактировать в текстовом редакторе
* Расписание должно загружаться с диска по кнопке на форме Load Schedule
* При загрузке расписания нужна проверка, чтобы не было пересекающихся событий, например одно событие в 10:00-11:00, второе с 10-30 до 11-30, в таком случае выдавать ошибку. Но при этом время окончания одного события и время начала второго могут совпадать.
* При загрузке расписания плеер должен доиграть текущий файл до конца и после этого начать воспроизведение по новому расписанию
### Алгоритм проигрывания папки
* Файлы из папки должны воспроизводится от начала события до окончания в алфавитном порядке
* Если общая длительность файлов в папке меньше длительности события, то играем файлы по кругу

## Требования к архитектуре
* Заложить возможность для простой реализации нового движка видео, например если необходимо выбирать движок в зависимости от версии ОС Windows  XP, Windows 10 или Ubuntu 16.04, то должна быть возможность сделать реализацию под новую версию не меняя уже ранее написанный код для управления воспроизведением

## Прочее
Результат выложить на GitHub в свой репозиторий. В README.md указать особенности сборки, запуска, если таковые будут.
