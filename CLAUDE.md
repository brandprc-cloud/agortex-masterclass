# AI-MASTERCLASS — навигация по проекту

## Что это за проект

Лендинг для практического онлайн-мастер-класса по AI для бизнеса под брендом **Agortex**.
Спикер: Андрей Брезгин (основатель Agortex).

Формат: один `index.html` без фреймворков — CSS и JS inline.
Хостинг: GitHub Pages.

Связь с основным проектом: форма регистрации → webhook → Telegram @mrbrezgin → Twenty CRM (проект CONSULTING) с тегом `source=masterclass-01`.

---

## Структура репозитория

```
AI-MASTERCLASS/
├── CLAUDE.md                  ← этот файл
├── .business/                 ← контент и бизнес-контекст
│   ├── content.md             ← все тексты лендинга (черновик + финал)
│   └── program.md             ← программа мастер-класса (модули, тайминг)
├── plans/                     ← технические планы
│   └── 2026-05-26-landing.md  ← план сборки index.html
└── landing/                   ← деплоится на GitHub Pages
    ├── index.html             ← весь лендинг
    ├── photo.jpg              ← фото спикера (скопировано из CONSULTING)
    └── favicon.svg            ← буква A на #1A2847
```

---

## Дизайн-система (Agortex)

Утверждена 2026-05-25. Источник: `/root/CONSULTING/.business/assets/brand-guidelines.md`

| Элемент        | Цвет      | HEX       |
|----------------|-----------|-----------|
| Фон светлый    | Кремовый  | `#F5EFE0` |
| Тёмные секции  | Тёмно-синий | `#1A2847` |
| Акцент/кнопки  | Золотой   | `#C9A43A` |
| Текст основной | Тёмно-серый | `#2C2C2C` |
| Текст вторич.  | Серый     | `#777777` |
| Карточки       | Белый     | `#FFFFFF` |

Шрифт: **Inter** (Google Fonts), все веса.

Чередование секций:
- Hero → тёмная (`#1A2847`)
- Спикер → тёмная (`#1A2847`)
- Для кого → светлая (`#F5EFE0`)
- До/После → светлая (`#F5EFE0`)
- Программа + CTA → тёмная (`#1A2847`)

---

## Стек и деплой

- Один файл `index.html` (весь CSS и JS inline)
- Хостинг: GitHub Pages
- Отдельный git-репозиторий (не связан с CONSULTING)
- URL: `https://USERNAME.github.io/agortex-masterclass/` или свой домен позже

```bash
# Деплой
cd /root/AI-MASTERCLASS/landing
git init
git add index.html photo.jpg favicon.svg
git commit -m "init: agortex masterclass landing"
git remote add origin https://github.com/USERNAME/agortex-masterclass.git
git push -u origin main
# Settings → Pages → Source: main / root
```

---

## CRM-интеграция с CONSULTING

Форма заявки на лендинге отправляет POST-запрос на webhook.
Тот же бот и CRM, что в проекте CONSULTING.
В теле запроса добавляется поле `source: "masterclass-01"`.
Владелец видит все лиды в одном месте (Twenty CRM).

Webhook-эндпоинт: настраивается отдельно при подключении формы.

---

## Связь с проектом CONSULTING

Данные, взятые из CONSULTING (не дублировать, ссылаться):
- Фото: `/root/CONSULTING/.business/assets/founder-photo.jpg`
- Брендинг: `/root/CONSULTING/.business/assets/brand-guidelines.md`
- Bio спикера: `/root/CONSULTING/.business/site-v2/10-ТЗ-главная.md` секция 5
- Аватар аудитории: `/root/CONSULTING/.business/audience/avatar.md`

---

## Правила работы

1. Один план = одна функция. Планы в папке `plans/`.
2. Тексты — только в `.business/content.md`, не хардкодить в HTML напрямую.
3. После значимых изменений — пушить на GitHub.
4. В конце сессии — рефлексия в `.business/` (опционально).

## Язык

Всегда отвечать на русском языке.
