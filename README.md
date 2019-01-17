# docker-lsyncd
Утилита для односторонней синхронизации локальной папки с папкой на удаленной машине. При удалении файла или папки в локальной папке, в удаленой папке удаление не происходит.
## Эксплуатация
Для начал работы необходимо установить [docker-compose](https://docs.docker.com/compose/install/), сконфигурировать систему и запустить.
### Конфигурирование
1) Переименовать файл lsyncd/lsyncd.config.example в lsyncd.config
2) Задать путь к локальной папке которую необходимо синхронизировать в параметре sync.source
3) Задать хост удаленной машины в параметре sync.host
4) Задать путь к папке на удаленной машине в параметре sync.targetdir
5) Создать папку kyes c ssh ключем для авторизации на удаленной машине, он должен быть без пароля.
### Запуск
Выполнить последовательно команды _docker-compose build_ и _docker-compose up -d_