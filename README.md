# mdsubdlab
# ФИО и Номер группы
Илья Певнев, 253504
# Функциональные требования
- **Пользователь**: Основной объект системы, который может регистрироваться, входить в систему и управлять своим профилем.
- **Роль**: Определяет права доступа пользователей. Каждому пользователю может быть назначена одна или несколько ролей.
- **Товар**: Представляет собой предмет, который может быть куплен пользователями.
- **Корзина**: Место, где пользователи могут временно хранить товары перед покупкой.
- **Отзывы**: Позволяют пользователям оставлять отзывы о товарах.
- **Купоны**: Предоставляют скидки на товары для пользователей.
# Сущности
- **User**:
id: Integer, PK, NOT NULL,
name: varchar(128), NOT NULL,
password: varchar(128), NOT NULL,
email: varchar(128), NOT NULL,
telephone_number: varchar(128), NOT NULL
- **Role**:
id: Integer, PK, NOT NULL,
user_id: Integer, NOT NULL,
permission_id: Integer, NOT NULL,
role_name: varchar(128), NOT NULL
- **Permission**:
id: Integer, NOT NULL,
name: varchar(128), NOT NULL
- **Seller**:
id: Integer, PK, NOT NULL,
user_id: Integer, NOT NULL,
stuff_id: Integer, NOT NULL
- **Buyer**:
id: Integer, PK, NOT NULL,
user_id: Integer, NOT NULL,
cart_id: varchar(128), NOT NULL
- **Stuff**:
id: Integer, PK, NOT NULL,
stuff_id: Integer, NOT NULL,
stuff_name: varchar(128), NOT NULL,
stuff_price_in_USD: Integer, NOT NULL
- **Cart**:
id: Integer, PK, NOT NULL,
buyer_id: Integer, NOT NULL
- **Reviews**:
id: Integer, PK, NOT NULL,
stuff_id: Integer, NOT NULL,
buyer_id: Integer, NOT NULL,
text: varchar(10000), NOT NULL
- **Coupons**:
id: Integer, PK, NOT NULL,
stuff_id: Integer, NOT NULL,
discount_in_percent: Integer, NOT NULL
- **Moderator**:
id: Integer, NOT NULL, PK,
user_id: Integer, NOT NULL


