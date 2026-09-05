# Руководство по кастомизации палитры (Shiki-Style)

В этой теме все ключевые цвета и фоновое изображение вынесены в CSS-переменные блока `:root`. Вы можете легко изменить акцентный цвет (на красный, синий, зелёный и т.д.) или поставить свой фон, не редактируя весь файл стилей.

> [!IMPORTANT]
> **Обязательно используйте обёртку `@media all { ... }`!**  
> Компилятор стилей Shikimori проверяет наличие директивы `@media`. Если её нет, сервер автоматически оборачивает ваш код в `@media only screen and (min-width: 1024px)`, из-за чего кастомизация не будет работать на мобильных устройствах (< 1024px). Обёртка `@media all` гарантирует применение стилей на всех типах устройств (ПК, планшеты, смартфоны).

---

## 1. Полный шаблон `:root` со всеми доступными переменными

Скопируйте этот блок в поле «Стиль» в настройках Shikimori сразу под строчкой `@import` и меняйте нужные значения:

```css
@media all {
  :root, html, body, .p-profiles, .p-profiles-show, .l-page, #profiles_show {
    /* ============================================================
       1. ФОНОВОЕ ИЗОБРАЖЕНИЕ
       ============================================================ */
    /* Вариант А: Использовать готовые картинки из репозитория:
       --bg-image: var(--bg-red) !important;       (красная тема red-style.gif)
       --bg-image: var(--bg-bw) !important;        (чёрно-белая тема b&w-style.gif)
       
       Вариант Б: Прямая ссылка на файл из репозитория (raw):
       --bg-image: url("https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/b&w-style.gif") !important;
       
       Вариант В: Любая внешняя ссылка на картинку (jpg, png, gif) или none: */
    --bg-image: url("https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/b&w-style.gif") !important;

    /* ============================================================
       2. ТЕКСТОВАЯ ПАЛИТРА
       ============================================================ */
    --color-text: #e4e4e9 !important;             /* Основной текст страницы (описания, списки, комментарии) */
    --color-text-primary: #ffffff !important;     /* Самый яркий белый текст (заголовки h1-h6, ник, текст при hover) */
    --color-text-secondary: #c4afd4 !important;   /* Вторичный текст (категории, бейджи, инфо-метки) */
    --color-text-hint: #a1a1aa !important;        /* Приглушённый цвет (подсказки, даты, серые счетчики) */
    --color-text-soft: #ede6f2 !important;        /* Мягкий светлый текст (примеры BBCode, текст активности .action) */
    --color-text-disabled: #636366 !important;    /* Заблокированные и неактивные элементы */

    /* ============================================================
       3. ССЫЛКИ
       ============================================================ */
    --color-link: #c4afd4 !important;             /* Цвет ссылок по умолчанию */
    --color-link-hover: #ffffff !important;       /* Цвет ссылок при наведении */
    --color-link-active: #ffffff !important;      /* Цвет ссылок при нажатии */

    /* ============================================================
       4. ГЛАВНЫЙ АКЦЕНТНЫЙ ЦВЕТ
       ============================================================ */
    --color-primary: #9884a5 !important;          /* Основной цвет темы (кнопки, активные элементы, графики) */
    --color-accent: #9884a5 !important;           /* Дубликат основного акцента (для совместимости) */
    --color-accent-rgb: 152, 132, 165 !important; /* Тот же цвет в формате R, G, B без скобок (отвечает за свечения и полупрозрачные фоны) */

    /* ============================================================
       5. СВЕТЛЫЙ ОТТЕНОК АКЦЕНТА
       ============================================================ */
    --color-accent-light: #c4afd4 !important;     /* Светлый оттенок акцента (градиенты, рамки, подсветка) */
    --color-accent-light-rgb: 196, 175, 212 !important; /* R, G, B светлого акцента (для прозрачных эффектов при hover) */

    /* ============================================================
       6. ПОВЕРХНОСТИ, КАРТОЧКИ И РАМКИ
       ============================================================ */
    --color-background: #121214 !important;       /* Базовый тёмный цвет страницы под подложками */
    --color-surface: #1c1c1e !important;          /* Фон карточек и панелей */
    --color-surface-hover: #2c2c2e !important;    /* Фон карточек при наведении */
    --color-border: rgba(255, 255, 255, 0.08) !important; /* Тонкая полупрозрачная рамка блоков */
    --color-border-hover: rgba(255, 255, 255, 0.15) !important; /* Рамка блоков при наведении */

    /* ============================================================
       7. СИСТЕМНЫЕ ЭЛЕМЕНТЫ ДВИЖКА SHIKIMORI
       ============================================================ */
    --headline-color: #ffffff !important;         /* Цвет текста в полосах разделов */
    --headline-border-color: #9884a5 !important;  /* Акцентная боковая полоска у заголовков разделов */
    --headline-background: #232326 !important;    /* Фон полосы раздела */
    --link-color: #c4afd4 !important;             /* Системный цвет ссылок движка */
    --link-hover-color: #ffffff !important;       /* Системный цвет ссылок движка при hover */
    --background-color: #121214 !important;       /* Системный фон движка */
    --text-color: #e4e4e9 !important;             /* Системный текст движка */
  }
}
```

---

## 2. Пресет «Красная тема» (Autumn Crimson / Ruby)

Готовый код для переключения темы на рубиново-красный акцент со своей фоновой картинкой (подходит для вставки сразу под `@import`):

```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/main.css";

@media all {
  :root, html, body, .p-profiles, .p-profiles-show, .l-page, #profiles_show {
    /* 1. Фоновая картинка (встроенная из репозитория или своя ссылка) */
    --bg-image: var(--bg-red) !important;
    /* Либо прямая ссылка:
       --bg-image: url("https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/red-style.gif") !important; */

    /* 2. Главный красный акцент (кнопки, активные элементы, графики) */
    --color-primary: #e05353 !important;
    --color-accent: #e05353 !important;
    --color-accent-rgb: 224, 83, 83 !important;

    /* 3. Светлый коралловый оттенок (ссылки, подсветка при hover, светлые полосы) */
    --color-accent-light: #fca5a5 !important;
    --color-accent-light-rgb: 252, 165, 165 !important;
    --color-link: #fca5a5 !important;
    --color-text-secondary: #fca5a5 !important;

    /* 4. Заголовки и системный текст */
    --headline-border-color: #e05353 !important;
    --link-color: #fca5a5 !important;
    --color-text-soft: #fceded !important;
  }
}
```

---

## 3. Пресет «Чёрно-белая тема» (Monochrome / Noir)

Полностью монохромное оформление без цветных элементов (чистый белый, серебряный, серый и глубокий тёмный фон).

### Вариант 1: Быстрое подключение через `@import`
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/main.css";
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/monochrome.css";
```

### Вариант 2: Вставка готового кода в поле стиля
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/main.css";

@media all {
  :root, html, body, .p-profiles, .p-profiles-show, .l-page, #profiles_show {
    /* 1. Чёрно-белый фон из репозитория (или прямая ссылка / none) */
    --bg-image: var(--bg-bw) !important;
    /* Либо прямая ссылка:
       --bg-image: url("https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/b&w-style.gif") !important; */

    /* 2. Основной монохромный акцент (белый/платиновый) */
    --color-primary: #ffffff !important;
    --color-accent: #ffffff !important;
    --color-accent-rgb: 255, 255, 255 !important;

    /* 3. Вторичные серые тона (ссылки, подсветка) */
    --color-accent-light: #d4d4d8 !important;
    --color-accent-light-rgb: 212, 212, 216 !important;
    --color-link: #d4d4d8 !important;
    --color-link-hover: #ffffff !important;
    --color-text-secondary: #a1a1aa !important;

    /* 4. Текст и системные элементы */
    --headline-border-color: #ffffff !important;
    --headline-color: #ffffff !important;
    --link-color: #d4d4d8 !important;
    --link-hover-color: #ffffff !important;
    --color-text-soft: #f4f4f5 !important;

    /* 5. Карточки и границы (глубокий чёрный) */
    --color-background: #09090b !important;
    --color-surface: #141416 !important;
    --color-surface-hover: #1f1f22 !important;
    --color-border: rgba(255, 255, 255, 0.12) !important;
    --color-border-hover: rgba(255, 255, 255, 0.28) !important;
  }

  /* Монохромные бейджи статусов аниме (онгоинг, просмотрено и т.д.) */
  html body .b-anime_status_tag, .b-anime_status_tag {
    background-color: rgba(255, 255, 255, 0.08) !important;
    border: 1px solid rgba(255, 255, 255, 0.25) !important;
    color: #e4e4e7 !important;
  }

  /* Опционально: обесцвечивание постеров и аватарок (цвет возвращается при наведении) */
  html body .c-column .image, html body .b-catalog_entry .cover, html body .avatar img,
  .c-column .image, .b-catalog_entry .cover, .avatar img {
    filter: grayscale(100%);
    transition: filter 0.3s ease !important;
  }
  html body .c-column .image:hover, html body .b-catalog_entry .cover:hover, html body .avatar img:hover,
  .c-column .image:hover, .b-catalog_entry .cover:hover, .avatar img:hover {
    filter: grayscale(0%);
  }
}
```

---

## 4. Сброс кеша стилей Shikimori

Shikimori кэширует подключённые через `@import` файлы на своём сервере. Если вы обновляете версию стиля из репозитория, выполните сброс кеша:
1. Перейдите по ссылке: 👉 **[shikimori.one/tests/reset_styles_cache](https://shikimori.one/tests/reset_styles_cache)** (или `.me` / `.io`)
2. Вставьте ссылку на `main.css` и нажмите **Submit**.
3. Перезагрузите страницу профиля с очисткой кеша (`Ctrl + F5` на Windows / `Cmd + Shift + R` на Mac).

