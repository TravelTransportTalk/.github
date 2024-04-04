# Еду поболтать (DevDays 2024 Spring)

## Описание
Приложение для поиска собеседников в путешествиях на общественных и не только транспортах (самолёты, поезда, электрички, автобусы).

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
$ <replace BOT_TOKEN in compose.yml>
$ docker compose up -d
```
