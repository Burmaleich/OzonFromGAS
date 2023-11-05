# OzonFromGAS 📖
Реализация методов Ozon Seller Api в среде Google Apps Script

### Идентификатор  `1jNkKwjF2fasD2kSn9KvjtcOe-09LepeUS4016TolPomer8oo4bsFkPLt`

# Описание 📝
Проект начат в рамках подготовки материала для информационной платформы [dev.ozon.ru](https://dev.ozon.ru/).  
Библиотека представляет из себя клиент для отправки запросов, адаптированный под выполнение в среде Google Apps Script.
Все методы и типы в ней полностью соответствуют официальной документации, типы сгенерированны автоматически.  
Для того, чтобы поставить галочку за соблюдение принципа разделения ответственности,
облегчить поддержку и исключить путаницу - ничего, кроме того, что есть в документации, в этой библиотеке не будет.
Различные функции-помощники, синтаксический сахар и вообще все, что не касается методов Ozon Seller API,
 будет в [таблице-примере](https://docs.google.com/spreadsheets/d/14fe-AP8gbqROvuZZuV_zETueCSX85S6vX8ynxcabs84/copy).


## Подключение библиотеки к скрипту 🚀  
  1. В редакторе скриптов нажимаем на иконку “+” рядом с пунктом “библиотеки”
  ![link_lib1](https://i.postimg.cc/FF8TFyNY/link-lib-1.png)  
  2. В появившемся окне в поле “Идентификатор скрипта” вводим идентификатор библиотеки `1jNkKwjF2fasD2kSn9KvjtcOe-09LepeUS4016TolPomer8oo4bsFkPLt` и нажимаем кнопку “найти”  
  ![link_lib2](https://i.postimg.cc/5NznXX2n/link-lib-2.png)
  3. Если идентификатор библиотеки введен верно, то увидим следующее окно. Выбираем самую последнюю версию (она необязательно будет 1)  
  ![link_lib3](https://i.postimg.cc/9QtbBsT9/link-lib-3.png)
  4. После подключения к скрипту, в разделе “Библиотеки” появится новый, нужный нам элемент. Значение “OzonApi” говорит о том, что именно через этот объект возможно получить доступ.   
Например, так: `const client = OzonApi.client(keys);`   
  ![link_lib4](https://i.postimg.cc/BnGNHJ8s/link-lib-4.png)

 
## Авторы  
- [@Дмитрий](https://t.me/mityayka1)  
- [@Александр](https://t.me/oshliaer)
## [Чат](https://t.me/+901fuQqcge01MjIy), в котором можно получить поддержку, и [канал](https://t.me/+ITZGIhC4MUljZGEy) про Гугл Таблицы и не только
## Примеры использования  
[![load-products-result.gif](https://i.postimg.cc/Yq3gzZqJ/load-products-result.gif)](https://postimg.cc/8j7j1yvH)
1.Получение списка идентификатор товара
```
    /** Инициализируем апи клиент */
    const client = OzonApi.client(keys);
    const productsIdsListResponse = client.productApiGetProductList({
        filter: {
            /*  Можно отфильтровать по offer_id, чтобы получить другие данные о товаре */
            // offer_id: [''],
            /* или по product_id */
            // product_id: [''],
            /** Здесь фильтр "по видимости", подробнее - https://docs.ozon.ru/api/seller/#operation/ProductAPI_GetProductList */
            visibility: 'ALL',
        },
        limit: 20,
    });
```
2. Получение данных о товарах по списку идентификаторов
```
    /** Инициализируем апи клиент */
    const client = OzonApi.client(keys);
    
    /**Запрашиваем информацию о товарах по полученному списку offer_id */
    const productsInfoListResponse = client.productApiGetProductInfoListV2({
        offer_id: productsOfferIds,
    });
```
Смотри подробности в [таблице](https://docs.google.com/spreadsheets/d/14fe-AP8gbqROvuZZuV_zETueCSX85S6vX8ynxcabs84/copy)  

 
## Поддержка  
Ответы на вопросы и помощь в нашем [чате телеграм](https://t.me/google_sheets_pro)  
 
[![flexbe-logo-2.png](https://i.postimg.cc/HkY2LBc9/flexbe-logo-2.png)](https://postimg.cc/YhPgnNxv)
