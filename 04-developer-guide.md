# Руководство разработчика

**Разделы документации:**
[Главная](index.md) | [Введение](01-intro.md) | [Пользователю](02-user-guide.md) | [Администратору](03-admin-guide.md) | [Разработчику](04-developer-guide.md) | [Справочник и FAQ](05-reference.md)

---

## Назначение интерфейса

Программный интерфейс (API) приложения реализован на Kotlin в виде слоя репозиториев (Repository). Он позволяет выполнять операции с данными без использования UI.

### Основные функции
- `createNotebook()`, `getAllNotebooks()`.
- `createNote()`, `getNotesByNotebook()`.
- `moveNote()`, `deleteNote()`.

## Обращение к программе

Все методы являются `suspend`-функциями для работы в корутинах.

**Пример создания записной книжки:**
```kotlin
val notebook = Notebook(name = "Работа")
val newId = notebookRepo.createNotebook(notebook)
