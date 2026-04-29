# Калькулятор мягких окон для Vercel

Исправленная версия с уменьшенным размером PDF для отправки в Telegram.

## Что есть

- Высота 1 и Высота 2 для наклонных проёмов.
- Площадь считается по большей высоте.
- Чертёж строится как трапеция.
- Молния рисуется с двух сторон при включённой галочке.
- PDF сжимается перед отправкой, чтобы не превышать лимит Vercel.

## Переменные окружения Vercel

Добавьте в Project → Settings → Environment Variables:

```env
TELEGRAM_BOT_TOKEN=ваш_токен
TELEGRAM_CHAT_ID=ваш_chat_id
```

После добавления переменных сделайте Redeploy.

## Проверка

Откройте:

```text
https://ваш-сайт.vercel.app/api/send-telegram
```

Должно быть:

```json
"telegramBotTokenConfigured": true,
"telegramChatIdConfigured": true
```
