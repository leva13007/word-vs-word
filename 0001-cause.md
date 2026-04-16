# 0001. cause vs lead to vs bring about vs trigger

> 🔧 IT

В ІТ ці дієслова звучать щодня, але їх часто кидають навмання. Щоб не плутатися, подивімося на весь ланцюжок причинності і побачимо, де саме кожне слово працює найкраще.

## Одним поглядом

| Слово | Значення (UA) | Ключовий нюанс |
|-------|--------------|----------------|
| **cause** | спричиняти | безпосередньо, root cause |
| **lead to** | призводити | через ланцюг наслідків |
| **bring about** | досягати результату | навмисно, запланована зміна |
| **bring** | приносити | побічний/природний ефект |
| **trigger** | запускати | система чекала цього сигналу |

---

### Мислимо як інженери

```
ACTION / CHANGE
   ↓
MECHANISM / PROCESS
   ↓
RESULT / OUTCOME
```

Кожне дієслово відповідає за власну ділянку цього маршруту.

---

### cause — пряма причина (root cause)

**Суть:** Х безпосередньо зробив Y.

- нейтрально, сухо, технічно
- завжди доречно у баг-репортах і RCA

**В ІТ:**

- a bug causes a crash
- a race condition causes data corruption

**Приклад:** `A null pointer exception caused the application to crash.`

**Як думаємо:** «Без X подія Y взагалі не трапилася б».

---

### lead to — ланцюг наслідків

**Суть:** X поступово привів до Y, були етапи.

- звучить стратегічно
- підкреслює процес, а не одиничну дію

**В ІТ:**

- слабкий дизайн → технічний борг → проблеми у продакшені
- зміни в UI → деградація usability

**Приклад:** `Poor error handling led to unstable behavior.`

**Як думаємо:** «Йдеться про еволюцію рішень, а не про один клік».

---

### bring about — навмисна зміна

**Суть:** Команда спеціально зробила дії, щоб отримати результат.

- звучить проактивно
- доречно, коли був план і очікування

**В ІТ:**

- рефакторинг brought about performance gains
- оптимізація brought about cost savings
- міграція brought about simpler operations

**Приклад:** `This refactoring brought about significant performance improvements.`

**Як думаємо:** «Ми цілеспрямовано прагнули саме цього outcome».

> `bring to` у технічних текстах майже не вживають; якщо бачиш “bring”, перевір, чи справді не йдеться про “bring about”.

---

### bring — природний або супутній наслідок

**Суть:** Подія X принесла Y як очікуваний або побічний результат, без акценту на цілеспрямованій роботі.

- м’якше за `cause`, бо не натякає на поломку
- доречно, коли «так вийшло» в межах нормальної еволюції

**В ІТ:**

- апдейт brought a refreshed UI
- нова політика brought extra reviews
- інтеграція brought latency trade-offs

**Приклади:**

- `The redesign brought smoother navigation.`
- `The same redesign brought additional complexity.`

**Як думаємо:** «Це наслідок, який природно прийшов у комплекті з рішенням».

**⚠️ Важливо:** у технічних текстах `bring` описує наслідок, але не встановлює причинно-наслідковий контракт, як `cause`. Якщо хочеш підкреслити, що X саме спричинило Y, краще `cause` або `bring about`.

---

### trigger — подія, що все запускає

**Суть:** Подія X смикнула курок процесу, який вже був готовий.

- типовий термін для event-driven систем
- часто в логах, alert-ах, CI/CD

**В ІТ:**

- вебхук triggered pipeline
- деплой triggered cache invalidation
- алерт triggered on-call rotation

**Приклад:** `A deploy triggered a cache invalidation.`

**Як думаємо:** «Система чекала, поки цей тригер її увімкне».

---

### Порівняльна шпаргалка

| Verb | Роль | Питання | Тип |
|------|------|---------|-----|
| cause | пряма причина | Що зламало? | root cause |
| lead to | ланцюг | До чого все прийшло? | process |
| bring | природний наслідок | Що прийшло разом із зміною? | outcome |
| bring about | навмисна дія | Що хотіли отримати? | intention |
| trigger | спусковий гачок | Що запустило? | event |

---

### Один сценарій — всі дієслова

`A configuration change triggered a memory leak, which caused increased memory usage. Over time, this led to frequent service restarts. A later refactoring brought about a stable system.`

Кожне слово відповідає своїй ділянці: trigger (подія) → cause (пряма причина) → lead to (ланцюг) → bring about (навмисне виправлення).

---

### Типові помилки

- `This feature caused improvement` → потрібно `brought about` (це ж очікувана вигода)
- `Button click caused deployment` → `triggered deployment`
- `Bad architecture triggered technical debt` → `led to technical debt`

---

### Мнемоніка для інженера

- cause → ❌ баг
- trigger → ▶️ подія
- lead to → ➡️ наслідки
- bring about → 🎯 мета
- bring → 📦 супутній ефект

---

### bring vs bring about vs cause

| Форма | Коли вживати |
|-------|--------------|
| bring | природний або очікуваний наслідок («оновлення принесло новий UI»)
| bring about | запланована, керована зміна
| cause | сувора причинність, аварії, баги

---

### Чеклист перед вибором слова

1. Це баг/поломка? → `cause`
2. Це ланцюг проміжних етапів? → `lead to`
3. Це тригер події? → `trigger`
4. Це очікуваний або природний результат? → `bring` (а якщо наголошуєш на керованій зміні — `bring about`)

---

### Практичний приклад

```txt
A configuration change triggered a memory leak, which caused increased memory usage.
Over time, this led to frequent service restarts.
A later refactoring brought about a stable system,
but also brought additional operational complexity.
```

Зверни увагу, як `bring` без about підкреслює додатковий, напівочікуваний побічний ефект.

---

## Для картки

> `(...)` — безпечний контекст, читається як є: «призвело (прямо)».
> `(~...~)` — всередині не перекладати дослівно, лише підказка: «призвело (~поступово~)».
> `(A|B)` — альтернативні синоніми.

| Слово | Запис на картці |
|-------|------|
| **cause** | `спричинило` або `призвело (~напряму~)` |
| **lead to** | `призвело (через ланцюг)` або `призвело (~поступово~)` |
| **bring about** | `досягло результату (~навмисно~)` |
| **bring** | `принесло (as a side effect)` або `принесло (~побічно~)` |
| **trigger** | `запустило (as a trigger)` — або залишити trigger |