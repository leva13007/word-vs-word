# 0013. solution vs decision vs fix vs workaround vs mitigation vs resolution vs patch vs hotfix

> 🔧 IT · 📖 general

Усі ці слова описують реакцію на проблему або вибір між варіантами — але вони розрізняються за тим, **чи проблему усунуто**, **наскільки це офіційно** і **наскільки терміново**. Найчастіша помилка — вживати *solution* або *fix* там, де насправді зробили лише *workaround* або *mitigation*.

## Одним поглядом

| Слово | Значення (UA) | Ключовий нюанс |
|-------|--------------|----------------|
| **solution** | рішення, вирішення | найширше; підходить для будь-якого контексту |
| **decision** | рішення (вибір) | між варіантами, не про «поломку» |
| **fix** | виправлення | усуває причину технічної проблеми |
| **workaround** | обхідний шлях | проблема лишається, але обходимо її |
| **mitigation** | пом'якшення | зменшуємо вплив/ризик, не усуваємо причину |
| **resolution** | закриття, вирішення | офіційний статус «тікет закрито» |
| **patch** | латка, патч | точкова зміна коду; може бути плановою |
| **hotfix** | термінове виправлення | urgent + production + поза звичайним релізом |

---

### Мислимо як інженери

```
INCIDENT / PROBLEM
    ↓
    ├─ mitigation ──── знижуємо вплив (rate limit, feature flag off)
    │                  проблема ЛИШАЄТЬСЯ
    ↓
    ├─ workaround ──── обходимо (manual retry, fallback endpoint)
    │                  причина ЛИШАЄТЬСЯ
    ↓
    fix / patch ─────── усуваємо причину в коді
    hotfix ──────────── те саме, але ТЕРМІНОВО в prod
    ↓
    resolution ─────── тікет/інцидент ОФІЦІЙНО ЗАКРИТО
    solution ────────── загальна назва для будь-якого успішного виходу

    decision ─────────  НЕ про поломку; це вибір між варіантами (ADR, design review)
```

---

### solution — вирішення (найширше)

**Суть:** Загальне слово для будь-якого успішного виходу з проблеми або задачі. Не уточнює метод.

- нейтральне, підходить для будь-якого регістру
- часто — кінцевий результат обговорення або дослідження

**В ІТ:**

- We need a long-term solution, not just a workaround.
- The solution involves refactoring the retry logic.
- cloud-based solution, open-source solution

**Приклад:** `After two days of investigation, the team found a solution that addressed the root cause.`

**Як думаємо:** «Завдання або проблема має відповідь — ось вона.»

---

### decision — рішення (вибір між варіантами)

**Суть:** Вибір між кількома варіантами після оцінки. Не про те, що щось «зламалось» — про те, який шлях обрати.

- ключовий контекст: архітектурні рішення (ADR), ретроспективи, design reviews
- не можна замінити на *fix* або *workaround*

**В ІТ:**

- the decision to use PostgreSQL over MySQL
- make a decision on the deployment strategy
- document the decision in an ADR

**Приклад:** `The team made a decision to migrate to a microservices architecture.`

**Як думаємо:** «Треба вибрати між A і B — це *decision*, а не *solution*.»

---

### fix — виправлення (усуває причину)

**Суть:** Конкретна технічна дія, яка прибирає причину проблеми. Менш формальне ніж *resolution*, більш технічне ніж *solution*.

- зазвичай стосується коду, конфігурації, скрипту
- передбачає, що після fix проблема більше не виникне

**В ІТ:**

- apply a fix to the authentication module
- the fix was merged in PR #412
- quick fix vs permanent fix

**Приклад:** `The fix involved adding a null check before accessing the user object.`

**Як думаємо:** «Знайшли причину — зробили *fix*.»

---

### workaround — обхідний шлях

**Суть:** Тимчасовий обхід проблеми без усунення її причини. Яма на дорозі лишається — ми просто їдемо в об'їзд.

- може існувати довго, якщо *fix* занадто дорогий
- часто документується для інших членів команди

**В ІТ:**

- use this workaround until the fix is deployed
- document the workaround in the runbook
- workaround: manually restart the service every 6 hours

**Приклад:** `As a workaround, we disabled the caching layer to prevent stale reads — the root cause is still under investigation.`

**Як думаємо:** «Яму не засипали, але проклали об'їзд — це *workaround*.»

---

### mitigation — пом'якшення (зменшуємо вплив)

**Суть:** Зменшення впливу або ризику проблеми без усунення її причини. Вогнегасник — не ремонт будівлі.

- типово для incident response, security, risk management
- іноді поєднується з workaround, але фокус на **масштабі шкоди**, а не на обході

**В ІТ:**

- mitigate the impact of the outage
- risk mitigation strategy
- mitigation: reduce traffic via rate limiting

**Приклад:** `As a mitigation, we enabled rate limiting to reduce the blast radius while the fix was being developed.`

**Як думаємо:** «Повністю зупинити не можемо — але зменшуємо шкоду: *mitigation*.»

---

### resolution — закриття (офіційний статус)

**Суть:** Офіційне закриття інциденту або тікету. Підкреслює **статус**, а не технічний метод.

- ключовий контекст: MTTR (Mean Time To Resolution), incident postmortems, Jira
- resolution може включати fix, workaround або hotfix — важливо, що «закрито»

**В ІТ:**

- the incident was closed with a resolution time of 47 minutes
- write up the resolution in the postmortem
- mark the ticket as resolved

**Приклад:** `The resolution was documented in the postmortem: the hotfix was deployed and the incident was closed.`

**Як думаємо:** «Тікет/інцидент **закрито** — це *resolution*.»

---

### patch — латка (точкова зміна коду)

**Суть:** Невелика цілеспрямована зміна коду або системи, яка виправляє конкретну помилку або вразливість. Може бути плановою, на відміну від hotfix.

- часто: security patch, OS patch, library patch
- можна включати в звичайний release cycle

**В ІТ:**

- apply the security patch
- the vendor released a patch for CVE-2025-1234
- patch management process

**Приклад:** `We applied the vendor's patch to address the authentication bypass vulnerability.`

**Як думаємо:** «Маленька латка поверх коду — *patch*.»

---

### hotfix — термінове виправлення в продакшені

**Суть:** Виправлення, яке виходить терміново в production поза звичайним release cycle. Urgent + out-of-band.

- завжди про production
- обходить звичайний процес: скорочений code review, мінімальне тестування
- різниця від *patch*: hotfix = терміновість + нештатний процес

**В ІТ:**

- deploy a hotfix to production immediately
- hotfix branch: hotfix/1.2.1
- hotfix required approval from two senior engineers

**Приклад:** `A hotfix was pushed directly to production at 2 AM to stop the data leak — the proper fix followed in the next sprint.`

**Як думаємо:** «Горить! Прямо в prod, прямо зараз — *hotfix*.»

---

### Порівняльна таблиця

| Слово | Причину усунуто? | Офіційне закриття? | Терміновість | Типовий контекст |
|-------|-----------------|-------------------|--------------|-----------------|
| **solution** | частіше так | — | будь-яка | загальна мова, документація |
| **decision** | не застосовно | — | будь-яка | ADR, design review, retro |
| **fix** | ✅ так | — | помірна | PR, code review, bug tracker |
| **workaround** | ❌ ні | — | низька | runbook, тимчасова міра |
| **mitigation** | ❌ ні | — | під час інциденту | incident response, risk mgmt |
| **resolution** | зазвичай так | ✅ так | — | postmortem, MTTR, Jira |
| **patch** | ✅ так | — | помірна | security, OS, library updates |
| **hotfix** | ✅ так | — | 🔴 висока | production, out-of-band release |

---

### Один сценарій — всі слова

`During the incident, we applied a mitigation by turning off the feature flag, then used a workaround to re-route traffic; a hotfix was deployed overnight to patch the root cause, which led to the resolution of the ticket — and in the postmortem we documented the fix as part of a broader solution, including a decision to adopt automated rollback.`

---

### Типові помилки

- `❌ We deployed a hotfix to staging.` → hotfix завжди про **production**; для staging — це просто *patch* або *fix*
- `❌ The mitigation resolved the issue.` → mitigation **не закриває** проблему; після mitigation все одно потрібен *fix*
- `❌ We found a workaround — the bug is fixed.` → workaround не означає, що причину усунуто; краще: `we found a workaround; the fix is in progress`
- `❌ We made a fix to use Redis instead of Memcached.` → це **архітектурне рішення**, не fix; краще: `we made a decision to switch to Redis`

---

### Мнемоніка

- **solution** → 🔑 «будь-яка відповідь на будь-яке питання»
- **decision** → 🔑 «A чи B? — це *decision*»
- **fix** → 🔑 «знайшли причину, прибрали причину»
- **workaround** → 🔑 «яма лишилась — ми їдемо в об'їзд»
- **mitigation** → 🔑 «вогнегасник, а не ремонт»
- **resolution** → 🔑 «тікет *closed* — ось *resolution*»
- **patch** → 🔑 «маленька латка поверх коду»
- **hotfix** → 🔑 «2 AM, production, горить — *hotfix*»

---
