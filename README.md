# Mittora-test-task

PHP:

Цель работы:

1) У вас есть csv-файл с разделами и товарами интернет-магазина на 5000 строк.
Необходимо получить информацию из файла и внести информацию в базу данных
интернет-магазина (опционально с проверкой имеющихся позиций и обновления
информации по ней).
Опишите алгоритм решения данной задачи с указание используемых функций и классов.

Ход выполнения:
1. Создаём БД где будем хранить распаршеные данные из .csv файла и подключаемся к ней, файл connect.php
2. Используя встроенные функции fgetcsv() и документацию читаем файл и записываем его данные в БД, предварительно написав проверку(можно добавить и написать другие) файл index.php

2) Опишите реализацию алгоритма двухфакторной авторизации на сайте (желательно
привести хотя бы названия функций, которые будете использовать).

Реализация:
1. Первое, что приходит на ум - это генерация токена в момент авторизации зарегистрированного пользователя, сохранение этого токена в бд(с огранничением по времени жизни) и отправка токена
на почту пользователя, далее ввод токена с почты и если они совпадают, то авторизаия прошла успешно.
Сгенерировать уникальный токен может помочь PHP класс OAuthProvider и его метод OAuthProvider::generateToken
2. Работа с Google API и с Google Authenticator следуя документации

SQL:

Цель работы:

В базе данных есть:
таблица категорий товаров category (id, name) ,
таблица товаров product (id,category_id,name,price),
таблица свойств property (id,name)
таблица значений свойств товаров property_value (product_id,property_id,value)
Необходимо:
Необходимо:
a: получить значения свойств товара, если известно его ID

SELECT value
fROM property_value JOIN product
ON property_value.product_id = product.id
WHERE product.id = 1

b: получить список названий уникальных свойств товара по названию категории

SELECT DISTINCT value
 FROM property_value JOIN product
 ON property_value.product_id = product.id
 JOIN category
 ON product.category_id = category.id
 WHERE category.name = 'electronics'

FRONT:

1) img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 40%;
}
