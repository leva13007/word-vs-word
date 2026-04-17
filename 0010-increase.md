# 0010. increase vs raise vs rise vs grow vs boost vs improve vs enhance

> 📖 general · 🔧 IT

Усі сім слів пов'язані з рухом угору, але відповідають на різні питання. Головна пастка для UA-мовців: усі перекладаються як "збільшити / зрости / покращити" — але в англійській важливо, хто або що рухається, навмисно чи само собою, і про кількість чи якість. Ще один сюрприз — `raise` і `rise` поводяться як `lay/lie`: одне transitive, інше ні.

## Одним поглядом

| Слово | Значення (UA) | Transitive? | Фокус |
|-------|--------------|-------------|-------|
| **increase** | збільшити(ся) | обидва | число, обсяг — нейтрально |
| **raise** | підвищити | тільки transitive | рівень, планку — свідомо |
| **rise** | зростати | тільки intransitive | число саме йде вгору |
| **grow** | рости | обидва | розмір, органічно, з часом |
| **boost** | підбити, прискорити | тільки transitive | performance, confidence — позитивний спін |
| **improve** | покращити(ся) | обидва | якість або стан, не кількість |
| **enhance** | підсилити, збагатити | тільки transitive | якість або можливості — вже добре, стає ще краще |

---

🧠 Головна логіка

Спочатку задай два питання:

❓ Хто змінюється — хтось активно робить це, чи воно само?

 * Хтось активно робить → transitive: **raise**, **boost**, **increase** (obj), **grow** (obj), **improve** (obj)
 * Само собою → intransitive: **rise**, **grow** (no obj), **increase** (no obj), **improve** (no obj)

❓ Що змінюється — кількість/рівень чи якість?

 * Кількість, обсяг, рівень → **increase / raise / rise / grow / boost**
 * Якість, стан (виправити або покращити) → **improve**
 * Якість або можливості (підсилити те, що вже добре) → **enhance**

---

🔹 1️⃣ increase

📌 Пряме значення:

збільшувати(ся)

📌 Суть:

нейтральна технічна зміна числа або обсягу — вгору; можна і transitive, і intransitive

В ІТ

We increased the timeout from 30s to 60s.
Memory usage increased by 40% after the update.
The team increased test coverage to 85%.

Відчуття:
 * нейтрально, технічно, точно
 * підходить для метрик, чисел, обсягів
 * без емоційного забарвлення

🧠 Для розуміння:

"increase = нейтральне 'стало більше' — можна і зробити, і воно само."

---

🔹 2️⃣ raise

📌 Пряме значення:

підвищити (свідомо)

📌 Суть:

хтось навмисно піднімає рівень або планку — завжди transitive, завжди є агент

В ІТ

We raised the log level to DEBUG.
The team raised the quality bar for code reviews.
They raised the API rate limit to 1000 requests per minute.

Відчуття:
 * активна, свідома дія
 * є той, хто піднімає, і те, що піднімають
 * формально або технічно

🧠 Для розуміння:

"raise = хтось RAISE-дить рівень навмисно."

⚠️ `raise` завжди потребує об'єкта: `❌ The errors raised` → `The error count rose`

---

🔥 raise vs rise

 * `raise the threshold` → я / ми підвищили (transitive)
 * `errors rose during the night` → само зросло (intransitive)

---

🔹 3️⃣ rise

📌 Пряме значення:

зростати (само собою)

📌 Суть:

число або рівень рухається вгору без зовнішнього втручання — завжди intransitive

В ІТ

CPU usage rose to 95% under load.
The number of active users has risen steadily.
Response times rise when the cache is cold.

Відчуття:
 * нейтрально або з нотою занепокоєння
 * акцент: воно само, без агента
 * часто в аналітиці та звітах

🧠 Для розуміння:

"rise = RISE up на власних ногах — ніхто не допомагає."

⚠️ `❌ We rose the limit` → `We raised the limit`

---

🔹 4️⃣ grow

📌 Пряме значення:

рости / вирощувати

📌 Суть:

органічний, поступовий ріст розміру або масштабу — з часом, природно

В ІТ

The user base grew from 10K to 1M over two years.
We need to grow the team before the next phase.
Technical debt grows if you don't address it early.

Відчуття:
 * органічно, поступово
 * масштаб: команда, продукт, база користувачів
 * не для разового стрибка

🧠 Для розуміння:

"grow = як рослина — поступово, з часом."

---

🔥 increase vs grow

 * `increase the timeout` → конкретне технічне число
 * `grow the user base` → масштаб, органічний розвиток

---

🔹 5️⃣ boost

📌 Пряме значення:

прискорити, підбити, дати поштовх

📌 Суть:

активно і позитивно підсилити щось — завжди transitive, завжди позитивне забарвлення

В ІТ

Caching boosted response times by 3x.
The refactoring boosted developer productivity.
A CDN can boost performance for global users.

Відчуття:
 * енергійно, позитивно
 * часто в pitch, технічних блогах, звітах про покращення
 * не вживають про погані речі: `❌ boost errors`

🧠 Для розуміння:

"boost = позитивний ПОШТОВХ — rocket boost."

⚠️ `boost` не для нейтральних або негативних змін

---

🔹 6️⃣ improve

📌 Пряме значення:

покращити(ся)

📌 Суть:

якість, стан або ефективність стає кращою — не про кількість саму по собі

В ІТ

We improved error handling across the service.
Code readability improved after the refactoring.
The new algorithm improved accuracy from 87% to 94%.

Відчуття:
 * фокус на якості або стані, не на числі
 * нейтрально-позитивно
 * широкий контекст

🧠 Для розуміння:

"improve = якість стає КРАЩОЮ — не більшою, а кращою."

⚠️ `❌ improve the number of requests` → `increase the number of requests`
✔ `improve the quality of responses` — якість, не кількість

---

� 7️⃣ enhance

📌 Пряме значення:

підсилити, збагатити, підняти на рівень вище

📌 Суть:

щось вже працює або є хорошим — `enhance` робить це ще ціннішим, потужнішим або виразнішим; завжди transitive

В ІТ

The new UI enhances the user experience.
We enhanced the API with support for pagination and filtering.
The plugin enhances the editor's capabilities.

Відчуття:
 * якісне збагачення, не виправлення
 * підходить для features, UX, security, capabilities
 * більш формальний і «elevated» тон, ніж `improve`

🧠 Для розуміння:

"enhance = вже добре → зробили ЩЕ КРАЩЕ, збагатили."

⚠️ не вживають, коли щось було зламане або погане: `❌ enhance the broken flow` → `fix` або `improve`

---

🔥 improve vs enhance

 * `improve error handling` → воно працювало погано — виправили й покращили
 * `enhance the search experience` → воно вже працювало — збагатили, підняли рівень

---

🔥 boost vs enhance

 * `boost performance` → активний поштовх, часто кількісний (3x faster)
 * `enhance performance` → якісне удосконалення, не обов'язково різкий стрибок

---

🧠 Інженерний хак

| Якщо потрібно сказати… | Використовуй |
|------------------------|-------------|
| число/метрика стала більшою (нейтрально) | `increase` |
| хтось навмисно підвищив рівень | `raise` |
| число само собою зросло | `rise` |
| органічний ріст масштабу з часом | `grow` |
| активний позитивний поштовх | `boost` |
| якість або стан стали кращими (було погано) | `improve` |
| якість або можливості збагатили (вже було добре) | `enhance` |

---

🧩 Один сценарій

> After the optimization sprint, response times improved significantly. Cache hit rate increased from 60% to 90%. We also raised the connection pool limit to handle peak load. Weekly active users grew steadily — from 50K to 120K over three months. A new CDN boosted throughput for international traffic. Meanwhile, error rates rose briefly during the rollout, then dropped back to baseline. The team also enhanced the monitoring dashboard with richer alerting and drill-down capabilities.

---

🚨 Типові помилки

❌ `The errors raised during the night`
✔ `The errors rose during the night` — само зросло → `rise` (intransitive)

❌ `We rose the timeout value`
✔ `We raised the timeout value` — свідомо підвищили → `raise` (transitive)

❌ `improve the number of requests`
✔ `increase the number of requests` — число, не якість → `increase`

❌ `boost the error count` (негативне)
✔ `boost` тільки для позитивних речей; нейтральне → `increase`

❌ `grow the log level from INFO to DEBUG`
✔ `raise the log level` — рівень свідомо підвищується, не "органічно росте"

❌ `enhance the broken authentication flow`
✔ `improve` або `fix` — `enhance` не для того, що зламано або погано працює

---

🧠 Мнемоніка

 * **increase** → IN → нейтральне число IN-creases (технічна зміна)
 * **raise** → RAISE your hand → хтось свідомо піднімає
 * **rise** → RISE and shine → само встає, без допомоги
 * **grow** → GROW slowly → як рослина — органічно, з часом
 * **boost** → rocket BOOST → позитивний поштовх, раптовий
 * **improve** → imPROVE → PRO = краща якість, не більша кількість
 * **enhance** → ENHANCE = ENrich + ADVANCE → збагатити те, що вже є

---

## Для картки

> `(...)` — безпечний контекст. `(~...~)` — не перекладати дослівно. `(A|B)` — альтернативи.

| Слово | Запис на картці |
|-------|------|
| **increase** | `(збільшити(ся) ~число, нейтрально~)` |
| **raise** | `(підвищити ~свідомо, transitive~)` |
| **rise** | `(зростати ~само, intransitive~)` |
| **grow** | `(рости ~органічно, з часом~)` |
| **boost** | `(підбити ~позитивний поштовх~)` |
| **improve** | `(покращити(ся) ~якість, не кількість~)` |
| **enhance** | `(підсилити ~вже добре, зробити ще краще~)` |
