# Hy4 vs. Hy4 flash in WorkBuddy — a reproducible earnings review

In the November 2026 r/LocalLLaMA AMA, the Tencent Hy team said that long reasoning chains were a known issue for Hy4 and that it used reinforcement learning to shorten them in Hy4 flash. For an office task, the useful question is how soon you get an answer you can verify. A faster draft still costs time if you have to reopen every source to fix the reporting periods.

This guide is for the international WorkBuddy desktop client, available from [workbuddy.ai](https://www.workbuddy.ai/). Give each model the same two filings, request the same report, and check the output against the same answer key. Tencent's launch announcement describes a WorkBuddy rollout. Check whether both Hy4 and Hy4 flash are available to your international account before starting. The desktop client also supports compatible custom model endpoints when your provider and account support the required file tools. [AMA reply](https://www.reddit.com/r/LocalLLaMA/comments/1y15w4a/comment/19sxgnoy1ekyq/) · [Tencent's Hy4 flash announcement](https://www.tencent.com/tencent-launches-hy4-flash-to-power-high-speed-cost-efficient-ai-deployment-for-everyday-workflows/) · [International WorkBuddy model configuration](https://www.workbuddy.ai/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model-Configuration)

**Test status.** The figures below were checked against Apple's public SEC filings. The international WorkBuddy comparison is pending. Model availability for the test account, timings and scores have yet to be verified. The maintainer works on Tencent WorkBuddy growth.

## Use two filings with one reporting-period trap

Save these SEC filings as HTML, or export both to PDF using the same method. Use the same saved files in both runs. For a PDF export, record the printed filing page numbers as well as the PDF page numbers if they differ.

- `apple-fy26-q2` — Apple's Form 10-Q for the quarter ended March 28, 2026. [SEC filing](https://www.sec.gov/Archives/edgar/data/320193/000032019326000013/aapl-20260328.htm)
- `apple-fy26-q3` — Apple's Form 10-Q for the quarter ended June 27, 2026. [SEC filing](https://www.sec.gov/Archives/edgar/data/320193/000032019326000020/aapl-20260627.htm)

The statements of operations show a three-month column alongside year-to-date columns. The statements of cash flows give six-month and nine-month figures. A model can copy an exact number from the right filing and still assign it to the wrong period. Fiscal Q3 operating cash flow is a calculation using both filings.

## Run the same task twice

1. Put the two filings in a clean local folder. Keep the answer key below out of that folder.
2. Start a fresh task for each model in the international WorkBuddy desktop client. Choose **Hy4 flash** or **Hy4** manually. Use the same account, provider, input files and tool permissions. Record the app version, account edition, model labels and provider. If either model is unavailable, record that and leave the comparison pending.
3. Paste the prompt below. Time each run from submission until the finished brief is available. Keep the first output and record any corrective follow-up separately.
4. Audit the brief against the answer key. For a stronger comparison, run three pairs and alternate which model goes first. Keep each fresh task isolated from earlier results. Report individual times and the median for each model.

[WorkBuddy Quick Start](https://www.workbuddy.ai/docs/workbuddy/Quickstart) · [Repository earnings-review prompt](earnings-review.md)

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

All monetary figures are in USD millions. Use the current-year **three-month** columns in the statements of operations.

| Reported metric | Q2 ended Mar 28, 2026 | Q3 ended Jun 27, 2026 |
| --- | ---: | ---: |
| Total net sales | 111,184 | 109,417 |
| Operating income | 35,885 | 35,695 |
| Net income | 29,578 | 29,789 |

- **Sequential change in net sales.** `(109,417 − 111,184) / 111,184 × 100 ≈ −1.59%`. This compares fiscal Q3 with fiscal Q2 of the same year.
- **Fiscal Q3 operating cash flow.** `116,996 − 82,627 = 34,369` USD million. The first input covers nine months through June 27. The second covers six months through March 28. The quarter value is calculated and needs both citations.

[Apple Q2 Form 10-Q](https://www.sec.gov/Archives/edgar/data/320193/000032019326000013/aapl-20260328.htm) · [Apple Q3 Form 10-Q](https://www.sec.gov/Archives/edgar/data/320193/000032019326000020/aapl-20260627.htm)

## Score the brief before comparing speed

| Check | How to record it |
| --- | --- |
| Accuracy | Score the six reported values and two calculations out of eight. A row passes when its value, period and unit are correct. |
| Traceability | Score those same eight items out of eight. A pass requires the cited statement and row to support the value. Check both inputs for each calculation. |
| Rework | Count corrective prompts and note the reason, such as a year-to-date figure presented as a quarter. |
| Time to usable output | Record the first brief's wall-clock time and any extra time needed for corrections. Mark a brief that never passes the checks as incomplete. |

The useful comparison is time to an auditable brief. If both models pass on the first try, compare elapsed time. If one needs a second pass, include that rework. Any result describes this source pack, task setup and model configuration.
