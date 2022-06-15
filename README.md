# Скачивае фотографий космоса через API

- Программа умеет скачивать фотографии космоса с 3 ресурсов:
  - SpaceX
  - NASA APOD
  - NASA EPIC
- Программа также умеет отправлять эти фотографии в телеграмм канал:
  - одну фотографию при вызове опредленного скрипта
  - фотографии с заданным промежутком

### Как установить

- Создать в корне проекта файл **.env**, указать в нем:
  - токен NASA: **NASA_TOKEN**
  - токен телеграм бота **TELEGRAM_TOKEN**
  - Имя телеграм канал **TELEGRAM_CHANNEL_NAME**
  - Директорию для сохранения фото **IMAGES_DIRECTORY**
  - Интервал отправки фото телеграмм ботом в канал **MESSAGE_INTERVAL**
- Пример в файле **.env.example**
- Python3 должен быть установлен
- Затем используйте `pip` (или `pip3`, еслить есть конфликт с Python2) для установки зависимостей: 
    ```
    pip install -r requirements.txt
    ```

- Рекомендуется использовать [virtualenv/venv](https://docs.python.org/3/library/venv.html) для изоляции проекта.


### Как пользоваться
- Программа содержит 5 скриптов:
  ```fetch_nasa_apod.py``` - скачать фотографии дня с API NASA
  ```fetch_nasa_epic.py``` - скачать фотографии EPIC c API NASA
  ```fetch_spacex_images.py {flight_number}``` - скачать фотографии EPIC c API NASA, flight_number - номер полета, необязательный аргумент
  ```publish_image_to_telegram.py``` - опубликовать любую скаченную фотографию в телеграм канале
  ```publish_scheduled_image_to_telegram.py``` - публиковать скаченные фотографии в телеграм канале с заданным интервалом (по-умолчанию 4 часа), фотографии при этом удаляются. Если они заканчиваются - скачиваются новые.

- Запустить любой скрипт можно через консоль: 
    ``` 
    python3 publish_scheduled_image_to_telegram.py
    ```

### Цель проекта

Код написан в образовательный целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).

