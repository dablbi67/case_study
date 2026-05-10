[README.md](https://github.com/user-attachments/files/27561765/README.md)
# GBP Transfer Volume Analysis — UK↔SA

Exploratory analysis of daily GBP-ZAR transfer volumes, completed as part of a take-home case study. All analysis is written in **Snowflake SQL** with no Python dependencies.

---

## Dataset

| Field | Description |
|---|---|
| `posting_date` | Date of transfer (DD/MM/YYYY) |
| `volume_gbp` | Daily transfer volume in GBP |

**Coverage:** April 2023 – December 2023 (note: October data is incomplete)

---

## Tasks & Scripts

### Task 1 — Distribution Analysis (`Task%201`)

Identifies and proves the bimodal distribution of daily transfer volumes.

**Key finding:** The dataset contains two structurally separate populations — business days (median £233k) and inactive days (weekends + public holidays, median £2k) — with a near-empty valley between £28k and £51k confirming bimodality.

---

### Task 2 — Quarter-on-Quarter Analysis (`Task%202`)

Tests whether QoQ volume changes are statistically significant or driven by background fluctuations.

**Key finding:** No QoQ change is statistically significant at 95% confidence for business days. The large mean-median gap on weekends (88× in Q2) signals anomalous high-value transactions distorting the weekend average.

---

### Task 3 — October 2023 Volume Estimate (`Task%203`)

Estimates total October 2023 transfer volume with a confidence interval, given the incomplete data.

**Key finding:** Point estimate £5.6M (95% CI: £4.1M – £7.0M), based on 22 business days and a Q2–Q3 baseline.
