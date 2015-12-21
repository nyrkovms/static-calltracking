# Статический коллтрекинг
Скрипт подмены номеров для статического коллтрекинга.

### Описание
Этот код подменяет номера телефонов на страницах сайта в зависимости от того, с какого сайта или с какими utm метками пришел посетитель на ваш сайт. Номера для подмены вы задаете самостоятельно. Важно, чтобы у вас была возможность получить статистику звонков на все ваши номера. Благодаря подмене номеров, по статистике звонков вы сможете определить какие источники траффика дают наибольшее количество звонков. 

### Особенности
 * Позволяет задавать несколько номеров для одного источника. 
 * Есть список предопределенных основных источников траффика (органика, соц.сети, контекст).

### Установка
Сохраните скрипт sipuni-calltracking.min.js и подключите его на странице.
```
<script src='/js/sipuni-calltracking.min.js'></script>
```

### Использование
Задайте массив источников и соответсвующие им номера телефонов.
```
<script>
    sipuniCalltracking({
      targets: ['.ct_phone1', 'ct_phone2'],
      default_value: '+79999999999',
      sources: {
        'organic':{'ref':/(google|yandex|rambler|bing|yahoo)/ig},
        'social':{'ref':/(twitter|facebook|linkedin|vk\.com|odnoklassniki)/ig},
        'email':{'utm_source':'email'},
      },
      phones: [
        {'src':['organic', 'social'], 'phone1':'+75555555555', 'phone2': '+79995555555'},
        {'src':'email', 'phone1':'+73333333333', 'phone2': '+79993333333'},
      ]
    });
</script>
```
