# Personal Investment Research Workflow for WorkBuddy

A reusable prompt and report-template kit for using a desktop AI workspace to review public filings, compare companies, and create evidence-based research briefs.

> **Disclosure:** The maintainer works on Tencent WorkBuddy growth. WorkBuddy is the reference implementation. The prompts can be used with other workspaces that support the same inputs.

> **Important:** This repository is for research and education. It does not provide investment advice, price targets, trade execution, or guaranteed real-time market data.

## WorkBuddy Quickstarts

**[Turn two Apple 10-Qs into an auditable earnings brief](hy4-vs-hy4-flash-earnings-review.md).** Download the two filings, run the same prompt with Hy4 and Hy4 flash, and verify the figures and page references against an answer key. The walkthrough includes measured completion times and a cash flow citation error you can check in both PDFs.

[Get WorkBuddy](https://www.tencentcloud.com/act/pro/workbuddy?fromSource=intl.25923850.25923850.25923850&utm_medium=cpc&utm_id=intl.25923850.25923850.25923850)

## Why this workflow exists

Asking an AI assistant “What stock should I buy?” produces an answer that is difficult to verify. This kit uses a different pattern:

1. define a bounded research question;
2. provide primary source files;
3. require citations and formulas;
4. separate facts from interpretation;
5. expose missing evidence;
6. review the output manually.

Tencent WorkBuddy is the reference desktop workspace for this kit. It supports file-based work, model selection, tool use, and structured output. Model access and task capability depend on the configured provider, endpoint, credentials, quota, and model.

## Prompts and templates

| File | Use |
|---|---|
| [Earnings review](earnings-review.md) | Extract earnings figures into a source-linked evidence table |
| [Company comparison](company-comparison.md) | Compare periods, currencies and metrics across two companies |
| [Bull and bear case](bull-bear-case.md) | Build two interpretations from one verified evidence set |
| [Daily watchlist brief](daily-watchlist-brief.md) | Summarize dated public sources supplied by the user |
| [Research report](research-report.md) | Assemble the final research brief |
| [Comparison CSV](company-comparison.csv) | Record company metrics, periods and source references |
| [Fictional example](fictional-company-example.md) | See how a reported figure and a calculated metric are labeled |

## Quick start

1. Create a dedicated working folder.
2. Add public filings, earnings releases, investor presentations, and dated spreadsheets.
3. Open the folder in WorkBuddy.
4. Select a model suitable for document analysis and tool use.
5. Run the comparison prompt before asking for the narrative report.
6. Verify every material figure and citation.

## Model selection checklist

Test a model with non-sensitive sample data before using it regularly.

- [ ] Long-document handling
- [ ] Spreadsheet and table extraction
- [ ] Arithmetic consistency
- [ ] Tool calling
- [ ] Source citation accuracy
- [ ] Explicit handling of missing information
- [ ] No fabricated live-market access

WorkBuddy supports model switching and compatible custom model APIs. A specific model, including Tencent Hy4, is usable only when the user has valid access through the relevant service and the model is currently available.

## Validation rules

Reject or revise the output if any of these conditions is true:

- a material number has no source;
- a citation does not support the claim;
- the assistant silently changes currency or period;
- an adjusted metric is presented as an accounting-standard metric;
- a calculated metric has no formula;
- current market data is claimed without an authorized source;
- the output contains a personalized buy/sell recommendation.

## Data and privacy

Do not commit:

- brokerage exports;
- account identifiers;
- private portfolio holdings;
- paid research without redistribution rights;
- API keys or model credentials;
- confidential company material.

Using a local model does not guarantee that the entire workflow is offline. Web search, connectors, telemetry, and cloud file services may still transmit data.

## References

- [WorkBuddy Quick Start](https://intl.cloud.tencent.com/document/product/1316/84488)
- [WorkBuddy custom model configuration](https://indonesia.tencentcloud.com/document/product/1316/84496)
