# WorkBuddy Quickstart — Turn Two Apple 10-Qs Into an Auditable Earnings Brief

Use **WorkBuddy International** to turn two public Apple filings into a Markdown earnings brief. You’ll get six reported figures, two calculated metrics, and an evidence table that points back to the filings. Run the same task with **Hy4** and **Hy4 flash** to compare completion time and citation accuracy.

[Download the filings](#use-two-filings-with-one-reporting-period-trap) · [Copy the prompt](#run-the-same-task-twice) · [Check the answer key](#check-the-output-against-the-filings) · [See the measured results](#measured-results-on-workbuddy-international)

[Get WorkBuddy](https://www.tencentcloud.com/act/pro/workbuddy?fromSource=intl.25923850.25923850.25923850&utm_medium=cpc&utm_id=intl.25923850.25923850.25923850)

**Disclosure.** The maintainer works on Tencent WorkBuddy growth.

## Use two filings with one reporting-period trap

| Input | Reporting period | Download |
| --- | --- | --- |
| `apple-fy26-q2.pdf` | Apple fiscal Q2 ended March 28, 2026 | [Apple PDF](https://s2.q4cdn.com/470004039/files/doc_earnings/2026/q2/filing/10Q-Q2-2026-as-filed.pdf) · [SEC filing](https://www.sec.gov/Archives/edgar/data/320193/000032019326000013/aapl-20260328.htm) |
| `apple-fy26-q3.pdf` | Apple fiscal Q3 ended June 27, 2026 | [Apple PDF](https://s2.q4cdn.com/470004039/files/doc_earnings/2026/q3/filing/10Q-Q3-2026-as-filed.pdf) · [SEC filing](https://www.sec.gov/Archives/edgar/data/320193/000032019326000020/aapl-20260627.htm) |

Use the full 32-page PDFs. The statements of operations include three-month columns. The cash flow statements supply six-month and nine-month totals, so calculating standalone Q3 cash flow requires both filings.

## Run the same task twice

1. Open the [WorkBuddy International web app](https://www.workbuddy.ai/app) and start a fresh **Work** task. For the comparison, check that both built-in models are available in your model picker.
2. Select **Hy4**, attach both PDFs, and paste the prompt below. Save the first Markdown brief and record the app’s **Completed** time before sending any corrections.
3. Repeat in a fresh task with **Hy4 flash**. Use the same account, two files, and prompt. If you only need an earnings brief, run the task once with your available model and use the same answer key.

### Copy the prompt

This is the prompt used in both measured runs.

```text
Use only the two attached Apple FY2026 Form 10-Q filings.
Prepare an English Markdown brief comparing fiscal Q2 and Q3.

Start with an evidence table for quarterly net sales, operating income
and net income. For each value give the period-end date, period length,
currency and units, source filename, statement name, row label and page.

Calculate the sequential percentage change in net sales from Q2 to Q3.
Calculate fiscal Q3 operating cash flow using the cash flow statements.
Show the formulas and cite all inputs, including their period lengths.
Label values as reported or calculated. Mark unresolved evidence as missing.

Finish with a three-sentence comparison grounded in the table.
Use the supplied files only. Leave out recommendations and price targets.
```

## Check the output against the filings

Your brief should have six reported values, two calculations with formulas and citations, and a three-sentence comparison. All monetary figures below are in USD millions.

| Reported figure | Q2 | Q3 |
| --- | ---: | ---: |
| Total net sales | 111,184 | 109,417 |
| Operating income | 35,885 | 35,695 |
| Net income | 29,578 | 29,789 |

- **Sequential change in net sales** — `(109,417 − 111,184) / 111,184 × 100 ≈ −1.59%`.
- **Standalone Q3 operating cash flow** — `116,996 − 82,627 = 34,369` USD million. The first input covers nine months through June 27. The second covers six months through March 28.

Open the statements of operations on **PDF viewer page 4** (printed page 1) in both files. Open the cash flow statements on **PDF viewer page 8** (printed page 5). Viewer pages are counted from 1.

## Measured results on WorkBuddy International

On November 23, 2026, Hy4 ran first and Hy4 flash ran second. Both completed one fresh Work-mode task on the same signed-in account, using the two full PDFs and the same prompt. The app’s completion times exclude file preparation and manual review.

| First-pass check | Hy4 | Hy4 flash |
| --- | ---: | ---: |
| WorkBuddy completion time | 3 min 25 sec | 1 min 12 sec |
| Correct value, period and unit | 8/8 | 8/8 |
| Correct source and page reference | 8/8 | 7/8 |
| Corrective follow-up prompts sent | 0 | 0 |

Hy4 flash finished **2 minutes 13 seconds sooner** in this run. It gave the correct viewer page for both operating cash flow inputs and called it printed page 4. The filing footer says 5. Both inputs belong to the same calculation, so that cost one source check. Flash also called each 32-page PDF a 33-page file. The PDF length error was logged separately. These results describe one run per model on these filings.

## Score the brief before comparing speed

- **Accuracy.** Score the six reported values and two calculations out of eight. Check each value, period, and unit.
- **Traceability.** For those same eight items, follow each reference to the filing, statement, row, and page. Verify both inputs to each calculation.
- **Rework.** Record corrective prompts and any time spent getting to a brief that passes the checks.

For a repeat test, ask for the **viewer page and exact statement row** for each input. To compare timings across runs, repeat the pair, alternate which model goes first, and report the individual times and the median for each model.

## Related resources

- [Reusable earnings-review prompt](earnings-review.md)
- [WorkBuddy model configuration](https://www.workbuddy.ai/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model-Configuration)
- [Tencent’s Hy4 flash announcement](https://www.tencent.com/tencent-launches-hy4-flash-to-power-high-speed-cost-efficient-ai-deployment-for-everyday-workflows/) · [Hy team’s Reddit AMA reply](https://www.reddit.com/r/LocalLLaMA/comments/1y15w4a/comment/19sxgnoy1ekyq/)
