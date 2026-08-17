# Working Capital Diagnostic — Nhựa Hà Nội JSC (HNX: NHH)

A cash conversion cycle analysis of a Vietnamese OEM plastics manufacturer, FY2023–FY2025, benchmarked against four listed contract manufacturers in Malaysia, Japan, Sweden and Vietnam.

Built entirely from published audited financial statements. No confidential or internal information is used anywhere in this repository.

---

## The finding in one paragraph

NHH reduced its cash conversion cycle from 71.9 to 57.5 days over two years, releasing roughly VND 91 billion of working capital. On the headline number it now sits alongside comparable OEM contract manufacturers. Decomposing the cycle shows something different: NHH collects about 31 days faster than the peer mean and pays suppliers about 28 days sooner. The two deviations are similar in size and opposite in sign, so they almost cancel in the headline and hide each other. The remaining opportunity is on the payables side, not the receivables side.

## Results

**NHH cash conversion cycle, average-balance basis**

| Days | FY2023 | FY2024 | FY2025 | Change |
|---|---|---|---|---|
| Days sales outstanding | 51.6 | 45.7 | 45.8 | (5.8) |
| Days inventory outstanding | 62.8 | 48.1 | 43.7 | (19.0) |
| Days payable outstanding | 42.5 | 29.7 | 32.0 | (10.5) |
| **Cash conversion cycle** | **71.9** | **64.0** | **57.5** | **(14.4)** |

**Peer position, FY2025**

| Days | NHH | SKP | Sanko | Nolato | NTP |
|---|---|---|---|---|---|
| DSO | 45.8 | 80.5 | 73.7 | 60.9 | 20.6 |
| DIO | 43.7 | 37.4 | 39.0 | 53.6 | 95.8 |
| DPO | 32.0 | 63.2 | 57.3 | 31.9 | 23.1 |
| **CCC** | **57.5** | **54.7** | **55.3** | **82.6** | **93.3** |

Closing the payables gap to the OEM peer mean would release approximately VND 148 billion, carrying an annual financing cost of about VND 7.5 billion at the company's implied cost of debt of 5.05%. That is an estimate of headroom, not a target — part of the gap is structural and is explained in the report.

## Contents

| File | What it is |
|---|---|
| `report/NHH_Working_Capital_Report.pdf` | The analysis, 15 pages including four appendices. Start here. |
| `report/NHH_Working_Capital_Report.docx` | Same document, editable format. |
| `model/NHH_Working_Capital_Model.xlsx` | Ten-sheet Excel model. Every figure in the report traces back to this file. |
| `data/peer_database.xlsx` | Peer financials as extracted from source filings, with per-company extraction notes. |

## How the model is organised

The workbook follows an input / engine / output structure. Blue text marks hardcoded input, black marks formulas, green marks cross-sheet links.

| Sheet | Purpose |
|---|---|
| `01_Inputs` | NHH consolidated financials, keyed to Circular 200 statement codes. All hardcoded. |
| `02_Assumptions` | Drivers: days per year, tax rate, sensitivity scenarios. |
| `03_FS_Restated` | Vietnamese statutory format restated to an analytical format, with reconciliation checks. |
| `04_Ratios` | Liquidity, profitability, efficiency, leverage, DuPont, implied cost of debt. |
| `05_CCC` | Cycle decomposition on average balances, plus a purchases-basis DPO cross-check. |
| `06_Peer_Inputs` | Peer financials in their own reporting currencies, with extraction notes. |
| `07_Peer_Benchmark` | Peer comparison and the payables-gap bridge. |
| `08_Dashboard` | One-page summary with three charts. |
| `09_Reference` | Glossary, account codes, methodology notes. |

The model uses `INDEX`/`MATCH` on label text rather than fixed cell addresses, so inserting rows does not break it.

## Method

Cash conversion cycle is defined as DSO + DIO − DPO. All components use average balances, calculated as the mean of opening and closing positions. DSO is measured against revenue; DIO and DPO against cost of goods sold. A 365-day year is applied throughout.

Figures are held in each company's own reporting currency. The cycle is expressed in days and is currency-neutral, so no FX translation is applied and no translation error is introduced.

Three extraction decisions materially affect the comparison and are documented in the model:

- **Sanko Gosei** discloses notes receivable and electronically recorded monetary claims separately from accounts receivable, with mirror items on the payables side. All components are included. Using accounts receivable alone would understate both its DSO and its DPO by a wide margin.
- **SKP Resources** reports trade and other payables as a single line in every annual report. Its DPO is an upper bound and its cycle a lower bound. This is disclosed rather than estimated away.
- **An Phát Bioplastics** was excluded from all peer averages. It raised its holding in NHH from 47.44% to 62.75% on 26 September 2024 and consolidates NHH as a subsidiary, so comparing the two would mean comparing NHH with a group that contains NHH.

## Limitations

Stated in full in Section 7 of the report. The main ones:

- SKP closes 31 March and Sanko closes 31 May, so their fiscal years do not align with NHH's calendar year end.
- The inventory reduction is not decomposed between price effect and volume effect; resin prices fell over the period and published accounts do not permit the two to be separated.
- Receivables factoring and note discounting are not visible in published disclosure. If present, DSO would be understated.
- FY2023 return and turnover ratios use closing balances because the FY2022 balance sheet was obtained for receivables, inventory and payables but not for total assets. The cash conversion cycle is not affected.

## Sources

Audited consolidated financial statements published by each company, FY2022–FY2025, retrieved from company disclosure pages and exchange filing portals. Full source list in Appendix D of the report.

## Context and disclaimer

I built this after a summer internship in the finance function of a Vietnamese OEM injection-moulding manufacturer, which shaped the operational questions I asked of the data. The subject company, NHH, is a listed competitor analysed entirely from public filings.

This is an independent analytical exercise, not investment advice and not a recommendation to buy or sell any security. Any errors are my own.

---

*[Kien Chi Nguyen] · [IEBE_Erasmus School of Economics] · [https://www.linkedin.com/in/ki%C3%AAn-nguy%E1%BB%85n-2a9360349/]*
