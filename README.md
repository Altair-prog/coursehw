# Проект трекера привычек

## Описание проекта
Этот проект представляет собой backend для SPA (single-page application) трекера привычек, вдохновленного книгой Джеймса Клира *«Атомные привычки»*. Трекер позволяет пользователям создавать и управлять привычками, получать напоминания и отслеживать прогресс.

## Функциональность

### Модели
- **Привычка**:
  - Поля:
    - **Пользователь**: создатель привычки.
    - **Место**: место выполнения привычки.
    - **Время**: время выполнения привычки.
    - **Действие**: конкретное действие, представляющее привычку.
    - **Признак приятной привычки**: булево поле, указывающее, является ли привычка приятной (наградой).
    - **Связанная привычка**: связанная привычка, если она есть.
    - **Периодичность**: по умолчанию ежедневная, определяет частоту напоминаний.
    - **Вознаграждение**: способ поощрения пользователя за выполнение.
    - **Время на выполнение**: предположительное время на выполнение привычки, не более 120 секунд.
    - **Публичность**: позволяет делать привычку публичной.
  - Типы:
    - **Полезная привычка**: основное действие, которое пользователь хочет выполнять, с определённой наградой.
    - **Приятная привычка**: приятное действие, которое может выступать в роли награды за выполнение полезной привычки.

### Валидаторы
- Можно указать только одно из полей — **Вознаграждение** или **Связанная привычка**.
- Время выполнения привычки должно быть не более 120 секунд.
- Только приятные привычки могут быть связаны с полезными.
- Приятная привычка не должна иметь собственного вознаграждения или связанной привычки.
- Привычка должна выполняться хотя бы раз в 7 дней.

### Пагинация
- Список привычек выводится с пагинацией по 5 привычек на страницу.

### Права доступа
- Пользователи могут управлять только своими привычками (механизм CRUD).
- Публичные привычки видны всем, но их нельзя редактировать или удалять.

### Эндпоинты
- **Авторизация**:
  - Регистрация
  - Вход
- **Управление привычками**:
  - Просмотр, создание, редактирование и удаление привычек пользователя.
  - Просмотр списка публичных привычек.

### Интеграция
- Интеграция с Telegram для отправки напоминаний в установленное время.

### Безопасность
- Настроен CORS для возможности подключения фронтенда к развернутому серверу.

### Документация
- Автогенерация документации для API, при необходимости — ручное описание специфичных эндпоинтов.

---

## Начало работы

Для локального развертывания проекта:
1. Клонируйте репозиторий.
2. Установите зависимости.
3. Настройте интеграцию с Telegram и CORS.
4. Запустите backend сервер.