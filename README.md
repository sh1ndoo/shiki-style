# shiki-style

Кастомная тёмная тема для профилей и страниц [Shikimori](https://shikimori.one) с акцентным цветом `rgb(152, 132, 165)` (`#9884a5`).

## Особенности
- **Тёмная цветовая схема** с высокой непрозрачностью блоков (`rgba(18, 14, 24, 0.96)`)
- **Яркий и контрастный текст** (`#ffffff` для заголовков, `#ede6f2` для основного текста)
- **Акцентный цвет** `#9884a5` / `#c4afd4` вместо всех синих элементов сайта
- **Фон**: чёрно-белые цветы (`b&w-style.gif`)
- **Убрано скрытие истории** (список просмотренного отображается сразу)
- **Убраны RGB-эффекты** и мигающие анимации (статичная аккуратная тень)
- **Полная совместимость с CSS-парсером Shikimori** (обёрнуто в `@media all`, без запрещённых подстрок)

## Установка

### Вариант 1: Через `@import` в настройках стиля Shikimori
В настройках профиля (раздел «Стиль») вставьте строчку:
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/main.css";
```

> **Важно при обновлении**: Shikimori кеширует `@import`. Чтобы применить новую версию стиля после изменений в репозитории, сделайте сброс кеша на странице:  
> 👉 [shikimori.one/tests/reset_styles_cache](https://shikimori.one/tests/reset_styles_cache) (или `.io` / `.me`)  
> Вставьте ссылку на файл `main.css` и нажмите **Submit**.

### Вариант 2: Расширения Stylus / Stylish
Скопируйте всё содержимое файла [`css/main.css`](css/main.css) в пользовательский стиль для домена `shikimori.one`.

## Дополнительные стили

### Вкладки в описании профиля (BBCode Tabs)
Файл [`css/tabs.css`](css/tabs.css) содержит стили для интерактивных вкладок в описании профиля (поддерживает до 30 вкладок, эффекты `--ripple`, режимы `--vertical`, `--tabline`, `--centered`, `--stretched` и цветовые акценты).

Подключение через `@import`:
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/tabs.css";
```

### Карусель изображений (BBCode Carousel v2.5.1)
Файл [`css/carousel.css`](css/carousel.css) содержит стили для интерактивной карусели / слайдера изображений в профиле (поддерживает боковые стрелки, индикаторы слайдов, счётчик `data-counter`, режим постеров `data-posters` и тёмный фон `data-dark`).

Подключение через `@import`:
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/carousel.css";
```

### Красная тема (Ruby / Autumn Crimson)
Файл [`css/red.css`](css/red.css) переводит тему в рубиново-красную палитру с фоном `red-style.gif`.

Подключение через `@import` сразу после основного стиля:
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/red.css";
```

### Монохромная тема (Monochrome / Noir)
Файл [`css/monochrome.css`](css/monochrome.css) переводит тему в строгий чёрно-белый стиль (серебристо-белые акценты, серые ссылки, монохромные статусы и шкалы).

Подключение через `@import` сразу после основного стиля:
```css
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/monochrome.css";
```

## Кастомизация палитры и фона

Все ключевые цвета (акценты, ссылки, текст) и фоновое изображение настраиваются через переменные `:root` с обязательной обёрткой в `@media all`.

Подробное руководство со всеми доступными переменными и готовыми пресетами (**«Красная тема»** и **«Чёрно-белая тема»**) смотрите в файле:
👉 **[CUSTOMIZATION.md](CUSTOMIZATION.md)**


