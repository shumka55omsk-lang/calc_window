# Калькулятор мягких окон для Vercel — исправленная версия

## Что исправлено

Ошибка Vercel:

```text
Error: Function Runtimes must have a valid version, for example `now-php@1.0.0`
```

возникала из-за настройки runtime в `vercel.json`.

В этой версии:
- `vercel.json` удалён;
- API работает на стандартном Node.js runtime Vercel;
- в `package.json` добавлено `"type": "module"`;
- Telegram-токен хранится только в Environment Variables.

## Структура

```text
public/index.html
api/send-telegram.js
package.json
.env.example
README.md
```

## Как выложить

1. Залейте содержимое этой папки в GitHub.
2. В Vercel импортируйте репозиторий.
3. В Vercel → Project → Settings → Environment Variables добавьте:

```env
TELEGRAM_BOT_TOKEN=ваш_токен_бота
TELEGRAM_CHAT_ID=ваш_chat_id
```

4. Сделайте Redeploy.

## Проверка API

Откройте:

```text
https://ваш-домен.vercel.app/api/send-telegram
```

Должно показать:

```json
{
  "ok": true,
  "api": "send-telegram",
  "mode": "sendDocument",
  "runtime": "nodejs-default",
  "telegramBotTokenConfigured": true,
  "telegramChatIdConfigured": true
}
```

Если `telegramBotTokenConfigured` или `telegramChatIdConfigured` равны `false`, значит переменные окружения не добавлены или не применился новый деплой.
