# Платформа для онлайн-курсов

## Описание проекта
Веб-приложение предназначено для просмотра, регистрации и прохождения онлайн-курсов. Пользователи платформы разделены на три группы с различными правами:

- **Студенты** — могут просматривать список курсов, регистрироваться на них и проходить уроки.
- **Преподаватели** — имеют права студентов, а также могут создавать курсы, добавлять и редактировать материалы уроков.
- **Администраторы** — имеют все права преподавателей и студентов, а также могут удалять курсы, управлять пользователями и назначать роли.

## Функциональность

### 1. Регистрация пользователя
Пользователи могут зарегистрироваться на платформе, указав:
- ФИО
- Электронную почту
- Пароль

Преподавателям и администраторам требуется дополнительное подтверждение учётной записи администратором.

### 2. Логин и логаут
Пользователи могут входить в систему с помощью электронной почты и пароля. После выхода из системы пользователь рассматривается как незарегистрированный.

### 3. Просмотр списка курсов (INDEX)
Все пользователи могут просматривать доступные курсы с возможностью фильтрации по:
- Названию курса
- Преподавателю
- Категориям
- Дате начала
- Уровню сложности

### 4. Создание курсов (CREATE)
Только преподаватели и администраторы могут создавать новые курсы, заполняя информацию о:
- Названии курса
- Категории
- Уровне сложности
- Датах начала и окончания
- Добавляя материалы к урокам

### 5. Просмотр деталей курса (READ)
Все пользователи могут просматривать подробную информацию о курсах, включая:
- Описание
- Список уроков
- Отзывы

Студенты могут также видеть свою статистику по прохождению курсов.

### 6. Редактирование курсов (UPDATE)
- **Преподаватели** могут редактировать курсы, которые они создали, изменяя материалы уроков, описание и сроки.
- **Администраторы** могут редактировать любые курсы и управлять пользователями.

### 7. Удаление курсов (DELETE)
Только администраторы могут удалять курсы с платформы.

## Пользовательские роли и права

| Действие                   | Студент | Преподаватель | Администратор |
|----------------------------|---------|---------------|---------------|
| Регистрация                 | Да      | Да            | Да            |
| Логин / Логаут              | Да      | Да            | Да            |
| Просмотр курсов (INDEX)     | Да      | Да            | Да            |
| Создание курсов (CREATE)    | Нет     | Да            | Да            |
| Просмотр деталей (READ)     | Да      | Да            | Да            |
| Редактирование (UPDATE)     | Нет     | Да (свои)     | Да (все)      |
| Удаление курсов (DELETE)    | Нет     | Нет           | Да            |

## Архитектура проекта

Проект будет реализован на **C#** с использованием **ASP.NET Core** как фреймворка для создания веб-приложения.

### Стек технологий:
- **Backend**: C#, ASP.NET Core
- **Frontend**: Razor Pages или Blazor
- **База данных**: MS SQL Server
- **ORM**: Entity Framework Core

## Описание сущностей

### Пользователь (User)
- **ID**
- **Имя** (Name)
- **Электронная почта** (Email)
- **Пароль** (PasswordHash)
- **Роль** (Role: Student/Teacher/Admin)

### Курс (Course)
- **ID**
- **Название курса** (Title)
- **Описание** (Description)
- **Уровень сложности** (Difficulty)
- **Дата начала** (StartDate)
- **Дата окончания** (EndDate)
- **Преподаватель** (Teacher: ID пользователя)

### Урок (Lesson)
- **ID**
- **Название урока** (Title)
- **Описание** (Description)
- **Контент** (Content)
- **Курс** (Course: ID курса)

## Диаграмма базы данных

Ниже представлена диаграмма базы данных, демонстрирующая связи между сущностями:

![ER-диаграмма](![ER-Dg](https://github.com/user-attachments/assets/eb07eba7-187d-4c5d-bbe2-90067c5a335a)
)
