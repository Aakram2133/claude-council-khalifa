# The Claude Council ⚖️

**4 agents. 1 idea. 1 verdict.** A Claude Code skill that tells you whether your business idea is worth building before you spend months and money on it.

Ask Claude "is my idea good?" and it wants to be helpful, and helpful sounds like a balanced list of pros and cons that flatters you into building the wrong thing. The council fixes that. Each agent gets one job and runs in its own fresh context, and a judge has to rule.

| Agent | Job |
|---|---|
| 🟢 **Believer** | Makes the strongest honest case FOR the idea: who's in pain, what it costs them today, why now |
| 🔴 **Skeptic** | Tries to kill it: who won't pay, real competitors (including "a spreadsheet"), the assumption you're too close to see |
| 💰 **Investor** | Only cares if real money shows up: unit economics, first 10 customers, the cheapest demand test this week |
| ⚖️ **Judge** | Makes the three fight, then rules **BUILD / FIX FIRST / KILL**, plus one 10-minute action you can do today |

A KILL that saves six months is the most valuable thing it can produce.

## Install

```bash
git clone https://github.com/faroukahmed89-droid/claude-council.git
mkdir -p ~/.claude/skills
cp -r claude-council/skills/claude-council ~/.claude/skills/
```

Then open a **new** Claude Code session.

## Use

```
claude council: <your business idea in one paragraph>
```

Arabic works too, and the council answers in the language you write in:

```
المجلس: <فكرتك>
```

You get the verdict first, then a short summary from each agent. The full transcript is saved to `council/sessions/`.

## Memory

Every ruling is appended to `council/council.md` in your working folder. Come back after you've done the de-risk action:

```
claude council: what changed? I messaged 5 clients and 3 said they'd pay $50/month.
```

The Judge re-reads the history and tells you whether the ruling moved (e.g. `FIX FIRST → BUILD`). Ideas don't get killed in one sitting. They get killed by the same objection surviving three sittings.

## Built-in guardrails

- The idea is rewritten as a flat, persuasion-free paragraph first. Leading paragraphs make every agent agree.
- The Skeptic is told a gentle critique is a failure.
- The Investor must tag every number `(assumption)` or `(sourced: link)`.
- The Judge assumes you're emotionally attached and need the truth more than encouragement.
- Weak answers are re-run automatically: a polite Skeptic, untagged numbers, or a de-risk action that isn't doable in 10 minutes today.

> If the Judge says BUILD every time, the prompts are broken. A council that never kills anything is a mirror with extra steps.

---

## بالعربي

مجلس كلود هو ٤ Agents بياخدوا نفس فكرة البيزنس، وكل واحد فيهم عنده مهمة مختلفة:

- **المؤيد**: يثبتلك ليه الفكرة ممكن تنجح، ومين العميل اللي محتاجها فعلًا.
- **المشكك**: يهاجم الفكرة، ليه الناس ممكن متشتريش، وإيه المشاكل اللي إنت مش شايفها.
- **المستثمر**: عايز يعرف حاجة واحدة بس: هل الفكرة دي ممكن تعمل فلوس فعلًا؟
- **الحَكَم**: بيخلي التلاتة يتناقشوا ضد بعض، وفي الآخر يقولك إيه اللي لازم تثبته قبل ما تضيع شهور وفلوس.

اكتب `المجلس:` وبعدها فكرتك في فقرة واحدة.

## License

MIT
