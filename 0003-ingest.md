# 0003. download vs ingest vs load vs retrieve vs fetch

> 🔧 IT

Рух даних у пайплайні складається з окремих етапів: отримали байти, втягнули в систему, поклали у сховище, дістали, передали іншому сервісу. Кожне дієслово описує свій крок.

## Одним поглядом

| Слово | Значення (UA) | Ключовий нюанс |
|-------|--------------|----------------|
| **download** | завантажити | байти з мережі на диск/буфер |
| **ingest** | прийняти в систему | вхід пайплайну, система «ковтає» |
| **load** | записати в ціль | warehouse, DB, кеш |
| **retrieve** | витягнути | зі свого власного сховища |
| **fetch** | запитати у сервісу | HTTP/API, міжсервісна взаємодія |

---

### Мислимо як інженери

```
SOURCE (cloud, API)
  ↓ download
LANDING ZONE / BUFFER
  ↓ ingest
PIPELINE / STORAGE
  ↓ load
TARGET STORE (DB, cache, index)
  ↓ retrieve / fetch
CONSUMER (API, frontend, ML)
```

> `retrieve` зазвичай каже «дістати для себе», тоді як `fetch` часто означає «попросити інший сервіс».

---

### download — забрати байти

**Суть:** Перемістити файл/байти із зовнішнього джерела на локальний диск, staging bucket або проміжний сторедж.

- завжди про транспорт через мережу
- не торкається бізнес-моделі даних

**В ІТ:**

- download a file from S3
- download an artifact перед деплоєм
- download a dataset для подальшої обробки

**Приклад:** `The client downloads the file from S3 before processing.`

**Як думаємо:** «Звідки → куди фізично переїхали байти?»

---

### ingest — втягнути всередину

**Суть:** Прийняти вхідні дані у систему, щоб pipeline міг їх обробити.

- ключове слово в ETL/ELT, ML, observability
- може бути потоковим або пакетним

**В ІТ:**

- ingest logs із кількох датацентрів
- ingest events у Kafka
- ingest raw data into the data lake

**Приклад:** `The service ingests events from multiple sources and normalizes them.`

**Як думаємо:** «Чи проковтнула система цей вхід?»

---

### load — покласти у ціль

**Суть:** Записати оброблені дані в конкретне сховище або памʼять, де з ними працюватимуть наступні кроки.

- фінальна частина ETL (Extract → Transform → Load)
- часто означає bulk insert, cache warm-up, model loading

**В ІТ:**

- load curated data into the warehouse
- load embeddings into vector storage
- load dataset into GPU memory

**Приклад:** `Processed batches are loaded into the analytics database every hour.`

**Як думаємо:** «Куди саме ми поклали результат?»

---

### retrieve — витягнути те, що вже лежить

**Суть:** Отримати збережені дані назад для власного використання (API, сервіс, скрипт).

- завжди йде зсередини назовні
- зазвичай відповідає на запит користувача або іншої частини системи

**В ІТ:**

- retrieve records from the database
- retrieve cached responses
- retrieve embeddings for ranking

**Приклад:** `The reporting API retrieves daily aggregates from the warehouse.`

**Як думаємо:** «Що зберегли раніше і зараз дістаємо?»

---

### fetch — попросити інший сервіс

**Суть:** Зробити запит до зовнішнього сервісу (частіше HTTP/GraphQL) і забрати відповідь; не обовʼязково довготривале зберігання.

- популярне слово у фронтенді
- звучить легше, ніж `retrieve`, бо наголошує на міжсервісній взаємодії

**В ІТ:**

- frontend fetches user data from the API
- worker fetches secrets from Vault
- script fetches metrics from Prometheus

**Приклад:** `The dashboard fetches fresh metrics from the monitoring API every minute.`

**Як думаємо:** «У кого ми це попросили через мережу?»

---

### Порівняльна таблиця

| Verb | Дія | Де відбувається | Типове питання |
|------|-----|-----------------|----------------|
| download | перемістити байти | зовнішнє джерело → локальний/буфер | `Звідки на диск?` |
| ingest | прийняти в систему | на вході пайплайну | `Чи система зʼїла потік?` |
| load | записати у ціль | warehouse, DB, memory | `Куди поклали результат?` |
| retrieve | дістати назад | зі сховища для себе | `Що вже зберігали і тепер читаємо?` |
| fetch | запросити у сервісу | між сервісами / API | `У кого попросили дані?` |

---

### Один сценарій — повний pipeline

`A collector downloads raw logs from cloud storage, ingests them into the streaming platform, loads normalized batches into the warehouse, the reporting API retrieves aggregated records, and the React app fetches the final report via HTTP.`

---

### Типові помилки

- `retrieve a file from the internet` → треба `download`
- `download data from the database` → потрібно `retrieve` (або `fetch`, якщо через API)
- `ingest data from the database` → `ingest` використовується лише на вході, а не під час читання
- `fetch data into the warehouse` → це `load`, бо мова про запис

---

### Мнемоніка

- download → 📥 файл взяв
- ingest → 🧠 система проковтнула
- load → 📦 поклали в ціль
- retrieve → 📤 забираємо своє
- fetch → 🌐 попросили сусіда

---

## Для картки

> `(...)` — безпечний контекст. `(~...~)` — не перекладати дослівно. `(A|B)` — альтернативи.

| Слово | Запис на картці |
|-------|------|
| **download** | `завантажити` або `завантажити (~з мережі~)` |
| **ingest** | `прийняти (~в систему~)` або `втягнути (in pipeline)` |
| **load** | `записати (~у ціль~)` |
| **retrieve** | `витягнути (~зі сховища~)` |
| **fetch** | `запитати (~в іншого сервісу~)` |
