# 0005. do vs perform vs execute vs run vs process vs handle vs carry out vs fulfill

> 🔧 IT · 📖 general

Усі ці дієслова описують «виконання чогось», але підкреслюють різні частини шляху: від простого «зроби» до «ми задовольнили вимоги». Щоб не звучати розмито, вирівняємо їх по етапах інженерної роботи.

## Одним поглядом

| Слово | Значення (UA) | Ключовий нюанс |
|-------|--------------|----------------|
| **do** | зробити | будь-яка дія, без деталей механіки |
| **carry out** | виконати | є інструкція або плейбук |
| **perform** | проводити | формальна операція, документація |
| **execute** | виконати | команда/інструкція, низький рівень |
| **run** | запустити | процес, тести, сервіс |
| **process** | обробити | дані через алгоритм |
| **handle** | опрацювати | реакція на подію/помилку |
| **fulfill** | виконати | відповідність вимогам/очікуванням |

---

### Мислимо як інженери

```
INTENT / REQUEST
	↓ do (будь-що взагалі)
PLAN / PROCEDURE
	↓ carry out (зробити за планом)
OPERATION / COMMAND
	↓ perform / execute / run
DATA FLOW
	↓ process (перетворити)
EVENTS / EDGE CASES
	↓ handle (відреагувати)
OUTCOME / AGREEMENT
	↓ fulfill (вимоги виконані)
```

На кожному кроці використовуємо слово, яке найточніше описує дію.

---

### do — просто виконати

**Суть:** Загальне «зробити» без технічних деталей.

- нейтральне, розмовне
- доречне, коли сам факт виконання важливіший за механіку

**В ІТ:**

- do a quick sanity check
- do a dry run
- do the migration if nothing breaks

**Приклад:** `I’ll do the smoke test before we deploy.`

**Як думаємо:** «Просто зробіть дію, будь-яку.»

---

### carry out — реалізувати план

**Суть:** Виконати процедуру або інструкцію, яка вже була затверджена.

- звучить формально, часто в документах
- фокусується на дотриманні плану, а не на технічних деталях

**В ІТ:**

- carry out the deployment plan
- carry out the investigation outlined by security
- carry out the rollback procedure

**Приклад:** `The SRE team carried out the incident playbook exactly as written.`

**Як думаємо:** «Маємо сценарій — просто виконуємо його.»

---

### perform — виконати операцію

**Суть:** Провести формальну, вимірювану дію або перевірку.

- звучить офіційно: звіти, документація, SLA
- зазвичай описує повторювані процедури

**В ІТ:**

- perform validation
- perform a health check
- perform a backup

**Приклад:** `The service performs multiple validation checks before saving data.`

**Як думаємо:** «Виконуємо прописану операцію з чек-листа.»

---

### execute — виконати інструкцію/команду

**Суть:** Запустити конкретну команду, скрипт, SQL, оп-код.

- низькорівневе, технічне
- наголошує на точному дотриманні інструкцій

**В ІТ:**

- execute a SQL query
- execute a shell command
- execution engine executes the DAG node

**Приклад:** `The database executes the migration script inside a transaction.`

**Як думаємо:** «CPU/движок виконав інструкції буквально.»

---

### run — запустити процес

**Суть:** Дати процесу старт і дозволити йому працювати.

- більш розмовне, ніж `execute`
- підходить для тестів, контейнерів, сервісів

**В ІТ:**

- run integration tests
- run the CI pipeline
- run the container locally

**Приклад:** `Run the load tests overnight and share the report.`

**Як думаємо:** «Натисни ▶️ і нехай працює.»

---

### process — обробити дані

**Суть:** Прогнати дані через алгоритм, змінити стан, агрегувати, трансформувати.

- часто про batch/stream pipelines
- описує внутрішню логіку, а не просто запуск

**В ІТ:**

- process incoming events
- process payments
- process uploaded images

**Приклад:** `The worker processes 10k events per second and enriches them.`

**Як думаємо:** «Дані зайшли сирі, вийшли іншими.»

---

### handle — відреагувати на подію

**Суть:** Коректно опрацювати ситуацію (особливо винятки і крайові кейси).

- більше про реакцію, ніж про трансформацію
- часто з’являється в описі API, SDK, вебхуків

**В ІТ:**

- handle errors
- handle retries
- handle user input focus changes

**Приклад:** `The API handles invalid payloads by returning 422 with details.`

**Як думаємо:** «Що робимо, аби не зламатися?»

---

### fulfill — задовольнити вимоги

**Суть:** Показати, що результат відповідає умовам/очікуванням. Не про процес, а про відповідність.

- популярне в продакт/QA контексті
- часто використовується з requirement, promise, SLA

**В ІТ:**

- fulfill acceptance criteria
- fulfill the contract obligations
- fulfill the order (у e-commerce)

**Приклад:** `The new feature fulfills every acceptance criterion from the spec.`

**Як думаємо:** «Чи все, що обіцяли, тепер зроблено?»

---

### Порівняльна таблиця

| Verb | Фокус | Де вживаємо | Ключове питання |
|------|-------|-------------|-----------------|
| do | будь-яка дія | розмовна мова, чат | `Просто зробити щось?` |
| carry out | виконати план | плейбуки, процедури | `Є інструкція?` |
| perform | формальна операція | документація, SLA | `Є стандартна перевірка?` |
| execute | команда/інструкція | SQL, shell, движки | `Яку команду виконуємо?` |
| run | запустити процес | тести, сервіси, скрипти | `Що треба стартувати?` |
| process | трансформувати дані | пайплайни, воркери | `Які дані обробляємо?` |
| handle | відреагувати | API, edge cases | `На що реагуємо?` |
| fulfill | задовольнити вимоги | продакт, QA, SLA | `Чи виконані умови?` |

---

### Один сценарій

`We carried out the deployment plan, running the migration script while the database executed each statement. The service performed validation, handled invalid payloads, and processed the valid ones. After smoke tests were done, we confirmed the feature fulfills all acceptance criteria.`

---

### Типові помилки

- `handle the payment flow` → правильніше `process the payment flow` (бо йдеться про алгоритм, а не виняток).
- `execute the rollout plan` → краще `carry out the rollout plan` (бо це процедура, а не команда).
- `run a SQL query inside the DB engine` → конкретніше `execute a SQL query`.
- `fulfill the script` → `fulfill` не використовується для процесів; кажемо `run/execute the script`.

---

### Мнемоніка

- do → 🙌 просто зроби
- carry out → 📋 план
- perform → 🛠️ процедура
- execute → 🧱 команда
- run → ▶️ старт
- process → 🔄 трансформація
- handle → 🛡️ реакція
- fulfill → ✅ вимога

---

## Для картки

> `(...)` — безпечний контекст. `(~...~)` — не перекладати дослівно. `(A|B)` — альтернативи.

| Слово | Запис на картці |
|-------|------|
| **do** | `зробити (~будь-яка дія~)` |
| **carry out** | `виконати (~за планом/інструкцією~)` |
| **perform** | `провести (~формальна операція~)` |
| **execute** | `виконати (~команду~)` або залишити execute |
| **run** | `запустити (~процес/тести~)` |
| **process** | `обробити (~дані~)` |
| **handle** | `опрацювати (~подію/помилку~)` |
| **fulfill** | `виконати (~вимоги~)` або `справдати (criteria)` |
