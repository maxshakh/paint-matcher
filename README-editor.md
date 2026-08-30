# 🎨 Paint Catalog Editor

A single-file, offline companion tool for **[Paint Matcher](../)**. Edit the paint catalog visually — add/rename/reorder ranges and paints, bulk-import CSV, and export a **ready-to-use `index.html`** back. No hand-editing of code.

> 🇬🇧 English first · 🇷🇺 Русская версия ниже

![License: MIT](https://img.shields.io/badge/license-MIT-blue) ![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen) ![Offline](https://img.shields.io/badge/works-offline-success)

---

## 🇬🇧 English

### Why
Paint Matcher stores its whole catalog inside `index.html` (a `const PAINTS = {…}` block). Hand-editing 200 KB of data is error-prone. This editor gives a safe visual UI and writes the changes back **surgically** — it replaces only the data block and keeps everything else (favicon, i18n, all logic) intact.

### Workflow
1. **Import** your `index.html` (📁 *Load index.html*). The editor extracts the `PAINTS` block and recognizes the flags (metallic `,1`, discontinued `†`).
2. **Edit** in a two-panel UI:
   - **Ranges** (left): add / rename / delete, mark as *standard* (RAL/FS are excluded from the metallic filter), **drag ⠿ to reorder**.
   - **Paints** (right): sortable + filterable table; **in-place edit** (✏️ keeps the paint in its position), delete (✕), **drag ⠿ to reorder** rows.
   - **Add / edit form** with a color picker + HEX, and **metallic** / **discontinued †** checkboxes.
   - **Live validation**: bad HEX, duplicate codes/names per range.
3. **Export** — **⬇️ Download ready index.html** (only the data block is replaced), or **📋 Copy PAINTS block**, or **⬇️ JSON backup**.

### Bulk CSV import
Open **📄 Import CSV into range** and paste a table or load a `.csv`.

**Column format** (delimiter = comma, semicolon or tab; header row auto-detected):

| # | Column | Notes |
|---|--------|-------|
| 1 | Name | required |
| 2 | Code | required |
| 3 | HEX | `#RRGGBB` (the `#` is optional) |
| 4 | metallic | `1` / `yes` / `true` — else empty |
| 5 | discontinued | `1` / `yes` / `true` — else empty (a trailing `†` in the name also works) |

**Example**
```csv
Name,Code,HEX,metal,disc
Silver,70.997,#A8AAAD,1,
Old Blue,X-02,#2244AA,,1
Flat Red,70.957,A12B29,,
```

Options: import into an existing range or a **new** one, skip duplicate codes, live 5-row preview.

### Export a range to CSV
**⬇️ Range → CSV** exports the current range in the **exact same format** as the importer — a perfect round-trip for editing in Excel/Sheets and re-importing.

### Import options
- **index.html** (recommended) — gives you a ready file back on export.
- **PAINTS block** — paste `const PAINTS = {…}` or just the object.
- **JSON** — editor’s own backup format.
- **CSV** — bulk into a range.
- **Start blank** — build a catalog from scratch.

### Data format it writes
- normal: `["White","70.951","#FFFFFF"]`
- metallic: `["Silver","70.997","#A8AAAD",1]`
- discontinued: `["…Opt.1 †","A.MIG-0001","#353D26"]`
- combo: `["Metallic Red †","A.MIG-0188","#C13828",1]`

### Privacy & offline
100% **client-side**, no server. The session (catalog + language + theme) is cached in `localStorage`; the source `index.html` is not persisted (re-import it to get a ready file back).

### Tech
One self-contained `catalog-editor.html`, **no dependencies**, RUS/ENG + Dark/Light theme.

---

## 🇷🇺 Русский

### Зачем
Paint Matcher хранит весь каталог внутри `index.html` (блок `const PAINTS = {…}`). Править вручную 200 КБ данных — легко ошибиться. Редактор даёт безопасный визуальный интерфейс и вписывает изменения **хирургически** — заменяет только блок данных, сохраняя всё остальное (favicon, i18n, всю логику).

### Рабочий цикл
1. **Импорт** вашего `index.html` (📁 *Загрузить index.html*). Редактор извлекает блок `PAINTS` и распознаёт флаги (металлик `,1`, снятие с производства `†`).
2. **Редактирование** в двухпанельном UI:
   - **Линейки** (слева): добавить / переименовать / удалить, отметить как *стандарт* (RAL/FS — без металлик-фильтра), **перетаскивание ⠿ для порядка**.
   - **Краски** (справа): таблица с сортировкой и фильтром; **правка на месте** (✏️ сохраняет позицию краски), удаление (✕), **перетаскивание ⠿ строк**.
   - **Форма добавления/правки** с пипеткой цвета + HEX и чекбоксами **металлик** / **снята с пр-ва †**.
   - **Живая валидация**: битый HEX, дубли кодов/названий в линейке.
3. **Экспорт** — **⬇️ Скачать готовый index.html** (заменяется только блок данных), либо **📋 Копировать блок PAINTS**, либо **⬇️ Резервная копия JSON**.

### Массовый импорт CSV
Откройте **📄 Импорт CSV в линейку** и вставьте таблицу или загрузите `.csv`.

**Формат столбцов** (разделитель — запятая, точка с запятой или табуляция; строка-заголовок распознаётся автоматически):

| # | Столбец | Примечание |
|---|---------|-----------|
| 1 | Название | обязательно |
| 2 | Код | обязательно |
| 3 | HEX | `#RRGGBB` (символ `#` необязателен) |
| 4 | металлик | `1` / `yes` / `true` — иначе пусто |
| 5 | снята с пр-ва | `1` / `yes` / `true` — иначе пусто (также работает `†` в конце названия) |

**Пример**
```csv
Название,Код,HEX,metal,disc
Silver,70.997,#A8AAAD,1,
Old Blue,X-02,#2244AA,,1
Flat Red,70.957,A12B29,,
```

Опции: импорт в существующую линейку или в **новую**, пропуск дубликатов кодов, живой предпросмотр 5 строк.

### Экспорт линейки в CSV
**⬇️ Линейка → CSV** выгружает текущую линейку в **точно том же формате**, что понимает импорт — идеальный round-trip: поправили в Excel/Sheets и залили обратно.

### Способы импорта
- **index.html** (рекомендуется) — на выходе получите готовый файл.
- **Блок PAINTS** — вставьте `const PAINTS = {…}` или сам объект.
- **JSON** — собственный формат бэкапа редактора.
- **CSV** — массово в линейку.
- **С нуля** — собрать каталог с чистого листа.

### Формат данных на выходе
- обычная: `["White","70.951","#FFFFFF"]`
- металлик: `["Silver","70.997","#A8AAAD",1]`
- снята с пр-ва: `["…Opt.1 †","A.MIG-0001","#353D26"]`
- комбо: `["Metallic Red †","A.MIG-0188","#C13828",1]`

### Приватность и офлайн
Полностью **в браузере**, без сервера. Сессия (каталог + язык + тема) кэшируется в `localStorage`; исходный `index.html` не сохраняется (переимпортируйте его, чтобы получить готовый файл).

### Технологии
Один самодостаточный `catalog-editor.html`, **без зависимостей**, RUS/ENG + тёмная/светлая тема.

---

## ⚠️ Disclaimer / Отказ от ответственности
This tool edits data only; it does not validate paint accuracy. Always keep a backup of your working `index.html`. Trademarks belong to their respective owners.

Инструмент редактирует только данные и не проверяет достоверность цветов красок. Всегда храните резервную копию рабочего `index.html`. Товарные знаки принадлежат их владельцам.

---

© maxshakh & Opus, 2026 · MIT License
