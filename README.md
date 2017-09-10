# askgolos
Поиск по записям Golos.io

# Синтаксис запросов
## Поиск по фразам

Примеры запросов:
* Как купить блокчейн
* Что такое голос


## Точное вхождение
Примеры запросов:
* "How to buy bitcoin"
* "What is steem"
* "Markdown tutorial"

## Поиск по тегам
Примеры запросов:
* tags:life
* tags:steemit


## Поиск по авторам
Примеры запросов:
* author:thekyle
* author:abit
* author:steemit


## Поиск по дате создания
Формат даты для запроса: YYYY-MM-DD. Можно указать период от до в формате [DateStart to DateEnd]

Примеры запросов:
* created:2017-06-02
* created:[2017-05-01 TO 2017-05-31]

## Поиск по количеству голосов/комментариев
Примеры запросов:
Posts with 150 votes:
* net_votes:150
Posts with between 100 and 150 votes
* net_votes:[100 TO 150]
Posts with 50 comments:
* children:50
Posts with between 40 and 50 comments:
* children:[40 TO 50]
Posts with more than 50 comments:
* children:>50
or less than 50:
* children:<50
this also works with votes, less than or equal to 10 votes:
* net_votes:<=10

## Поиск с усилением слов
через крышку указываем усиление ^m
Примеры запросов
* How to mine^2 steem^3

## Исключение и вхождение
+ перед словом - обязательное вхождение в пост, - исключение
Пример запроса:
* cryptocurrency +mining -bitcoin


## Использование логических запросов
Доступны функции AND, OR, and NOT
Пример запроса:
* tags:asksteem AND author:thekyle
* created:2017-06-02 AND net_votes:>=100 AND children:<10



solr: "sudo chown -R 8983:8983 solr/askgolos"

Attaching to askgolos_mongo-connector_1
mongo-connector_1  | /bin/sh: 1: mongo-connector -m mongo:27017 -n steemdb.comment -t http://solr:8983/solr/askgolos -d solr_doc_manager --auto-commit-interval=0 --oplog-ts=/data/oplog.ts -a askgolos -p askgolos: not found
Attaching to askgolos_mongo-connector_1
askgolos_mongo-connector_1 exited with code 127