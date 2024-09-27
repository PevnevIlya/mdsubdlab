# mdsubdlab
# ФИО и Номер группы
Илья Певнев, 253504
# Функциональные требования
Пользователь может быть продавцом, покупателем, админом или модератором.
Продавец может разместить свой товар на площадке, а также предоставить к нему купоны.
Покупатель может добавлять товар в корзину покупок, оформлять заказ, использовать купоны и писать отзывы.
Модератор может изменять существующие отзывы и товары.
Администратор может то же, что и модератор, но и банить пользователей.
# Сущности
User:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор пользователя.
- **name**: varchar(128), NOT NULL — имя пользователя.
- **password**: varchar(128), NOT NULL — зашифрованный пароль пользователя.
- **email**: varchar(128), NOT NULL — электронная почта пользователя.
- **telephone_number**: varchar(128), NOT NULL — номер телефона пользователя.

Role:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор роли.
- **user_id**: Integer, NOT NULL — идентификатор пользователя, связанного с ролью.
- **permission_id**: Integer, NOT NULL — идентификатор разрешения, связанного с ролью.
- **role_name**: varchar(128), NOT NULL — название роли.

Permission:
- **id**: Integer, NOT NULL — уникальный идентификатор разрешения.
- **name**: varchar(128), NOT NULL — название разрешения.

Seller:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор продавца.
- **user_id**: Integer, NOT NULL — идентификатор пользователя, связанного с продавцом.
- **stuff_id**: Integer, NOT NULL — идентификатор товара, который продает продавец.

Buyer:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор покупателя.
- **user_id**: Integer, NOT NULL — идентификатор пользователя, связанного с покупателем.
- **cart_id**: varchar(128), NOT NULL — идентификатор корзины покупателя.

Stuff:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор товара.
- **stuff_id**: Integer, NOT NULL — идентификатор товара.
- **stuff_name**: varchar(128), NOT NULL — название товара.
- **stuff_price_in_USD**: Integer, NOT NULL — цена товара в долларах США.

Cart:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор корзины.
- **buyer_id**: Integer, NOT NULL — идентификатор покупателя, которому принадлежит корзина.

Reviews:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор отзыва.
- **stuff_id**: Integer, NOT NULL — идентификатор товара, на который оставлен отзыв.
- **buyer_id**: Integer, NOT NULL — идентификатор покупателя, оставившего отзыв.
- **text**: varchar(10000), NOT NULL — текст отзыва.

Coupons:
- **id**: Integer, PK, NOT NULL — уникальный идентификатор купона.
- **stuff_id**: Integer, NOT NULL — идентификатор товара, на который распространяется купон.
- **discount_in_percent**: Integer, NOT NULL — размер скидки в процентах.

Moderator:
- **id**: Integer, NOT NULL, PK — уникальный идентификатор модератора.
- **user_id**: Integer, NOT NULL — идентификатор пользователя, связанного с модератором.

