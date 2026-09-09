# Готовый BBCode шаблон для описания профиля Shikimori

Скопируйте приведённый ниже код целиком и вставьте его в поле **«О себе»** в настройках профиля Shikimori.

> [!NOTE]
> Для корректной работы интерактивных вкладок и карусели в разделе **«Стиль»** должны быть подключены стили `main.css`, `tabs.css` и `carousel.css`:
> ```css
> @import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/main.css";
> @import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/tabs.css";
> @import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/carousel.css";
> ```

---

## BBCode код для вставки в профиль:

```bbcode
[div=use-tabs --centered --ripple]
[div=b-js-link to-process active data-dynamic=switcher data-switcher=profile_tabs]🎨 О стиле[/div]
[div=b-js-link to-process data-dynamic=switcher data-switcher=profile_tabs]📑 Инструкция: Табы[/div]
[div=b-js-link to-process data-dynamic=switcher data-switcher=profile_tabs]🎠 Инструкция: Карусель[/div]
[div=b-js-link to-process data-dynamic=switcher data-switcher=profile_tabs]🌐 Соцсети[/div]
[div][div]
[center][size=16][b]✨ shiki-style — Современная тёмная тема[/b][/size]
[i]Элегантный тёмный macOS-дизайн для профилей и списков Shikimori[/i][/center]

[hr]

[b]Особенности темы:[/b]
[list]
[*] [b]macOS Dark Glass:[/b] Мягкое матовое стекло, размытие фона и закруглённые карточки.
[*] [b]Адаптивность:[/b] Полная поддержка ПК, планшетов и смартфонов (@media all).
[*] [b]4 готовых стиля:[/b] Original Violet, Ruby Red, Monochrome Noir и Retrowave Neon.
[*] [b]Быстрая настройка:[/b] Все цвета и фоны меняются через переменные :root.
[/list]

[hr]

[center][b]📷 Примеры оформления (Карусель скриншотов):[/b][/center]

[div=u-carousel2 to-process data-dynamic=tabs data-counter]
[div=b-js-link active data-tab-switch]Монохром[/div]
[div=b-js-link data-tab-switch]Красный[/div]
[div=b-js-link data-tab-switch]Ретровейв[/div]
[div=u-carousel-inner]
[div data-tab][img w=700]https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/b%26w-style.gif[/img][center][size=11][i]Монохромный стиль (B&W Noir)[/i][/size][/center][/div]
[div=hidden data-tab][img w=700]https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/red-style.gif[/img][center][size=11][i]Красный рубиновый стиль (Ruby Red)[/i][/size][/center][/div]
[div=hidden data-tab][img w=700]https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/img/retrowave.gif[/img][center][size=11][i]Ретровейв стиль (Synthwave Neon)[/i][/size][/center][/div]
[/div]
[/div]

[hr]

[b]⚙️ Как установить тему на свой профиль:[/b]
[list]
[*] Откройте [b]Настройки[/b] профиля ➔ раздел [b]«Стиль»[/b].
[*] Вставьте базовый стиль:
[code=css]@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/main.css";[/code]
[*] Для готового цветового пресета добавьте вторую строку импорта:
[code=css]/* Красная тема (Ruby) */
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/red.css";

/* Чёрно-белая тема (Noir) */
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/monochrome.css";

/* Ретровейв тема (Neon) */
@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/retrowave.css";[/code]
[*] Нажмите кнопку [b]«Сохранить»[/b].
[/list]

[spoiler=🎨 Как изменить палитру вручную (переменные :root)][code=css]@media all {
  :root, html, body, .p-profiles, .p-profiles-show, .l-page, #profiles_show {
    --bg-image: url("прямая_ссылка_на_фон.gif") !important;
    --color-primary: #ff2a85 !important;
    --color-accent: #ff2a85 !important;
    --color-accent-rgb: 255, 42, 133 !important;
    --color-accent-light: #00f0ff !important;
    --color-accent-light-rgb: 0, 240, 255 !important;
    --color-link: #00f0ff !important;
  }
}[/code][/spoiler]
[/div][div]
[center][size=16][b]📑 Модуль табов (BBCode Tabs)[/b][/size]
[i]Интерактивные переключаемые вкладки в профиле на чистом CSS[/i][/center]

[hr]

[b]1. Подключение стилей:[/b]
Добавьте импорт в [b]Настройки[/b] ➔ [b]«Стиль»[/b]:
[code=css]@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/tabs.css";[/code]

[hr]

[b]2. Шаблон BBCode для копирования:[/b]
[code][div=use-tabs --centered --ripple]
[div=b-js-link to-process active data-dynamic=switcher data-switcher=tabs]Вкладка 1[/div]
[div=b-js-link to-process data-dynamic=switcher data-switcher=tabs]Вкладка 2[/div]
[div=b-js-link to-process data-dynamic=switcher data-switcher=tabs]Вкладка 3[/div]
[div][div]Содержимое первой вкладки[/div]
[div]Содержимое второй вкладки[/div]
[div]Содержимое третьей вкладки[/div][/div]
[/div][/code]

[hr]

[b]3. Важные параметры кнопок переключения:[/b]
[list]
[*] [b]to-process data-dynamic=switcher[/b] — активирует встроенный обработчик кликов движка Shikimori.
[*] [b]data-switcher=название[/b] — уникальное имя группы переключателей (например, [i]data-switcher=profile_tabs[/i]).
[*] [b]active[/b] — класс активной по умолчанию вкладки (задаётся первому табу).
[/list]

[hr]

[b]4. Доступные модификаторы (добавляются в [color=#00f0ff]use-tabs[/color]):[/b]
[list]
[*] [b]--centered[/b] — центрирует кнопки переключения по ширине страницы.
[*] [b]--stretched[/b] — равномерно растягивает кнопки во всю ширину контейнера.
[*] [b]--tabline[/b] — стиль кнопок в виде аккуратных подчеркнутых вкладок без овальных рамок.
[*] [b]--vertical[/b] — вертикальное меню вкладок слева от контента.
[*] [b]--vertical --right[/b] — вертикальное меню вкладок справа от контента.
[*] [b]--ripple[/b] — анимация неоновой световой полоски под активной вкладкой.
[/list]
[/div][div]
[center][size=16][b]🎠 Модуль карусели (BBCode Carousel v2.5.1)[/b][/size]
[i]Слайдер изображений с боковыми стрелками, точками и счётчиком[/i][/center]

[hr]

[b]1. Подключение стилей:[/b]
Добавьте импорт в [b]Настройки[/b] ➔ [b]«Стиль»[/b]:
[code=css]@import "https://raw.githubusercontent.com/sh1ndoo/shiki-style/main/css/carousel.css";[/code]

[hr]

[b]2. Шаблон BBCode для копирования:[/b]
[code][div=u-carousel2 to-process data-dynamic=tabs data-counter]
[div=b-js-link active data-tab-switch]1[/div]
[div=b-js-link data-tab-switch]2[/div]
[div=b-js-link data-tab-switch]3[/div]
[div=u-carousel-inner]
[div data-tab][img w=700]https://ссылка_на_первую_картинку.jpg[/img][/div]
[div=hidden data-tab][img w=700]https://ссылка_на_вторую_картинку.jpg[/img][/div]
[div=hidden data-tab][img w=700]https://ссылка_на_третью_картинку.jpg[/img][/div]
[/div]
[/div][/code]

[hr]

[b]3. Параметры и возможности карусели:[/b]
[list]
[*] [b]data-counter[/b] — отображает стильный стеклянный бейдж со счётчиком (например, [i]1 / 3[/i]) в правом верхнем углу.
[*] [b]data-counter="hover"[/b] — счётчик слайдов проявляется только при наведении мыши.
[*] [b]Боковые стрелки[/b] — кликабельные полупрозрачные зоны по бокам слайда для перелистывания.
[*] [b]Нижние индикаторы[/b] — полоски внизу для мгновенного перехода к нужному слайду.
[*] [b]hidden data-tab[/b] — всем слайдам, кроме первого, обязательно задаётся класс [color=#ff2a85]hidden[/color].
[/list]
[/div][div]
[center][size=16][b]🌐 Мои контакты и социальные сети[/b][/size]
[i]Связь со мной, любимые тайтлы и профили на других платформах[/i][/center]

[hr]

[quote]
[b]🐙 GitHub:[/b] [url=https://github.com/sh1ndoo/shiki-style]sh1ndoo/shiki-style[/url]
[b]✈️ Telegram:[/b] [url=https://t.me/your_telegram]@your_telegram[/url]
[b]👾 Discord:[/b] [color=#00f0ff]username#0000[/color]
[b]🎮 Steam:[/b] [url=https://steamcommunity.com]Профиль Steam[/url]
[b]💬 ВКонтакте:[/b] [url=https://vk.com]vk.com/id[/url]
[/quote]

[hr]

[center][b]⭐ Избранные тайтлы:[/b][/center]
[animes ids=5114,1575,6702,13601 cover_notice=studio columns=4]

[center][size=11][i]Добавляйтесь в друзья или пишите в ЛС — всегда рад общению![/i][/size][/center]
[/div][/div]
[/div]
```
