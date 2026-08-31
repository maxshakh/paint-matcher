# 🎨 Paint Matcher — Image → Hobby Paints

A single-file, offline web tool that analyzes an image and finds the closest matching miniature/model paints across **12 hobby ranges** plus the **RAL Classic** and **FS 595** industrial standards, using the perceptual **ΔE2000** color-difference metric.

> 🇬🇧 English first · 🇷🇺 Русская версия ниже

![License: MIT](https://img.shields.io/badge/license-MIT-blue) ![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen) ![Offline](https://img.shields.io/badge/works-offline-success)

---

## 🇬🇧 English

### What it does
- **Image analysis** — drop/paste an image, choose the number of colors, and get the best-matching paint per brand for each detected color.
- **5×5 eyedropper** — hover/click anywhere on the image to sample an averaged color and add it to a report.
- **Cross-reference table** — for any paint, see the **top-3 closest analogs** in every other range, plus dedicated **RAL Classic / FS 595** standard columns.
- **My stock** — keep a personal inventory of the paints you own (saved offline in your browser). Owned paints are **highlighted** in the cross-reference table, and a **“only in stock”** filter shows just what you already have.
- **ΔE & swatch dialogs** — click a **ΔE** value for a dL/da/db breakdown with a CIELAB legend and a **mixing hint**; click a **swatch** for a 100×100 zoom with full HEX/RGB/LAB.
- **Metallic filter** — a **“use metallics in comparison”** toggle (off by default), because a single HEX can’t represent gloss/reflection. Metallics are flagged explicitly in the data, not guessed.
- **Reorderable / draggable columns** — the order is **saved per range**.
- **UI** — RUS/ENG language switch and Dark/Light/System theme, all persisted. Sticky headers, frozen first column, sortable stock table.

### Supported ranges (14)
**Hobby (12):** Vallejo **Model Color**, **Model Air**, **Game Color**, **Game Air**, **Mecha Color**, **AK Interactive 3rd Gen**, **Citadel**, **Green Stuff World (Maxx Formula)**, **Scale75 (Scalecolor)**, **The Army Painter (Warpaints Fanatic)**, **AMMO Mig ATOM**, **AMMO Mig Acrylic**.
**Standards (2):** **RAL Classic**, **FS 595**.

Together that’s **2,100+ colors** with cross-brand matching by ΔE2000.

### Markers
- **†** after a paint name — the paint is **discontinued** (per manufacturer data).
- Metallics carry an explicit flag in the data and are excluded from matching unless the metallic toggle is on.

### Data quality
- **Names & numbers** come from official manufacturer catalogs.
- **HEX values** come from community-**measured** swatches (paint applied, photographed, averaged) — e.g. Basecoat Lab and Tale of Painters — or from **RAL/RLM/FS** standard bindings for military tones.
- **Metallics** use averaged tones per metal type — treat as guidance and confirm with a dry brush stroke.
- The full source list is on the built-in **Data sources** tab.
- Note: Vallejo **Game Air** was renumbered from `72.7xx` to `76.xxx` in the October 2022 rebrand; this catalog uses the current numbering.

### How to use
1. Open the live page (or the `index.html` file locally).
2. On **Image analysis**, drop/paste an image and click **Analyze**.
3. Switch to **Cross-reference** to explore top-3 analogs for any paint.
4. Add paints you own on **My stock** for in-stock highlighting.

### Editing the catalog
You don’t need to hand-edit the code. Use the companion **Paint Catalog Editor** (`catalog-editor.html`): import this `index.html`, add/edit paints and ranges (bulk CSV, drag-and-drop, in-place edit), and export a ready-to-use `index.html` back.

### Privacy & offline
- 100% **client-side** — no server, no tracking, works fully **offline**.
- Your **stock, theme, language and column order** live only in **your browser** (`localStorage`).
- Share your stock via **⬇️ Export JSON** / **⬆️ Import JSON**.

### Tech
One self-contained `index.html` — HTML, CSS and JavaScript, **no external dependencies**. Just open it in any modern browser.

---

## 🇷🇺 Русский

### Что это
Однофайловый офлайн-инструмент: анализирует изображение и подбирает ближайшие модельные/миниатюрные краски по **12 хобби-линейкам** плюс промышленным стандартам **RAL Classic** и **FS 595**, используя перцептивную метрику цветового различия **ΔE2000**.

### Возможности
- **Анализ изображения** — перетащите/вставьте картинку, выберите число цветов и получите лучший аналог на каждый бренд для каждого выделенного цвета.
- **Пипетка 5×5** — наведите/кликните по изображению, чтобы взять усреднённый цвет и добавить его в отчёт.
- **Таблица соответствий** — для любой краски показывает **топ-3 ближайших аналога** в каждой линейке, плюс отдельные колонки-стандарты **RAL Classic / FS 595**.
- **Мой склад** — личный список имеющихся у вас красок (хранится офлайн в браузере). Краски со склада **подсвечиваются**, а фильтр **«только со склада»** показывает лишь то, что уже есть.
- **Диалоги ΔE и образца** — клик по **ΔE** открывает разбор dL/da/db с легендой CIELAB и **подсказкой по смешиванию**; клик по **образцу** — зум 100×100 с HEX/RGB/LAB.
- **Фильтр металликов** — переключатель **«использовать металлики в сравнении»** (по умолчанию выкл.), т.к. металлик нельзя передать одним HEX. Металлики помечены в данных явным флагом, а не угадываются.
- **Перетаскивание колонок** — порядок **сохраняется по каждой линейке**.
- **Интерфейс** — переключатель языка RUS/ENG и темы Тёмная/Светлая/Системная (всё сохраняется). Закреплённые заголовки, зафиксированная первая колонка, сортируемая таблица склада.

### Поддерживаемые линейки (14)
**Хобби (12):** Vallejo **Model Color**, **Model Air**, **Game Color**, **Game Air**, **Mecha Color**, **AK Interactive 3rd Gen**, **Citadel**, **Green Stuff World (Maxx Formula)**, **Scale75 (Scalecolor)**, **The Army Painter (Warpaints Fanatic)**, **AMMO Mig ATOM**, **AMMO Mig Acrylic**.
**Стандарты (2):** **RAL Classic**, **FS 595**.

Всего — **2100+ цветов** с кросс-бренд подбором по ΔE2000.

### Маркеры
- **†** после названия — краска **снята с производства** (по данным производителя).
- Металлики имеют явный флаг в данных и исключаются из подбора, пока не включён соответствующий переключатель.

### Качество данных
- **Названия и номера** — из официальных каталогов производителей.
- **HEX-значения** — из **измеренных** свотчей сообщества (краска нанесена, сфотографирована, усреднена) — напр. Basecoat Lab и Tale of Painters — либо из привязок к стандартам **RAL/RLM/FS** для военных тонов.
- **Металлики** заданы средними тонами по типу металла — используйте как ориентир и проверяйте сухим мазком.
- Полный список источников — на встроенной вкладке **«Источники данных»**.
- Примечание: Vallejo **Game Air** после ребрендинга в октябре 2022 сменил коды с `72.7xx` на `76.xxx`; каталог использует актуальную нумерацию.

### Как пользоваться
1. Откройте опубликованную страницу (или файл `index.html` локально).
2. На вкладке **«Анализ изображения»** перетащите/вставьте картинку и нажмите **«Анализировать»**.
3. Перейдите в **«Таблицу соответствий»** для топ-3 аналогов любой краски.
4. Добавьте свои краски на вкладке **«Мой склад»** — включится подсветка имеющегося.

### Редактирование каталога
Не нужно править код руками. Используйте отдельный **Редактор каталога** (`catalog-editor.html`): импортируйте этот `index.html`, добавляйте/правьте краски и линейки (массовый CSV, drag-and-drop, правка на месте) и выгружайте готовый `index.html` обратно.

### Приватность и офлайн
- Полностью работает **в браузере** — без сервера и трекинга, **офлайн**.
- Ваши **склад, тема, язык и порядок колонок** хранятся только **в вашем браузере** (`localStorage`).
- Обмен складом — **⬇️ Экспорт JSON** / **⬆️ Импорт JSON**.

### Технологии
Один самодостаточный `index.html` — HTML, CSS и JavaScript, **без внешних зависимостей**. Просто откройте в любом современном браузере.

---

## ⚠️ Disclaimer / Отказ от ответственности
Paint names, numbers and colors are approximate references for guidance only and may differ from the real product. All brand and product names are trademarks of their respective owners; this project is unofficial and unaffiliated.

Названия, номера и цвета красок приведены как ориентировочные справочные данные и могут отличаться от реального продукта. Все названия брендов и продуктов являются товарными знаками их владельцев; проект неофициальный и не аффилирован с производителями.

---

© maxshakh & Opus, 2026 · MIT License
