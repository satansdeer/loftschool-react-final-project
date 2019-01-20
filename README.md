# Финальный проект

Вам предстоит самостоятельно написать приложение для заказа такси.

[Пример приложения](https://pensive-gates-d31754.netlify.com/)

Логин: test@test.com
Пароль: 123123

## Работа с сервером

Для получения данных о маршруте и списка доступных адресов - вы можете использовать [сервер](https://puffy-morning.glitch.me/).

Так же на сервере реализована простейшая система авторизации с захардкоженными данными.

Для сервера использован сервис [glitch](https://glitch.com/), так что вы можете взять существующий сервис за основу, сделать его ремикс и улучшить на своё усмотрение. Например добавить регистрацию и хранение данных пользователя.

## Работа с картой

Для работы с картой предлагается использовать сервис [mapbox](https://www.mapbox.com/). Он предоставляют библиотеку для Javascript, её довольно удобно использовать для отображения карты и маршрутов на ней.

[Документация для Jаvascript библиотеки](https://docs.mapbox.com/mapbox-gl-js/api/)

## Задачи

- Как пользователь:

  - Я могу авторизоваться в приложении
  - При неверном логине или пароле я получу ошибку валидации
  - При попытке перейти на любую страницу кроме `/login` я буду перенаправлен обратно на страницу `/login`

- Как авторизованный пользователь:

  - Я имею доступ к странице с картой (`/map`)
  - При незаполненных платёжных данных на странице карты я вижу сообщение о необходимости их заполнить и ссылку на профиль.
  - Я имею доступ к странице профиля (`/profile`)
  - На странице профиля (`/profile`) я могу указать данные банковской карты

    - Поля `cardName`, `cardNumber`, `expDate`, `cvv` обязательны для заполнения
    - Поле `cardName` может содержать только буквы латинского алфавита
    - Поле `cardNumber` может содержать только цифры и должно иметь длину 8 символов.
    - Поле `expDat` должно иметь формат даты
    - Поле `CVV` может содержать только цифры. Состоит из 3 символов.
    - Я получаю оповещение при успешном сохранении данных карты.

  - Я могу выйти из аккаунта нажав кнопку "Выйти".

- Как авторизованный пользователь с указанными платёжными данными:
  - На странице с картой я могу выбрать адрес отправления и прибытия из списка доступных.
  - При указанных адресах отправления и прибытия я могу нажать на кнопку "Выполнить заказ".
    - Карта переместится к точке отправления.
    - Будет построен маршрут от адреса отправления к адресу прибытия.
    - Я получу сообщение об успешно выполненном заказе.
    - Мне будет доступна кнопка выполнения нового заказа.
