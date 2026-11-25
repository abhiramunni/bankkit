# BankKit — Find a zero-balance account that fits you

Some bank accounts fine you for a low balance. Some pay you 7% a year.
BankKit compares 8 Indian savings accounts, ranks the right one for you in
4 quick questions, and shows exactly what your money earns at each bank.

**Live:** https://abhiramunni.github.io/bankkit/

## What it does

- **Matchmaker quiz** — 4 questions (usual balance, need for a branch, what
  matters most, how you want to open it) → a ranked match list with a match
  percentage for every account.
- **Compare all 8** — SBI Insta Plus (YONO), Kotak 811, IDFC FIRST
  (zero-balance variants), AU Small Finance Digital, Equitas Small Finance,
  Jupiter (Federal Bank), Jio Payments Bank, and BSBDA / Jan Dhan. Each card
  shows the interest rate, minimum balance, debit-card cost, UPI, how to open
  it — and the catch the ad hides. Filter by zero balance, highest interest,
  fully digital, or branch near you. Tap any card for the full detail sheet.
- **Interest calculator** — move the slider to your usual balance and see the
  yearly interest at every bank, using each bank's real slabs. The same
  ₹4 lakh earns ₹2,500 a year at SBI and ₹23,500 at Equitas.
- **Open-it checklist** — the 5 documents you need, the 4 opening steps,
  video KYC explained, and why a nominee takes 30 seconds and saves months.
- **Know this** — 6 plain-language guides: BSBDA (the account no bank can
  refuse), the ₹5 lakh DICGC cover, the charges page, dormant accounts,
  sweep FDs, and nominees.
- **Shortlist** — star accounts to pin them here; everything is saved on
  your device only (localStorage), nothing is sent anywhere.

## The numbers (hand-checked)

Yearly interest, before tax, at November 2026 slabs:

| Balance | SBI | Kotak 811 | IDFC FIRST | AU SFB | Equitas SFB | Jio PB |
|---|---:|---:|---:|---:|---:|---:|
| ₹1,00,000 | ₹2,500 | ₹2,500 | ₹2,500 | ₹2,500 | ₹2,500 | ₹4,000 |
| ₹4,00,000 | ₹10,000 | ₹10,000 | ₹14,000 | ₹10,250 | ₹23,500 | ₹8,000* |
| ₹10,00,000 | ₹25,000 | ₹25,000 | ₹53,000 | ₹30,500 | ₹60,500 | ₹8,000* |

*Jio Payments Bank balance is capped at ₹2 lakh.

Quiz check: balance under ₹10,000 + never needs a branch + no fees + fully
online → Jio and Kotak 811 both score 12/12 (100%). Balance ₹1–5 lakh +
highest interest → IDFC FIRST tops at 9/12 (75%).

## Honest notes

- Rates, fees and minimum-balance rules are **indicative**, from the banks'
  published pages as of November 2026. Banks change slabs and charges
  without notice — check the bank's own rate card before opening an account.
- BankKit is an educational comparison tool, not financial advice, and is
  not affiliated with any bank named here.
- Deposits in Indian banks are insured up to ₹5 lakh per depositor per bank
  by DICGC.
- Jupiter is included deliberately as the warning: it is **not** zero
  balance — it needs a ₹5,000 average monthly balance, or fees of up to
  ₹300 a month.

## Tech

Single self-contained `index.html` (plus two photos) — no backend, no
sign-up, localStorage only. Warm editorial design (ivory paper, espresso
ink, bronze/gold), cinematic intro with tap-to-skip, Fraunces + Inter.

## Run the tests

```bash
node --check <(python3 -c "s=open('index-publish.html').read();print(s[s.index('<script>')+8:s.index('</script>')])")
node qa-test.js   # 61 headless jsdom assertions
```

## Licence

MIT — see `LICENSE`.
