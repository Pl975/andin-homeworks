# Домашнее задание к занятию «3.1 Coroutines: легковесные потоки, Thread Pools & Dispatchers»

В качестве результата пришлите ссылки на ваш GitHub-проект в личном кабинете студента на сайте [netology.ru](https://netology.ru).

**Важно**: ознакомьтесь со ссылками, представленными на главной странице [репозитория с домашними заданиями](../README.md).

**Важно**: если у вас что-то не получилось, то оформляйте Issue [по установленным правилам](../report-requirements.md).

## Как сдавать задачи

1. Откройте ваш проект с предыдущего ДЗ (можете брать код с лекции)
1. Сделайте необходимые коммиты
1. Сделайте пуш (удостоверьтесь, что ваш код появился на GitHub)
1. Ссылку на ваш проект отправьте в личном кабинете на сайте [netology.ru](https://netology.ru)
1. Задачи, отмеченные, как необязательные, можно не сдавать, это не повлияет на получение зачета (в этом ДЗ все задачи являются обязательными)

## Задача authorId

### Легенда

Разработчики снова переделали API (они это любят) и сделали следующие сущности:
```kotlin
data class Post(
    val id: Long,
    val authorId: Long,
    val content: String,
    val published: Long,
    val likedByMe: Boolean,
    val likes: Int = 0,
    var attachment: Attachment? = null,
)

data class Attachment(
    val url: String,
    val description: String,
    val type: AttachmentType,
)

data class Comment(
    val id: Long,
    val postId: Long,
    val authorId: Long,
    val content: String,
    val published: Long,
    val likedByMe: Boolean,
    val likes: Int = 0,
)

data class Author(
    val id: Long,
    val name: String,
    val avatar: String,
)
```

Как вы видите, теперь в постах и комментариях нет ни имени автора, ни аватарки.

Сервер с реализацией находится в каталоге [server](server).

Чтобы получить автора, нужно делать запрос на `/api/authors/{id}`, где `{id}` - это идентификатор автора (никакого `getAll` для авторов нет).

### Задача

Используя примеры с лекций, реализуйте любым способом (последовательным, либо с помощью `async`/`await`) получение авторов:
1. Для постов
1. Для комментариев (*необязательная часть*)

Нужно сделать обычный (не Android) проект, в котором реализовать такую последовательность вызовов, в результате которой мы получим коллекцию из постов с авторами и комментариями (комментарии тоже должны быть с авторами - *необязательная часть*).

### Результат

Опубликуйте изменения в виде Pull Request'а в вашем проекте на GitHub.

В качестве результата пришлите ссылку на PR GitHub-проект в личном кабинете студента на сайте [netology.ru](https://netology.ru)