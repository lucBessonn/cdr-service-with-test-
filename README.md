# CDR Service

Это приложение для обработки и анализа данных о звонках абонентов, используя концепцию Call Detail Records (CDR) и Usage Detail Records (UDR). Приложение позволяет получать статистику о звонках абонентов по заданным периодам времени, а также обрабатывать данные о звонках для всех абонентов.

## Описание

Приложение предоставляет REST API для взаимодействия с данными CDR. API позволяет получать статистику по звонкам абонентов за определенные годы и месяцы.

### Основные возможности:
- Получение статистики по звонкам для конкретного абонента за определенный период (год/месяц).
- Получение статистики по всем абонентам за указанный период (год/месяц).
- Поддержка фильтрации по типу звонков (входящие, исходящие).
- Возможность работы с базой данных H2 в памяти для хранения данных.

## Структура проекта

Проект состоит из следующих компонентов:
- **model** — модели данных для хранения информации о звонках (CDR) и абонентах (Subscriber).
- **repository** — репозитории для взаимодействия с базой данных.
- **service** — сервисы для обработки логики данных.
- **controller** — REST контроллеры для взаимодействия с клиентом.
- **Application** — основной класс для запуска Spring Boot приложения.

## Установка

Для запуска приложения необходимо установить следующие компоненты:
- Java 17.
- Maven для сборки и управления зависимостями.

### Шаги для запуска:
JAR архив слишком большой, поэтому дублирую ссылку на него здесь
https://disk.yandex.ru/d/6VlXk-8rFL8Lcg
1. Скачайте архив Aplication_with_test и распакуйте его

  в терминале перейдите в каталог с файлом pom.xml и введите команды:

mvn clean install

mvn spring-boot:run



версия с тестами не запустилась на одном компьютере, но запустилась на другом, причина не выявлена, поэтому если версия с тестами не работает, запустите пожалуйста версию без них, скачав архив Aplication_worked.



Приложение будет доступно по адресу http://localhost:8080.

Запрос для одного абонента за месяц
GET http://localhost:8080/api/udr/subscriber/79990001122?year=2025&month=2

Запрос для одного абонента за всё время
GET http://localhost:8080/api/udr/subscriber/79990001122

Запрос по всем абонентам за месяц
GET http://localhost:8080/api/udr/all?year=2024&month=3
