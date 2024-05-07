
## GIT FOR ANDROID

### Шаг 1: Установка Termux
1. Скачайте и установите приложение Termux из Google Play Store или F-Droid.

### Шаг 2: Установка Git
``` bash

pkg update
pkg install git
```

### Шаг 3: Настройка Git
Настройте ваше имя пользователя и email в Git:
``` bash

git config --global user.name "Ваше Имя"
git config --global user.email "ваш_email@example.com"
```

### Шаг 4: Создание Personal Access Token (PAT)
1. Войдите в свой аккаунт на GitHub.
2. Перейдите в настройки вашего профиля (Settings).
3. Выберите "Developer settings" -> "Personal access tokens".
4. Нажмите "Generate new token".
5. Установите галочки для нужных разрешений (например, repo).
6. Сохраните сгенерированный токен.

### Шаг 5: Клонирование репозитория
Клонируйте репозиторий, используя HTTPS и ваш PAT:

``` bash

git clone https://username:TOKEN@github.com/username/repository.git
```

Замените `username` на ваше имя пользователя на GitHub, `TOKEN` на ваш PAT, и `repository.git` на имя вашего репозитория.

## GIT FOR PC

### Шаг 1: Установка Git
1. Скачайте Git с официального сайта git-scm.com.
2. Запустите установщик и следуйте инструкциям, выбирая настройки по умолчанию или настраивая по вашему желанию.

### Шаг 2: Настройка Git
Откройте командную строку (CMD) или PowerShell и настройте Git:
``` bash

git config --global user.name "Ваше Имя"
git config --global user.email "ваш_email@example.com"
```

### Шаг 3: Генерация SSH-ключа (опционально)
Если предпочитаете использовать SSH:

``` bash

ssh-keygen -t ed25519 -C "your_email@example.com"
```
Добавьте созданный ключ в ваш аккаунт на GitHub.

### Шаг 4: Клонирование репозитория
Клонируйте репозиторий:

``` bash

git clone URL_РЕПОЗИТОРИЯ
```
Замените `URL_РЕПОЗИТОРИЯ` на актуальный URL вашего репозитория на GitHub.

### Шаг 5: Работа с репозиторием
Используйте стандартные команды Git для работы с вашим репозиторием:
``` bash

git add .
git commit -m "Описание изменений"
git push
```
