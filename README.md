# Я не курю — чек-лист

Одностраничный чек-лист, чтобы бросить вейп: ежедневные привычки, план по дням и неделям, экстренная помощь с таймером и дыханием, протокол на случай срыва.

- Работает без интернета и без сборки — один HTML-файл.
- Прогресс сохраняется в `localStorage` браузера.
- Есть тёмная и светлая темы.
- Адаптировано под телефон и компьютер.

## Локальный запуск

Самый простой способ — открыть `index.html` двойным щелчком.

Если нужен локальный сервер:

```bash
python -m http.server 8000
```

Затем открыть http://localhost:8000

## Структура

```
index.html            — само приложение
apple-touch-icon.png  — иконка для «На экран Домой» на iPhone
.nojekyll             — отключает обработку Jekyll на GitHub Pages
```

## Публикация на GitHub Pages

### 1. Создать репозиторий

На github.com: **New repository** → имя, например `quit-vape` → **Public** → **не** добавлять README, .gitignore и лицензию → **Create repository**.

> На бесплатном аккаунте GitHub Pages работает только в публичном репозитории. В приватном нужен GitHub Pro.

### 2. Первый коммит и пуш

В папке проекта:

```bash
cd C:\Users\andre\Dev\Agents\quit-vape

git config user.name "Ваше Имя"
git config user.email "ваш@email"

git commit -m "Initial commit"

git remote add origin https://github.com/<USERNAME>/quit-vape.git
git branch -M main
git push -u origin main
```

При первом пуше Git Credential Manager откроет браузер для входа в GitHub. Пароль от аккаунта не подойдёт — нужен вход через браузер или Personal Access Token.

### 3. Включить GitHub Pages

В репозитории: **Settings** → **Pages** → **Build and deployment**:

- **Source:** Deploy from a branch
- **Branch:** `main`, папка `/ (root)`
- **Save**

Через 1–3 минуты сайт будет доступен по адресу:

```
https://<USERNAME>.github.io/quit-vape/
```

Если репозиторий назвать `<USERNAME>.github.io`, адрес будет без имени репозитория:

```
https://<USERNAME>.github.io/
```

### 4. Открыть на iPhone

Отправить ссылку → открыть в Safari → **Поделиться** → **На экран «Домой»**. Появится иконка, приложение будет открываться без адресной строки.

## Обновления

После изменений:

```bash
git add -A
git commit -m "Update"
git push
```

GitHub Pages пересоберёт сайт автоматически.

## Важно

Прогресс хранится в браузере каждого устройства. У разных людей будут свои отметки — синхронизации между устройствами нет.
