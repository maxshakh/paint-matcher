# Paint Matcher — Image → Hobby Paints

A single-file, offline web tool that analyzes an image and finds the closest matching miniature/model paints across **8 hobby ranges** plus the **RAL Classic** and **FS 595** industrial standards, using the perceptual **ΔE2000** color-difference metric.

> 🇬🇧 English below · 🇷🇺 Русская версия ниже

---

## 🇬🇧 English

### What it does
- **Image analysis** — drop an image, pick the number of colors, and get the best-matching paint per brand for each detected color.
- **5×5 eyedropper** — hover/click anywhere on the image to sample an averaged color and add it to a report.
- **Cross-reference table** — for any paint, see the **top-3 closest analogs** in every other range, plus dedicated **RAL Classic / FS 595** standard columns.
- **My stock** — keep a personal inventory of the paints you own (saved offline in your browser). Paints you own are **highlighted** in the cross-reference table, so you instantly see what you don't need to buy.
- **ΔE & swatch dialogs** — click a **ΔE** value for a dL/da/db breakdown with a CIELAB legend and a **mixing hint**; click a **swatch** for a 100×100 zoom with full HEX/RGB/LAB.
- **Reorderable columns** — drag table columns; the order is **saved per range**.
- **UI** — RUS/ENG language switch and Dark/Light/System theme, both persisted.

### Supported ranges
Vallejo **Model Color**, **Model Air**, **Game Color**, **Game Air**, **AK Interactive 3rd Gen**, **Citadel**, **The Army Painter (Warpaints Fanatic)**, **Scale75 (Scalecolor)**, **Green Stuff World (Maxx Formula)** — plus **RAL Classic** and **FS 595** standards.

### How to use
1. Open the live page (or the `index.html` file locally).
2. On the **Image analysis** tab, drop/paste an image and click **Analyze**.
3. Switch to **Cross-reference** to explore top-3 analogs for any paint.
4. Add paints you own on the **My stock** tab to get in-stock highlighting.

### Data quality
- **Names & numbers** come from official manufacturer catalogs.
- **HEX values** come from community-**measured** swatches (paint applied, photographed, averaged) or from **RAL/RLM/FS** standard bindings for military tones.
- **Metallics** use averaged tones per metal type — a single HEX can't capture gloss/reflections, so treat them as guidance and always confirm with a dry brush stroke.
- Full source list is on the built-in **Data sources** tab.

### Privacy & offline
- 100% **client-side** — no server, no tracking. Works fully **offline**.
- Your **stock, theme, language and column order** are stored only in **your browser** (`localStorage`).
- Sharing your stock: use **⬇️ Export JSON** and let a friend **⬆️ Import JSON**.

### Tech
A single self-contained `index.html` — HTML, CSS and JavaScript with no external dependencies. Just open it in any modern browser.

---

## 🇷🇺 Русский

### Что это
Однофайловый офлайн-инструмент: анализирует изображение и подбирает ближайшие модельные/миниатюрные краски по **8 хобби-линейкам** плюс промышленным стандартам **RAL Classic** и **FS 595**, используя перцептивную метрику цветового различия **ΔE2000**.

### Возможности
- **Анализ изображения** — перетащите картинку, выберите число цветов и получите лучший аналог на каждый бренд для каждого выделенного цвета.
- **Пипетка 5×5** — наведите/кликните по изображению, чтобы взять усреднённый цвет и добавить его в отчёт.
- **Таблица соответствий** — для любой краски показывает **топ-3 ближайших аналога** в каждой линейке, плюс отдельные колонки-стандарты **RAL Classic / FS 595**.
- **Мой склад** — личный список имеющихся у вас красок (хранится офлайн в браузере). Краски со склада **подсвечиваются** в таблице — сразу видно, что докупать не нужно.
- **Диалоги ΔE и образца** — клик по **ΔE** открывает разбор dL/da/db с легендой CIELAB и **подсказкой по смешиванию**; клик по **образцу** — зум 100×100 с HEX/RGB/LAB.
- **Перетаскивание колонок** — порядок колонок таблицы **сохраняется по каждой линейке**.
- **Интерфейс** — переключатель языка RUS/ENG и темы Тёмная/Светлая/Системная (выбор сохраняется).

### Поддерживаемые линейки
Vallejo **Model Color**, **Model Air**, **Game Color**, **Game Air**, **AK Interactive 3rd Gen**, **Citadel**, **The Army Painter (Warpaints Fanatic)**, **Scale75 (Scalecolor)**, **Green Stuff World (Maxx Formula)** — плюс стандарты **RAL Classic** и **FS 595**.

### Как пользоваться
1. Откройте опубликованную страницу (или файл `index.html` локально).
2. На вкладке **Анализ изображения** перетащите/вставьте картинку и нажмите **Анализировать**.
3. Перейдите в **Таблицу соответствий**, чтобы посмотреть топ-3 аналога для любой краски.
4. Добавьте свои краски на вкладке **Мой склад**, чтобы включить подсветку имеющегося.

### Качество данных
- **Названия и номера** — из официальных каталогов производителей.
- **HEX-значения** — из **измеренных** свотчей сообщества (краска нанесена, сфотографирована, усреднена) либо из привязок к стандартам **RAL/RLM/FS** для военных тонов.
- **Металлики** заданы средними тонами по типу металла — один HEX не передаёт блеск/отражения, поэтому используйте их как ориентир и проверяйте сухим мазком.
- Полный список источников — на встроенной вкладке **Источники данных**.

### Приватность и офлайн
- Полностью работает **в браузере** — без сервера и трекинга. Работает **офлайн**.
- Ваши **склад, тема, язык и порядок колонок** хранятся только **в вашем браузере** (`localStorage`).
- Чтобы поделиться складом: кнопка **⬇️ Экспорт JSON**, друг делает **⬆️ Импорт JSON**.

### Технологии
Один самодостаточный файл `index.html` — HTML, CSS и JavaScript без внешних зависимостей. Просто откройте в любом современном браузере.

---

## Disclaimer / Отказ от ответственности
Paint names, numbers and colors are approximate references for guidance only and may differ from the real product. All brand and product names are trademarks of their respective owners; this project is unofficial and unaffiliated.

Названия, номера и цвета красок приведены как ориентировочные справочные данные и могут отличаться от реального продукта. Все названия брендов и продуктов являются товарными знаками их владельцев; проект неофициальный и не аффилирован с производителями.

---

© maxshakh & Opus, 2026
