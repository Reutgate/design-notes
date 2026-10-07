# Design notes — продуктовый дизайн

Пять экранов на React + Vite. Серверная логика и база данных не нужны.

## Запуск для редактирования
Установите Node.js совместимой версии (22.12+).
В терминале из папки проекта:

```sh
npm ci
npm run dev
```

## Сборка
```sh
npm run build
```
Готовый сайт находится в dist/client. На обычном статическом хостинге публикуйте содержимое этой папки.
Дополнительные dist/server и dist/.openai используются только Sites.

## GitHub
Создайте новый репозиторий в GitHub Desktop, скопируйте содержимое этого архива (не внешнюю папку) в папку репозитория, сделайте Commit и Publish repository.
.gitignore исключает node_modules и dist.

## Автоматическая публикация из GitHub
Выберите Vite/Static site в панели хостинга:
- Install command: npm ci
- Build command: npm run build
- Publish directory: dist/client
- Node: 22.12+ (совместимая версия)

## Обычный сервер
Передайте готовые файлы из dist/client в корневую папку сайта.
Веб-сервер должен отдавать index.html, assets и другие файлы.
Данный экспорт рассчитан на корень домена, например https://example.com/.
Для публикации в подпапке требуется изменить base в Vite и пути /assets в App.jsx.

Для GitHub не нужны .git из оригинального проекта, node_modules, учетные данные Sites или project_id. Они не включены.
