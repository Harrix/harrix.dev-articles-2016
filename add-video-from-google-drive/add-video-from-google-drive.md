---
date: 2016-03-13
categories: [it, web]
tags: [Google Drive, Wordpress, Видео]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-video-from-google-drive/add-video-from-google-drive.md
permalink: https://harrix.dev/ru/blog/2016/add-video-from-google-drive/
lang: ru
attribution:
  - {
      author: Google,
      author-site: "https://www.google.com/",
      license: Public domain,
      license-url: "https://en.wikipedia.org/wiki/Public_domain",
      permalink: "https://commons.wikimedia.org/wiki/File:Google_Drive_Logo.svg",
      permalink-date: 2019-06-19,
      name: Google Drive Logo.svg,
    }
---

# Как добавить на сайт видео из Google Drive

![Featured image](featured-image.svg)

Как добавить на сайт видео из Google Drive, например в Wordpress.

Данная инструкция работает в марте 2016 года. Зная, как любит Google менять команды и настройки, то в момент прочтения вами статьи, инструкция может не работать.

Зайдите в Google Drive и найдите там свой файл:

![Файл в Google Drive](img/google-drive_01.png)

_Рисунок 1 — Файл в Google Drive_

Двойным кликом откройте видеофайл. И там перейдите в раздел открытия доступа к файлу:

![Открытый файл](img/google-drive_02.png)

_Рисунок 2 — Открытый файл_

Включайте доступ по ссылке и копируйте ссылку:

![Получение доступа к файлу по ссылке](img/google-drive_03.png)

_Рисунок 3 — Получение доступа к файлу по ссылке_

Потом перейдите по этой ссылке. Лучше всего откройте новую вкладку в режиме инкогнито:

![Открытие ссылки файла](img/google-drive_04.png)

_Рисунок 4 — Открытие ссылки файла_

Там выбирайте кнопку в виде трех точек:

![Переход к командам](img/google-drive_05.png)

_Рисунок 5 — Переход к командам_

И выбирайте команду `Встроить`:

![Команда «Встроить»](img/google-drive_06.png)

_Рисунок 6 — Команда «Встроить»_

И копируйте код вставки вашего видео:

![Код встраивания](img/google-drive_07.png)

_Рисунок 7 — Код встраивания_

Теперь можете вставлять в ваш сайт данный код (например, в новой записи Wordpress в режиме «Текст»).

Обратите внимание, что рекомендую изменить ширину видео на 100% (но можно этого и не делать).

Также, если вы хотите, чтобы вы могли на полный экран видео растянуть, то пропишите:

```html
allowfullscreen="true"
```

Например, у меня получился такой код для вставки:

```html
<iframe
  src="https://drive.google.com/file/d/0B2Z03wQWGPQWRjlPWUQ0dEJUWkE/preview"
  allowfullscreen="true"
  width="100%"
  height="480"
></iframe>
```
