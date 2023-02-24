---
date: 2016-01-08
categories: [it, web]
tags: [CMS, Wordpress, jQuery, JavaScript]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/jquery-not-work-in-wordpress/jquery-not-work-in-wordpress.md
---

# jQuery не работает в WordPress

В статье рассмотрю один вариант, с которым столкнулся сам, когда правильный код jQuery отказывался работать в Wordpress, хотя в Wordpress плагин включен по умолчанию.

Целый день, блин, потратил на поиск небольшой особенности работы Wordpress. Целый день, Карл! Может, это истина в последней инстанции, которую все знают, но я ничего не находил по теме.

Итак, был у меня вот такой код jQuery:

```html
<script type="text/javascript">
  $(document).ready(function() {
    $("#search_input").focus(function() {
      $("#search_input").animate({ width: "100px" });
    });
    $("#search_input").blur(function() {
      $("#search_input").animate({ width: "30px" });
    });
  });
</script>
```

В том же [jsfiddle.net](https:\jsfiddle.net) код проходил на ура, но в Wordpress отказывался работать. Что нужно было сделать?

**Решение.** Нужно было `$` поменять на `jQuery`:

```html
<script type="text/javascript">
  jQuery(document).ready(function() {
    jQuery("#search_input").focus(function() {
      jQuery("#search_input").animate({ width: "100px" });
    });
    jQuery("#search_input").blur(function() {
      jQuery("#search_input").animate({ width: "30px" });
    });
  });
</script>
```

**В чем дело?** Оказывается, что в Wordpress стандартный способ обращения к элементам через `$` отключен, так как другие библиотеки также могут использовать данный механизм обращения к элементам.

Поэтому в Wordpress файл `jquery.js`, который располагается по адресу `[сайт]/wp-includes/js/jquery/jquery.js`, отличается от стандартных версий библиотеки jQuery тем, что в конце файла прописана строчка:

```js
jQuery.noConflict();
```

Эта строчка и отключает работу с элементами страницы через `$`. Поэтому приходится работать через `jQuery`.
