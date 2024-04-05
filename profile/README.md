# Еду поболтать (DevDays 2024 Spring)

## Описание
Приложение для поиска собеседников в путешествиях на общественном и не только транспорте (самолёты, поезда, электрички, автобусы, катера).

Предполагается следующий сценарий использования:

1. Пользователь через телеграм-бота создаёт свою анкету, где вводит свои: никнейм, ФИО и описание интересов. После этого бот выдаёт пользователю его уникальный идентификатор и ссылку на WebUI приложения
2. Через WebUI есть возможность:
   - Создать новое "путешествие", состоящее из:
     - Вида транспорта
     - Даты отправления
     - Пункт отправления
     - Пункта прибытия
     - Времени отправления
     - Кода рейса (опционально)
   - Просмотреть уже существующие путешествия. Из каждый анкеты можно перейти в профиль пользователя в Телеграме для того, чтобы начать общение


## Возможности
1. Регистрация новой анкеты на выбранный рейс
2. Просмотр уже созданных анкет по выбранным направлениям с возможностью фильрации

## Состав команды
- Вильданов Эмир — Frontend Developer
- Фролов Михаил — Fullstack Developer
- Аленькова Юлия — Backend Developer
- Еленский Михаил — DevOps Engineer
- Филонов Всеволод — Backend Developer

## Компоненты системы
- [TravelTalk](https://github.com/TravelTransportTalk/TravelTalk) — WebUI на Streamlit
- [travel-talk-server](https://github.com/TravelTransportTalk/travel-talk-server) — Backend-сервер, написанный на Java + Spring
- [register-bot](https://github.com/TravelTransportTalk/register-bot) — Telegram-бот для быстрой регистрации пользователей

Дополнительно:
- [tf-infra](https://github.com/TravelTransportTalk/tf-infra) — описание инфраструктуры на Terraform
- [k8s-infra](https://github.com/TravelTransportTalk/k8s-infra) — параметры всех системных инструментов внутри кластера

## Инструкция по запуску
### Docker Compose
```
$ git clone https://github.com/TravelTransportTalk/.github travel-talk
$ cd travel-talk
# download data from https://drive.google.com/file/d/1WeRqdW5IQBqlCH6VKS5XPRGnFcpQhAZi/view?usp=sharing
# load data from into table using \copy
$ docker compose --profile db up -d
$ psql -h localhost -p 5435 -WU postgres
  db=# \copy stations_raw
       FROM '/path/to/flat_stations_russia.csv'
       DELIMITER ','
       CSV HEADER;
$ <replace BOT_TOKEN in compose.yml>
$ docker compose --profile all up -d
```
