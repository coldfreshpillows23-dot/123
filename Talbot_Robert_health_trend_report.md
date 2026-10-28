# Health Marker Trend Report: Robert J. Talbot

| | |
|---|---|
| **Patient** | Robert J. Talbot, male, DOB 07/14/1958 (age 60 at first record, 65 at latest record) |
| **MRNs** | PCP 004-882-19 · Nephrology NEP-2022-0447 · Endocrinology END-1194 · Cardiology CAR-5582 · Hospital WR-004882 · Transplant TRANS-2023-0819 |
| **Height** | 5'11" (documented 03/04/2022 and 01/30/2024) |
| **Actual data range** | **02/14/2019 to 05/14/2024 (about 5 years 3 months).** Dense data from 03/2022 onward; 2019 to early 2022 comes only from a staff-compiled lab archive with about 2 draws per year. |
| **Sources (code)** | ARC = `old_baseline_labs_2019_2020.txt` · LAB = `lab_results.csv` · PCP = `physician_notes_redacted.txt` · NEPH = `nephrology_clinic_notes.txt` · ENDO = `endocrine_and_thyroid_notes.txt` · HOSP = `hospital_discharge_partial.txt` (unfinalized draft) · TX = `transplant_eval_bloodwork.txt` · CARD = `cardiology_clearance_note.txt` · VIT = `vitals_and_weights_log.txt` · RX = `pharmacy_med_record.csv` |

> **Decision support only.** Every plotted value is copied from the source files and can be traced by date and source code. Nothing is estimated or filled in. Recommendations are for review by the treating clinicians and are not orders.

## Critical findings at a glance

1. **Potassium has been high on 12 of 14 reliable results since 04/2022. The latest is 6.0 mEq/L (04/17/2024)**, on lisinopril 40 mg, after a hospitalization for K 6.1 in 08/2023.
2. **Blood pressure is uncontrolled. Every reliable reading since 2022 is at or above 148/92, and the latest is 169/103.** That does not meet cardiology's listing condition (<140/90). LVH is present and LVEF fell from 60% to 52%.
3. **Kidney function is falling fast.** eGFR went from 70 to 31 in 5 years (about 12.7 mL/min per year since 03/2022). Protein in the urine is rising (UPCR 620 mg/g), bicarbonate is 16, phosphorus 6.1, PTH 276.
4. **Hemoglobin is 9.4 g/dL and an ESA was started without documented iron studies.** None of the uploaded files contain iron studies, hematology notes or thyroid tests (see Section 7).

---

## How to read the charts

- **Color:** 🟢 = within the reference range · 🔴 = outside the reference range · 🟡 = value was reported but is questionable (hemolysis, conflicting reports, wrong-patient suspicion). 🟡 values are shown but are not used to judge trends. Emoji were used for color because they show in color both in a plain text editor and on GitHub. Tables also mark **H**/**L** (high/low) and **?** (questionable), so the meaning survives black-and-white printing.
- **Time axis:** oldest on the left, newest on the right. **One column = 2 months, and spacing is proportional to real time**, so sparse years look sparse. When there are several results in one 2-month column, they are stacked. Exact dates and values are in the table under each chart.
- **Gaps are marked in each chart:** an `x` on the `no result` row means a panel or visit happened in that window but this marker was not reported. The `gaps >=6 mo` line lists every interval of 6 months or more between results, and says **NO RESULTS before …** when a marker was first measured well after the record begins (02/2019).
- **Dashed lines** are reference limits. A dot is always drawn on the correct side of a limit. Because rows are binned, a dot's height is approximate; the table gives the exact value.
- Reference ranges are for an **adult male aged 60 to 65**. The reporting lab's range is used where it gave one; age- or sex-specific notes are added where they matter.

---

## 1. Comprehensive Metabolic Panel (CMP)

The patient never had a complete 14-analyte CMP on a single date. The records contain partial renal-type panels. All CMP analytes are grouped in one chart below, with a shared time axis.

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

[1] CREATININE (mg/dL)  ref 0.74-1.35 (LLN 0.74 below chart)
        2.10 |
        2.00 |                                                      🔴      🔴
        1.90 |                                                      🔴    🔴🔴
        1.80 |                                                        🔴🔴
        1.70 |                                                    🔴
        1.60 |                                                🔴🔴
        1.50 |                                          🔴🔴🔴
        1.40 |                                      🔴🔴
    ULN 1.35 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        1.30 |                        🟢    🟢    🟢🟢
        1.20 |        🟢    🟢    🟢
        1.10 |🟢
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : Feb 2019 -> Sep 2019 (7 mo); Mar 2020 -> Sep 2020 (6 mo)

[2] eGFR (mL/min/1.73m2)  ref >=60; KDIGO stage boundaries shown
          69 |🟢      🟢
          66 |              🟢
          63 |                    🟢  🟢
          60 |                                    🟢
      LLN 60 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          57 |                              🔴      🔴
          54 |                                      🔴
          51 |                                        🔴
          48 |                                          🔴🔴
          45 |                                              🔴
  G3a|G3b 45 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          42 |                                                🔴🔴
          39 |                                                    🔴
          36 |                                                      🔴🔴🔴
          33 |                                                      🔴  🔴  🔴
          30 |                                                              🔴
   G3b|G4 30 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                                                            x
 gaps >=6 mo : Feb 2019 -> Sep 2019 (7 mo); Mar 2020 -> Sep 2020 (6 mo)

[3] BUN (mg/dL)  ref 7-20 (LLN 7 below chart)
          50 |                                                      🔴
          46 |
          42 |                                                      🔴      🔴
          38 |                                                          🔴
          34 |                                                    🔴
          30 |                                            🔴
          26 |                                      🔴🔴🔴
          22 |                                      🔴
      ULN 20 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          18 |
          14 |🟢
          10 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :        x     x     x   x     x     x         x x x     x   x
 gaps >=6 mo : Feb 2019 -> Mar 2022 (37 mo); Sep 2022 -> May 2023 (8 mo)

[4] POTASSIUM (mEq/L)  ref 3.5-5.1
         6.4 |                                                      🟡
         6.2 |
         6.0 |                                                      🔴    🟡🔴
         5.8 |                                                        🔴🔴🟡🔴
         5.6 |                                              🔴🟡🔴        🔴
         5.4 |                                            🔴
         5.2 |                                      🔴              🔴
     ULN 5.1 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         5.0 |                                                🟢
         4.8 |                                          🟢
         4.6 |
         4.4 |                              🟢
         4.2 |
         4.0 |🟢            🟢                        🟡
         3.8 |
         3.6 |
     LLN 3.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :        x           x   x           x               x
 gaps >=6 mo : Feb 2019 -> Mar 2020 (13 mo); Mar 2020 -> Aug 2021 (17 mo); Aug 2021 -> Apr 2022 (8 mo)

[5] SODIUM (mEq/L)  ref 136-145
         146 |
     ULN 145 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         144 |
         142 |
         140 |              🟢
         138 |                                      🟢  🟢              🟢
         136 |
     LLN 136 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         134 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :x       x           x   x     x     x   x   x x x x x x x   x x
 gaps >=6 mo : NO RESULTS before Mar 2020 (record starts Feb 2019); Mar 2020 -> Apr 2022 (25 mo); Jul 2022 -> Dec 2023 (17 mo)

[6] CO2 / BICARBONATE (mEq/L)  ref 22-29 (ULN 29 above chart)
          24 |
          23 |
          22 |                                          🟢
      LLN 22 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          21 |                                              🔴
          20 |                                                🔴🔴
          19 |                                                    🔴🔴
          18 |                                                        🔴🔴
   treat <18 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          17 |                                                          🔴  🔴
          16 |                                                              🔴
          15 |                                                      🔴
          14 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :x       x     x     x   x     x     x x x   x               x
 gaps >=6 mo : NO RESULTS before Jul 2022 (record starts Feb 2019)

[7] GLUCOSE, lab/visit (mg/dL)  ref fasting 70-99
         210 |
         200 |                                                      🔴
         190 |
         180 |                                                      🔴🔴🔴
         170 |                                                🔴            🔴
         160 |                                                🔴  🔴
         150 |                                      🔴🔴  🔴
         140 |                              🔴    🔴
         130 |                                                          🔴
         120 |        🔴    🔴        🔴
         110 |🔴                                    🔴
         100 |
      ULN 99 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          90 |
          80 |
          70 |
      LLN 70 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          60 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                    x                     x   x   x         x
 gaps >=6 mo : Feb 2019 -> Sep 2019 (7 mo); Mar 2020 -> Feb 2021 (12 mo)

[8] ALBUMIN (g/dL)  ref 3.5-5.0 (ULN 5.0 above chart)
         3.8 |
         3.7 |                                          🟢
         3.6 |                                            🟢
         3.5 |                                              🟢
     LLN 3.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         3.4 |
         3.3 |                                                🔴
         3.2 |                                                  🔴
         3.1 |                                                          🔴
         3.0 |                                                        🔴
         2.9 |                                                          🔴  🔴
         2.8 |                                                              🔴
         2.7 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :x       x     x     x   x     x     x x x           x x     x
 gaps >=6 mo : NO RESULTS before Jul 2022 (record starts Feb 2019); Apr 2023 -> Oct 2023 (6 mo)

[9] CALCIUM, total (mg/dL)  ref 8.5-10.5 (uncorrected for albumin)
        10.6 |
    ULN 10.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        10.4 |
        10.2 |
        10.0 |
         9.8 |
         9.6 |
         9.4 |
         9.2 |                                          🟢              🟢
         9.0 |
         8.8 |
         8.6 |
     LLN 8.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         8.4 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :x       x     x     x   x     x     x x x   x x x x x x x   x x
 gaps >=6 mo : NO RESULTS before Jul 2022 (record starts Feb 2019); Jul 2022 -> Dec 2023 (17 mo)
```

**CMP data table.** † = glucose reported in mmol/L without units (per `lab_results.csv` footnote); shown converted to mg/dL (x 18.016), with the original value in Notes.

| Date       | Glu      | BUN    | Cr       | eGFR   | Na     | K                   | CO2    | Alb     | Ca     | Source   | Notes                                                                                                |
|------------|----------|--------|----------|--------|--------|---------------------|--------|---------|--------|----------|------------------------------------------------------------------------------------------------------|
| 2019-02-14 | 🔴 108H  | 🟢 14  | 🟢 1.12  | 🟢 70  | —      | 🟢 4.1              | —      | —       | —      | ARC      |                                                                                                      |
| 2019-09-22 | 🔴 115H  | —      | 🟢 1.16  | 🟢 68  | —      | —                   | —      | —       | —      | ARC      |                                                                                                      |
| 2020-03-10 | 🔴 118H  | —      | 🟢 1.19  | 🟢 66  | 🟢 139 | 🟢 4.0              | —      | —       | —      | ARC      |                                                                                                      |
| 2020-09-18 | —        | —      | 🟢 1.22  | 🟢 64  | —      | —                   | —      | —       | —      | ARC      | EGFR archive flagged LOW in error                                                                    |
| 2021-02-28 | 🔴 124H  | —      | 🟢 1.25  | 🟢 62  | —      | —                   | —      | —       | —      | ARC      | EGFR archive flagged LOW in error                                                                    |
| 2021-08-11 | 🔴 138H  | —      | 🟢 1.29  | 🔴 59L | —      | 🟢 4.4              | —      | —       | —      | ARC      |                                                                                                      |
| 2022-02-03 | 🔴 143H  | —      | 🟢 1.31  | 🟢 60  | —      | —                   | —      | —       | —      | ARC      | EGFR archive flagged LOW (borderline)                                                                |
| 2022-03-04 | 🔴 106†H | 🔴 22H | 🟢 1.34  | 🔴 58L | —      | —                   | —      | —       | —      | LAB      | GLU lab flagged NORMAL vs 3.9-6.1 mmol/L range; †5.9 mmol/L converted                                |
| 2022-04-03 | 🔴 147H  | 🔴 24H | 🔴 1.39H | 🔴 55L | 🟢 138 | 🔴 5.2H             | —      | —       | —      | LAB      | GLU fasting                                                                                          |
| 2022-06-15 | 🔴 150†H | 🔴 26H | 🔴 1.44H | 🔴 51L | —      | 🟡 3.9?             | —      | —       | —      | LAB/NEPH | †8.3 mmol/L converted; K patient-reported; no K in lab file for this date                            |
| 2022-07-28 | —        | 🔴 27H | 🔴 1.47H | 🔴 49L | 🟢 137 | 🟢 4.8              | 🟢 22  | 🟢 3.7  | 🟢 9.1 | NEPH     |                                                                                                      |
| 2022-09-22 | 🔴 152H  | 🔴 28H | 🔴 1.51H | 🔴 48L | —      | 🔴 5.4H             | —      | 🟢 3.6  | —      | LAB      |                                                                                                      |
| 2022-11-03 | —        | —      | 🔴 1.54H | 🔴 45L | —      | 🔴 5.5H             | 🔴 21L | 🟢 3.5  | —      | NEPH     |                                                                                                      |
| 2023-01-10 | 🔴 164†H | —      | 🔴 1.58H | 🔴 44L | —      | 🟡 5.6H? / 🟢 5.1   | 🔴 20L | 🔴 3.3L | —      | LAB/PCP  | †9.1 mmol/L converted; K AM; lab: possible hemolysis; K PM point-of-care recheck                     |
| 2023-02-22 | 🔴 171H  | —      | —        | —      | —      | —                   | —      | —       | —      | ENDO     | GLU fasting                                                                                          |
| 2023-04-04 | —        | —      | 🔴 1.65H | 🔴 41L | —      | 🔴 5.5H             | 🔴 20L | 🔴 3.2L | —      | NEPH     |                                                                                                      |
| 2023-05-18 | 🔴 162H  | 🔴 34H | 🔴 1.71H | 🔴 39L | —      | —                   | 🔴 19L | —       | —      | LAB      |                                                                                                      |
| 2023-05-30 | 🔴 158H  | —      | —        | —      | —      | —                   | —      | —       | —      | ENDO     | GLU fasting                                                                                          |
| 2023-08-10 | 🔴 203H  | 🔴 48H | 🔴 2.04H | 🔴 32L | —      | 🟡 6.4H? / 🔴 6.1H  | 🔴 15L | —       | —      | HOSP     | CR admission, AKI; EGFR AKI; K outpatient draw; hospital suspects hemolysis; K admission 14:30       |
| 2023-08-14 | 🔴 179H  | 🔴 40H | 🔴 1.89H | 🔴 35L | —      | 🔴 5.2H             | 🔴 19L | —       | —      | HOSP     | CR discharge; K discharge                                                                            |
| 2023-09-06 | 🔴 176H  | —      | —        | —      | —      | —                   | —      | —       | —      | ENDO     | GLU fasting                                                                                          |
| 2023-10-10 | —        | —      | 🔴 1.82H | 🔴 37L | —      | 🔴 5.8H             | 🔴 18L | 🔴 3.0L | —      | NEPH     |                                                                                                      |
| 2023-11-02 | 🔴 133†H | 🔴 36H | 🔴 1.79H | 🔴 36L | —      | 🔴 5.7H             | 🔴 18L | 🔴 3.1L | —      | LAB      | GLU flow sheet same day: 168; †7.4 mmol/L converted                                                  |
| 2023-12-14 | 🔴 178H  | 🔴 38H | 🔴 1.84H | 🔴 34L | 🟢 138 | 🔴 5.7H             | 🔴 17L | 🔴 2.9L | 🟢 9.2 | TX       |                                                                                                      |
| 2024-01-25 | —        | —      | —        | —      | —      | 🟡 5.9H? / 🟡 5.7H? | —      | —       | —      | RX       | K pharmacy-reported; conflicts with PCP 5.7; K PCP chart value cited by pharmacy; conflicts with 5.9 |
| 2024-01-30 | —        | —      | 🔴 1.93H | —      | —      | 🟡 5.9H?            | —      | —       | —      | CARD     | K cardiology: possible hemolysis                                                                     |
| 2024-02-10 | —        | —      | —        | —      | —      | 🔴 5.6H             | —      | —       | —      | RX       | K recheck before lisinopril refill                                                                   |
| 2024-03-14 | 🔴 168H  | 🔴 40H | 🔴 1.89H | 🔴 33L | —      | 🔴 5.8H             | 🔴 17L | 🔴 2.9L | —      | LAB      |                                                                                                      |
| 2024-04-17 | —        | —      | 🔴 1.95H | 🔴 31L | —      | 🔴 6.0H             | 🔴 16L | 🔴 2.8L | —      | NEPH     |                                                                                                      |

**Reference ranges (adult male, age 60 to 65)**

| Analyte | Range used | Age/sex notes |
|---|---|---|
| Creatinine | 0.74–1.35 mg/dL (LAB, male) | Transplant center uses 0.6–1.2 mg/dL. |
| eGFR | ≥60 mL/min/1.73m² | KDIGO: <60 means reduced GFR at any age. The average for a healthy man in his 60s is about 85. Stages: G3a 45–59, G3b 30–44, G4 15–29. |
| BUN | 7–20 mg/dL (LAB) | Transplant center 8–25. Some labs use an upper limit of about 23–24 for adults over 60. |
| Potassium | 3.5–5.1 mEq/L (LAB) | Transplant center 3.5–5.5. Not age/sex dependent. |
| Sodium | 136–145 mEq/L (LAB) | Not age/sex dependent. |
| CO2 (bicarbonate) | 22–29 mEq/L (LAB) | Transplant center 23–29. KDIGO 2024 suggests drug treatment when below 18 (dashed line "treat <18"). |
| Glucose | 70–99 mg/dL fasting | Fasting status is usually undocumented; for a random sample, <140 is normal. The LAB file also used 70–100 mg/dL and 3.9–6.1 mmol/L (≈70–110 mg/dL). |
| Albumin | 3.5–5.0 g/dL | Levels are slightly lower in older adults; below 3.5 is still abnormal. |
| Calcium (total) | 8.5–10.5 mg/dL (TX) | Reported uncorrected. Low albumin makes the total calcium read falsely low. |

**Clinical observations**

- **Creatinine / eGFR / BUN: declining, and the decline is speeding up.** eGFR fell steadily from 70 (02/2019) to 31 (04/2024). That is about 7.5 mL/min per year overall and **about 12.7 mL/min per year since 03/2022**, well above KDIGO's 5 mL/min per year threshold for "rapid progression." There was AKI in 08/2023 (creatinine 2.04, eGFR 32); function recovered to about 35–37 but never back to the pre-AKI level of 39. BUN has risen in parallel (14 to 40; 48 at the AKI). **No eGFR below 30 has been recorded**, so by the numbers the patient is in KDIGO G3b, close to the G4 boundary (see Section 8 on stage labels in the notes).
- **Potassium: worsening, with sustained high values.** K was 4.0–4.4 in 2019–2021. Since 04/2022, **12 of 14 reliable results are above 5.1**, and **every result since 10/2023 is 5.6 or higher** (latest 6.0 on 04/17/2024). Six values are 🟡 questionable (hemolysis, conflicting reports, or unverified). Even with those set aside, the trend is real. Same-day rechecks have come back lower (5.6 → 5.1 on 01/10/2023; 6.4 → 6.1 on 08/10/2023), so some single high draws are inflated. No repeat is documented after the 6.0 on 04/17/2024.
- **CO2: worsening metabolic acidosis.** 11 of 12 results are below 22. It has been **18 or lower since 10/2023 and below 18 since 12/2023** (latest 16), even on sodium bicarbonate, which was started 01/2023 and increased 11/2023.
- **Glucose: consistently high.** All 20 lab/visit values are above 99 mg/dL. Values since 2023 range from 133 to 203, mostly 158–179. See Section 3.
- **Albumin: declining.** It went from 3.7 to 2.8 g/dL; 7 of 10 results are below 3.5. Likely contributors are urinary protein loss (UPCR 620), poor intake (documented nausea and reduced appetite), and inflammation.
- **Sodium and calcium: normal, but rarely measured.** Sodium was measured on 4 dates, all 137–139. Calcium was measured **only twice** (9.1, 9.2), which is too few for a patient on calcitriol. Corrected for albumin 2.9 (standard formula, a calculation rather than a measured value), the 12/14/2023 calcium would be about 10.1 mg/dL, near the upper limit.

**Treatment recommendations (several CMP markers were out of range more than once)**

1. **Hyperkalemia, urgent.** Repeat potassium within days on a carefully drawn, non-hemolyzed sample (plasma if available), and get an ECG if it is ≥6.0. To keep renin-angiotensin blockade for kidney protection, consider starting a **potassium binder** (patiromer or sodium zirconium cyclosilicate; note the sodium load of SZC given edema and BP). Refer to a renal dietitian for a low-potassium diet, and check for salt substitutes and potassium-raising drugs. If K stays above 5.5 despite these steps, **reduce lisinopril rather than stop it abruptly**, per KDIGO. Give clear written hold instructions: the patient kept taking lisinopril during the 01/2024 pharmacy hold.
2. **Kidney protection.** **No SGLT2 inhibitor appears in any medication list.** KDIGO 2022/2024 recommends one for type 2 diabetes with CKD at eGFR ≥20 (strong recommendation), which fits this patient at eGFR 31. Also avoid NSAIDs and minimize IV contrast, and confirm progress on AV access and the transplant timeline (nephrology plans from 04/2023 and 04/2024).
3. **Metabolic acidosis.** Titrate alkali therapy toward the normal range, while watching the sodium load against BP and edema. Correcting acidosis also lowers potassium. Persistent severe acidosis and hyperkalemia despite treatment are factors nephrology weighs when planning kidney replacement therapy.
4. **Low albumin.** Get a formal nutrition assessment with a renal dietitian. For diabetes with CKD not on dialysis, KDIGO suggests protein of 0.8 g/kg/day, individualized when malnutrition is present. Look into the nausea and poor appetite: uremia, medications, and gastroparesis are possibilities.
5. **Calcium monitoring.** Check albumin-corrected or ionized calcium on every draw while calcitriol is used or adjusted.

---

## 2. Complete Blood Count (CBC)

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

[1] HEMOGLOBIN (g/dL)  ref 13.5-17.5 (adult male); anemia in men <13.0 (WHO/KDIGO)
        15.0 |🟢
        14.5 |
        14.0 |              🟢        🟢
        13.5 |
    LLN 13.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        13.0 |
 anemia 13.0 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        12.5 |                                    🔴
        12.0 |                                        🟡🔴
        11.5 |
        11.0 |                                              🔴🔴
        10.5 |                                                  🔴🔴
        10.0 |                                                      🔴🔴🔴
         9.5 |                                                            🔴🔴
         9.0 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : Feb 2019 -> Mar 2020 (13 mo); Mar 2020 -> Feb 2021 (12 mo); Feb 2021 -> Feb 2022 (11 mo)

[2] HEMATOCRIT (%)  ref 41-53 (adult male)
        54.0 |
      ULN 53 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        52.0 |
        50.0 |
        48.0 |
        46.0 |
        44.0 |
        42.0 |
      LLN 41 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        40.0 |
        38.0 |
        36.0 |                                        🔴
        34.0 |
        32.0 |
        30.0 |                                                          🔴
        28.0 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                        x
 gaps >=6 mo : NO RESULTS before Jun 2022 (record starts Feb 2019); Jun 2022 -> Dec 2023 (18 mo)

[3] WBC (K/uL)  ref 4.5-11.0
        12.0 |
    ULN 11.0 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        11.0 |
        10.0 |
         9.0 |
         8.0 |                                                          🟢
         7.0 |                        🟢              🟢
         6.0 |
         5.0 |
     LLN 4.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         4.0 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Feb 2021 (record starts Feb 2019); Feb 2021 -> Jun 2022 (16 mo); Jun 2022 -> Dec 2023 (18 mo)

[4] PLATELETS (K/uL)  ref 150-400
         420 |
     ULN 400 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         400 |
         380 |
         360 |
         340 |
         320 |
         300 |
         280 |
         260 |
         240 |
         220 |                                        🟢
         200 |                                                          🟢
         180 |
         160 |
     LLN 150 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         140 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                        x
 gaps >=6 mo : NO RESULTS before Jun 2022 (record starts Feb 2019); Jun 2022 -> Dec 2023 (18 mo)
```

| Date       | Hgb       | Hct      | WBC    | Plt    | Source | Notes                                                                                 |
|------------|-----------|----------|--------|--------|--------|---------------------------------------------------------------------------------------|
| 2019-02-14 | 🟢 14.8   | —        | —      | —      | ARC    |                                                                                       |
| 2020-03-10 | 🟢 14.2   | —        | —      | —      | ARC    |                                                                                       |
| 2021-02-28 | 🟢 14.0   | —        | 🟢 7.1 | —      | ARC    |                                                                                       |
| 2022-02-03 | 🔴 12.4L  | —        | —      | —      | ARC    |                                                                                       |
| 2022-06-15 | 🟡 11.8L? | 🔴 35.4L | 🟢 7.2 | 🟢 212 | LAB    | HGB specimen processing delay; earlier note cites 12.2; HCT same specimen as Hgb 11.8 |
| 2022-07-28 | 🔴 12.0L  | —        | —      | —      | NEPH   |                                                                                       |
| 2022-11-03 | 🔴 11.2L  | —        | —      | —      | NEPH   |                                                                                       |
| 2023-01-10 | 🔴 10.9L  | —        | —      | —      | LAB    |                                                                                       |
| 2023-04-04 | 🔴 10.7L  | —        | —      | —      | NEPH   |                                                                                       |
| 2023-05-18 | 🔴 10.4L  | —        | —      | —      | LAB    |                                                                                       |
| 2023-08-10 | 🔴 9.9L   | —        | —      | —      | HOSP   |                                                                                       |
| 2023-10-10 | 🔴 10.0L  | —        | —      | —      | NEPH   |                                                                                       |
| 2023-11-02 | 🔴 10.1L  | —        | —      | —      | LAB    |                                                                                       |
| 2023-12-14 | 🔴 9.9L   | 🔴 30.1L | 🟢 7.8 | 🟢 198 | TX     |                                                                                       |
| 2024-01-30 | 🔴 9.5L   | —        | —      | —      | CARD   |                                                                                       |
| 2024-03-14 | 🔴 9.7L   | —        | —      | —      | LAB    |                                                                                       |
| 2024-04-17 | 🔴 9.4L   | —        | —      | —      | NEPH   | HGB ESA started 4/19/24                                                               |

**Reference ranges (adult male, 60 to 65).** Hemoglobin 13.5–17.5 g/dL (LAB); WHO and KDIGO define anemia in men as **<13.0 g/dL**, with no separate threshold for older men. Hematocrit 41–53%. WBC 4.5–11.0 K/uL. Platelets 150–400 K/uL. Single values (12/14/2023): RBC **3.31 M/uL (low; ref 4.5–5.9)**, MCV 91 fL (normal 80–100), MCHC 32.8 g/dL (normal 32–36).

**Clinical observations**

- **Hemoglobin: steady decline, 14.8 → 9.4 g/dL.** **All 14 values since 02/2022 are below range.** Notably, there was a **1.6 g/dL drop between 02/2021 (14.0) and 02/2022 (12.4)**, when eGFR was still about 60. CKD usually causes significant anemia only at lower GFR, so iron deficiency or blood loss should be ruled out. The anemia is normocytic (MCV 91), which does not exclude iron deficiency in CKD.
- **Iron status is unknown.** Iron studies were "ordered" on 06/15/2022. Ferrous sulfate was filled **once** (06/17/2022) with no refills. **No ferritin, TSAT or iron results exist in any uploaded file.** Epoetin alfa was started 04/19/2024 without documented iron studies.
- Hematocrit is low on both dates (35.4, 30.1). WBC and platelets are normal and stable.

**Treatment recommendations (hemoglobin and hematocrit were out of range more than once)**

1. **Get iron studies now** (ferritin, TSAT), plus B12, folate and a reticulocyte count. KDIGO anemia guidance is to find and correct iron deficiency before or alongside ESA therapy.
2. **If he is iron deficient, do a GI evaluation** (colonoscopy ± EGD). Iron deficiency in a 65-year-old man needs a source found, and age-appropriate cancer screening is needed for transplant listing anyway.
3. **Replete iron if needed.** IV iron is often preferred in CKD when oral iron fails or is not tolerated.
4. **ESA safety.** Check Hgb at least monthly while starting the ESA, and do not push Hgb above 11.5 g/dL (KDIGO). **Watch BP closely**, because ESAs can raise BP and his BP is already uncontrolled (Section 5).

---

## 3. Hemoglobin A1c (diabetes control)

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

HbA1c (%)  normal <5.7; individualized target lines at 7.0 and 8.0 (transplant threshold)
         8.7 |                                                        🔴  🔴🔴
         8.5 |                                                    🔴    🔴    🔴
         8.3 |                                                    🔴
         8.1 |                                                🔴
 listing 8.0 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         7.9 |
         7.7 |                                            🔴
         7.5 |                                      🔴
         7.3 |                                      🔴
         7.1 |                              🔴    🔴
   goal <7.0 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         6.9 |
         6.7 |                        🔴
         6.5 |              🔴    🔴
         6.3 |        🔴
         6.1 |
         5.9 |🔴
         5.7 |
    ULN <5.7 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         5.5 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                                        x             x
 gaps >=6 mo : Feb 2019 -> Sep 2019 (7 mo); Mar 2020 -> Sep 2020 (6 mo)
```

| Date       | HbA1c % | Source | Notes                           |
|------------|---------|--------|---------------------------------|
| 2019-02-14 | 🔴 5.9H | ARC    |                                 |
| 2019-09-22 | 🔴 6.2H | ARC    |                                 |
| 2020-03-10 | 🔴 6.4H | ARC    |                                 |
| 2020-09-18 | 🔴 6.6H | ARC    |                                 |
| 2021-02-28 | 🔴 6.8H | ARC    |                                 |
| 2021-08-11 | 🔴 7.0H | ARC    |                                 |
| 2022-02-03 | 🔴 7.1H | ARC    |                                 |
| 2022-03-04 | 🔴 7.2H | LAB    | metformin stopped this day      |
| 2022-04-03 | 🔴 7.4H | LAB    |                                 |
| 2022-09-22 | 🔴 7.8H | LAB    |                                 |
| 2023-01-10 | 🔴 8.1H | LAB    |                                 |
| 2023-02-22 | 🔴 8.2H | ENDO   | point-of-care; glargine started |
| 2023-05-18 | 🔴 8.3H | LAB    |                                 |
| 2023-05-30 | 🔴 8.4H | ENDO   |                                 |
| 2023-09-06 | 🔴 8.6H | ENDO   | aspart added                    |
| 2023-12-14 | 🔴 8.5H | TX     |                                 |
| 2024-01-18 | 🔴 8.7H | ENDO   |                                 |
| 2024-03-14 | 🔴 8.6H | LAB    |                                 |
| 2024-05-14 | 🔴 8.5H | ENDO   |                                 |

**Reference ranges (adult male, 60 to 65).** Normal <5.7%; prediabetes 5.7–6.4%; diabetes ≥6.5%. **Individual treatment target:** <7.0% is the general ADA goal; **<8.0%** is appropriate for an older adult with multiple comorbidities and is also **the transplant program's listing threshold.**

**Clinical observations**

- **Steadily worsening.** HbA1c rose from 5.9% (02/2019) by about 0.4 points per year to a peak of 8.7% (01/2024). It has **plateaued at 8.5–8.7% since 09/2023** despite adding basal insulin (02/2023) and mealtime insulin (09/2023). **All 9 values since 01/2023 are above the 8.0% transplant threshold.**
- **Metformin was stopped 03/04/2022 at eGFR 58**, which is above the labeled eGFR limits (full dose allowed at eGFR ≥45; reduced dose at 30–44). HbA1c rose every quarter after that. Restarting it now is **not** advisable given eGFR 31, recent AKI and bicarbonate 16, but the history is relevant context.
- **HbA1c is less reliable in this patient.** Advanced CKD, anemia, recent ESA start (which pushes HbA1c falsely low), and possible iron deficiency (which can push it falsely high) all distort the result. The 05/14/2024 value was drawn 25 days after ESA start, so true glucose control may be worse than 8.5% suggests.

**Treatment recommendations (all values out of range)**

1. **Start a continuous glucose monitor (CGM).** Endocrinology discussed it 01/18/2024. Use time-in-range and GMI rather than relying on HbA1c alone.
2. **Add an SGLT2 inhibitor** (same drug as CMP recommendation 2). It is mainly for kidney and heart protection; glucose lowering is modest at eGFR about 30.
3. **Reconsider a GLP-1 receptor agonist.** Semaglutide has kidney-outcome evidence in T2D with CKD (FLOW trial). Weigh this against his existing nausea, poor appetite, weight loss and low albumin; these may make it unsuitable for now.
4. **Keep titrating basal/bolus insulin** toward <8.0%, watching for hypoglycemia. Insulin is cleared more slowly as eGFR falls.
5. Confirm he completed diabetes education (referred 09/06/2023; completion not documented), and **confirm his insulin supply**: no insulin fills appear in the pharmacy record.

---

## 4. CKD mineral-bone markers and proteinuria

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

PHOSPHORUS (mg/dL)  ref 2.5-4.5 (LLN 2.5 below chart)
         6.2 |
         6.0 |                                                              🔴
         5.8 |                                                          🔴
         5.6 |                                                    🔴  🔴
         5.4 |
         5.2 |                                                🔴🔴
         5.0 |                                            🔴🔴
         4.8 |
         4.6 |
     ULN 4.5 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         4.4 |
         4.2 |                                          🟢
         4.0 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Jul 2022 (record starts Feb 2019)
```

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

PTH, intact (pg/mL)  ref 10-65 (LLN 10 below chart)
         280 |                                                              🔴
         260 |
         240 |
         220 |                                                          🔴
         200 |                                                        🔴
         180 |
         160 |
         140 |
         120 |                                                  🔴
         100 |                                              🔴
          80 |                                          🔴
      ULN 65 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          60 |
          40 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                                            x   x   x
 gaps >=6 mo : NO RESULTS before Jul 2022 (record starts Feb 2019); Apr 2023 -> Oct 2023 (6 mo)
```

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

URINE PROTEIN/CREATININE RATIO (mg/g)  normal <150; KDIGO A3 >500
         650 |
         600 |                                                              🔴
         550 |                                                        🔴
     A3 >500 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         500 |
         450 |
         400 |                                                  🔴
         350 |                                              🔴
         300 |                                          🔴
         250 |
         200 |
         150 |
    ULN <150 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         100 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
   no result :                                            x   x   x     x
 gaps >=6 mo : NO RESULTS before Jul 2022 (record starts Feb 2019); Apr 2023 -> Oct 2023 (6 mo); Oct 2023 -> Apr 2024 (6 mo)
```

| Date       | Phos    | PTH     | UPCR    | Ca     | Source | Notes                  |
|------------|---------|---------|---------|--------|--------|------------------------|
| 2022-07-28 | 🟢 4.2  | 🔴 68H  | 🔴 280H | 🟢 9.1 | NEPH   |                        |
| 2022-09-22 | 🔴 4.9H | —       | —       | —      | LAB    |                        |
| 2022-11-03 | 🔴 5.0H | 🔴 92H  | 🔴 340H | —      | NEPH   |                        |
| 2023-01-10 | 🔴 5.2H | —       | —       | —      | LAB    |                        |
| 2023-04-04 | 🔴 5.3H | 🔴 124H | 🔴 420H | —      | NEPH   | PTH calcitriol started |
| 2023-05-18 | 🔴 5.5H | —       | —       | —      | LAB    |                        |
| 2023-10-10 | 🔴 5.6H | 🔴 198H | 🔴 510H | —      | NEPH   |                        |
| 2023-12-14 | 🔴 5.8H | 🔴 221H | —       | 🟢 9.2 | TX     |                        |
| 2024-03-14 | 🔴 5.9H | —       | —       | —      | LAB    |                        |
| 2024-04-17 | 🔴 6.1H | 🔴 276H | 🔴 620H | —      | NEPH   |                        |

**Reference ranges (adult male, 60 to 65).** Phosphorus 2.5–4.5 mg/dL. Intact PTH 10–65 pg/mL; KDIGO does not define an optimal PTH for CKD not on dialysis, and a persistent rise is treated as a concern. Urine protein/creatinine ratio: normal <150 mg/g; KDIGO categories A2 = 150–500 and A3 >500. 25-OH vitamin D 30–100 ng/mL, with deficiency <20 (single value: **18 on 12/14/2023**). These ranges are not age- or sex-specific.

**Clinical observations**

- **Phosphorus: steadily worsening.** 4.2 → 6.1 mg/dL; 9 of 10 results high. It kept rising after sevelamer was started (09/2022) and increased (08/2023).
- **PTH: severe and accelerating.** 68 → 276 pg/mL (**about 4x the upper limit**); all 6 values high. It kept rising after calcitriol was started (04/2023). **Vitamin D deficiency (18 ng/mL)** has not been treated: no cholecalciferol or ergocalciferol appears in any medication list.
- **UPCR: steadily worsening.** 280 → 620 mg/g. It crossed into **KDIGO A3 (severe) in 10/2023**. **No urine protein or albumin test exists for 2019–2021**, even though diabetes care calls for one every year.

**Treatment recommendations (all three markers out of range more than once)**

1. **Phosphorus:** renal dietitian, with a focus on phosphate additives in processed food. **Check the actual sevelamer dose and whether he takes it with meals**: the dispensed quantities do not match the documented dose (Section 8). If phosphorus stays high, nephrology can consider changing or adding a binder; KDIGO advises limiting calcium-based binders.
2. **PTH:** **replete 25-OH vitamin D first** (KDIGO 2017), control phosphorus, then adjust calcitriol only with corrected calcium and phosphorus monitoring. The 10/10/2023 plan to increase calcitriol has no matching pharmacy fill.
3. **Proteinuria:** SGLT2 inhibitor; renin-angiotensin blockade at the highest dose potassium allows (binder, Section 1); BP control (Section 5). Finerenone is indicated for T2D with CKD and albuminuria but is generally **not started when K >5.0**, so it only becomes an option once potassium is controlled. Track urine albumin/creatinine ratio every 3–6 months.

---

## 5. Vital signs

### 5a. Blood pressure

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

[1] SYSTOLIC BP (mmHg)  normal <120; goal <130 (DM+CKD); cardiology listing condition <140
         185 |                                                      🔴
         180 |
         175 |
         170 |                                                            🔴🔴🔴
         165 |                                                      🟡  🔴🔴
         160 |                                      🔴    🔴      🔴
         155 |                                                🔴🔴
         150 |                                      🔴🔴      🔴    🔴
         145 |
         140 |
listing <140 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         135 |
         130 |
   goal <130 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         125 |
         120 |                                                      🟡
 normal <120 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         115 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)

[2] DIASTOLIC BP (mmHg)  normal/goal <80; cardiology listing condition <90
         113 |                                                      🔴
         110 |
         107 |                                                              🔴
         104 |                                                            🔴  🔴
         101 |                                                      🟡  🔴🔴
          98 |                                            🔴    🔴🔴
          95 |                                      🔴        🔴    🔴
          92 |                                        🔴
 listing <90 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          89 |
          86 |
          83 |
          80 |
  normal <80 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          77 |                                                      🟡
          74 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)
```

**Reference ranges (adult, 60 to 65; not sex-specific).** Normal is <120/<80 (ACC/AHA). The goal for diabetes with CKD is <130/80 (ADA, ACC/AHA); KDIGO 2021 suggests systolic <120 if tolerated. Cardiology's condition for transplant listing is **<140/90**.

**Observation: uncontrolled and rising.** **All 16 reliable readings are above normal and above the listing condition**, ranging from 148/92 to 184/112. BP improved slightly to 148/92 in 06/2022 and has climbed since 01/2023 (154/96 → 172/106 → 169/103). He had hypertensive urgency at 184/112 on 08/10/2023. **There is already heart damage:** LVH on ECG and echo, LVEF 60% → 52%, grade 1 diastolic dysfunction, BNP 186. Worsening edema (furosemide increased 03/2024) and falling SpO2 suggest fluid overload is part of the cause.

**Treatment recommendations**

1. He is already on **maximum-dose amlodipine 10 mg and lisinopril 40 mg**. Add-on options for the prescriber:
   - **Better loop diuretic dosing.** At eGFR about 30, higher or twice-daily dosing is often needed.
   - A **beta-blocker** (e.g., carvedilol, given the LVH and falling EF).
   - **Chlorthalidone**, which is effective in stage 4 CKD (CLICK trial); monitor K, Na and glucose.
   - **Hydralazine/nitrate.**
   - Spironolactone is limited by his hyperkalemia.
2. Start home BP monitoring, review adherence, and limit sodium to <2 g/day. Remember that sodium bicarbonate and SZC add sodium.
3. **Recheck BP 2–4 weeks after the ESA start (04/19/2024).**

### 5b. Heart rate

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

HEART RATE (bpm)  ref 60-100
         102 |
     ULN 100 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          98 |
          94 |
          90 |                                                              🟢
          86 |                                                🟢    🟡  🟢🟢  🟢
          82 |                                      🟢    🟢  🟢  🟢
          78 |                                      🟢🟢        🟢
          74 |
          70 |                                                      🟡
          66 |
          62 |
      LLN 60 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          58 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)
```

**Reference range (adult, not age/sex-specific):** 60–100 bpm. **Observation:** all values are normal, with a slow upward drift from 76–82 (2022) to 84–88 (2024). That fits worsening anemia and fluid overload. No treatment needed. If a beta-blocker is added, there is room in the heart rate.

### 5c. Weight and BMI

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

WEIGHT (lb)  height 5'11": BMI 18.5-24.9 = ~133-178 lb (LLN below chart)
         220 |
      BMI 30 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         215 |                                            🔴
         210 |                                      🔴🔴
         205 |                                                🔴🔴  🟡  🔴
         200 |                                                    🔴      🔴🔴🔴
         195 |
         190 |
         185 |
         180 |
      BMI 25 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         175 |
         170 |
         165 |                                                      🟡
         160 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)
```

**Reference range (male, 5'11"):** BMI 18.5–24.9, which is about **133–178 lb**. BMI 25 ≈ 179 lb and BMI 30 ≈ 215 lb (lines are computed from the documented height; no BMI values were calculated for the patient). The only documented BMI is **28.0 (01/30/2024, cardiology)**. In adults 65 and older, a BMI of 25–27 is not linked to higher mortality.

**Observation:** weight is in the overweight range, so all reliable values are 🔴 by BMI. **The real concern is unintentional loss:** 212 → 199 lb (−13 lb, about 6%) from 03/2022 to 05/2024, alongside falling albumin (3.7 → 2.8), poor appetite and nausea. Because edema has been worsening, fluid is probably hiding some of the true tissue loss. The 09/2022 jump to 215 lb came with leg swelling, so it was probably fluid.

**Treatment recommendation (more than one value out of range): do *not* pursue weight loss.** Start a renal-dietitian nutrition assessment (for example, subjective global assessment), track dry weight, and look into the nausea. His BMI of 28 is already within typical transplant-program limits.

### 5d. Oxygen saturation

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

SpO2 (%) on room air  ref 95-100
         100 |
          99 |                                                      🟡
          98 |                                        🟢
          97 |                                      🟢        🟢🟢
          96 |                                            🟢      🟢
          95 |                                                      🟡  🟢🟢  🟢
      LLN 95 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          94 |                                                              🔴
          93 |
          92 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)
```

**Reference range (adult at sea level, not age/sex-specific):** 95–100% on room air. **Observation:** SpO2 was 96–98% in 2022–early 2023, has been 94–95% since 08/2023, and was **94% on 03/14/2024 (the only low value)**. The slow decline, together with edema, BNP 186 and exertional shortness of breath, fits fluid overload and/or anemia. Only one value is out of range, so no formal recommendation is given; re-examine lungs and volume status at the next visit.

### 5e. Temperature

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

TEMPERATURE (F)  ref ~97.0-99.0
        99.2 |
    ULN 99.0 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        99.0 |
        98.8 |
        98.6 |                                                      🟡
        98.4 |                                        🟢
        98.2 |                                      🟢          🟢🟢        🟢
        98.0 |                                      🟢    🟢        🟡  🟢    🟢
        97.8 |                                                🟢          🟢
        97.6 |                                                🟢
        97.4 |
        97.2 |
        97.0 |
    LLN 97.0 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
        96.8 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)
```

**Reference range (adult):** about 97.0–99.0 °F; older adults often run at the low end. **Observation:** all values are normal and stable (97.6–98.4 °F, excluding the questionable 07/14/2023 entry).

### 5f. Clinic glucose (nursing flow sheet)

```text
Legend: 🟢 within reference range   🔴 outside reference range   🟡 questionable value (see notes)
        x = drawn/visit on that date but no result for this marker   1 column = 2 months

CLINIC GLUCOSE, nursing flow sheet (mg/dL)  ref fasting 70-99 (fasting status not recorded)
         180 |                                                            🔴
         170 |                                                      🟡  🔴  🔴🔴
         160 |                                                🔴🔴🔴
         150 |                                      🔴🔴  🔴
         140 |                                                🔴
         130 |
         120 |
         110 |
         100 |
      ULN 99 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          90 |                                                      🟡
          80 |
          70 |
      LLN 70 +- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
          60 |
             +------------+-----------+-----------+-----------+-----------+-----
              2019        2020        2021        2022        2023        2024
 gaps >=6 mo : NO RESULTS before Mar 2022 (record starts Feb 2019)
```

**Reference range:** fasting 70–99 mg/dL; fasting status was not recorded on the flow sheet. **Observation:** all 11 reliable values are high (138–175) and rising. **On dates that also have a lab glucose, the flow-sheet value matches it exactly 4 times and nearly 2 times, and conflicts 2 times.** So the flow sheet may have copied lab values rather than recording separate fingerstick tests (Section 8).

**Treatment recommendation (more than one value out of range):** same plan as Section 3: CGM, SGLT2 inhibitor, and insulin titration to <8.0%. Also have nursing record **fasting status and whether the value is a fingerstick or a copied lab result** at each visit, so this chart becomes usable.

**Vitals data table**

| Date       | SBP               | DBP             | HR            | Temp              | Wt                | SpO2          | FS-Glu            | Source | Notes                                                                               |
|------------|-------------------|-----------------|---------------|-------------------|-------------------|---------------|-------------------|--------|-------------------------------------------------------------------------------------|
| 2022-03-04 | 🔴 158H           | 🔴 96H          | 🟢 78         | 🟢 98.2           | 🔴 212H           | 🟢 97         | 🟡 147H?          | VIT    | flow-sheet glucose 147 vs same-day lab 5.9 mmol/L (~106)                            |
| 2022-04-04 | 🔴 152H           | 🔴 94H          | 🟢 82         | 🟢 97.9           | 🔴 209H           | 🟢 97         | 🔴 147H           | VIT    | BP transcribed "I52" = 152 (confirmed by amended 4/4/22 note)                       |
| 2022-06-15 | 🔴 148H           | 🔴 92H          | 🟢 76         | 🟢 98.4           | 🔴 208H           | 🟢 98         | 🔴 149H           | VIT    | glucose transcribed "I49"                                                           |
| 2022-09-22 | 🔴 162H           | 🔴 98H          | 🟢 80         | 🟢 98.1           | 🔴 215H           | 🟢 96         | 🔴 152H           | VIT    | HR transcribed "8O" = 80 (confirmed by 9/22/22 note)                                |
| 2023-01-10 | 🔴 154H / 🔴 151H | 🔴 96H / 🔴 94H | 🟢 84 / 🟢 81 | 🟢 97.8 / 🟢 97.6 | 🔴 206H / 🔴 206H | 🟢 97 / 🟢 97 | 🔴 162H / 🔴 138H | VIT    | AM; PM recheck                                                                      |
| 2023-03-15 | 🔴 156H           | 🔴 97H          | 🟢 79         | 🟢 98.3           | 🔴 204H           | 🟢 97         | 🔴 158H           | VIT    |                                                                                     |
| 2023-05-18 | 🔴 160H           | 🔴 99H          | 🟢 83         | 🟢 98.2           | 🔴 202H           | 🟢 96         | 🔴 162H           | VIT    |                                                                                     |
| 2023-05-30 | 🔴 160H           | 🔴 99H          | —             | —                 | 🔴 202H           | —             | —                 | ENDO   | endocrinology visit                                                                 |
| 2023-07-14 | 🟡 122H?          | 🟡 78?          | 🟡 70?        | 🟡 98.6?          | 🟡 165?           | 🟡 99?        | 🟡 91?            | VIT    | entire row inconsistent with patient (37-40 lb lighter); likely wrong patient/entry |
| 2023-08-10 | 🔴 184H           | 🔴 112H         | —             | —                 | —                 | —             | —                 | HOSP   | ED presentation, hypertensive urgency                                               |
| 2023-08-12 | 🟡 164H?          | 🟡 102H?        | 🟡 86?        | 🟡 98.0?          | 🟡 205H?          | 🟡 95?        | 🟡 171H?          | VIT    | clinic entry dated while patient was inpatient (8/10-8/14/23)                       |
| 2023-08-14 | 🔴 148H           | 🔴 94H          | —             | —                 | —                 | —             | —                 | HOSP   | hospital discharge                                                                  |
| 2023-11-02 | 🔴 166H           | 🔴 101H         | 🟢 85         | 🟢 98.1           | 🔴 203H           | 🟢 95         | 🔴 168H           | VIT    |                                                                                     |
| 2024-01-18 | —                 | —               | —             | —                 | 🔴 200H           | —             | —                 | ENDO   | endocrinology visit                                                                 |
| 2024-01-25 | 🔴 168H           | 🔴 104H         | 🟢 87         | 🟢 97.7           | 🔴 201H           | 🟢 95         | 🔴 175H           | VIT    |                                                                                     |
| 2024-01-30 | 🔴 166H           | 🔴 100H         | 🟢 84         | —                 | 🔴 201H           | 🟢 95         | —                 | CARD   | cardiology; L arm 164/98; RR 16; BMI 28.0 documented                                |
| 2024-03-14 | 🔴 172H           | 🔴 106H         | 🟢 88         | 🟢 98.3           | 🔴 200H           | 🔴 94L        | 🔴 168H           | VIT    |                                                                                     |
| 2024-05-09 | 🔴 169H           | 🔴 103H         | 🟢 86         | 🟢 98.1           | 🔴 199H           | 🟢 95         | 🔴 174H           | VIT    |                                                                                     |
| 2024-05-14 | —                 | —               | —             | —                 | 🔴 199H           | —             | —                 | ENDO   | endocrinology visit                                                                 |

---

## 6. Results with a single time point (no trend possible)

No trend chart is drawn for these, because each has only one dated result (LVEF's earlier value has no date).

| Marker | Value (date, source) | Reference (adult male) | Status |
|---|---|---|---|
| Chloride | 102 mEq/L (12/14/2023, TX) | 98–107 | 🟢 |
| Total protein | 6.1 g/dL (12/14/2023, TX) | 6.0–8.3 | 🟢 low-normal |
| Total bilirubin / ALT / AST | 0.6 mg/dL / 18 U/L / 22 U/L (12/14/2023, TX) | 0.2–1.2 / 7–56 / 10–40 | 🟢 |
| Magnesium | 1.9 mg/dL (12/14/2023, TX) | 1.7–2.2 | 🟢 |
| 25-OH vitamin D | 18 ng/mL (12/14/2023, TX) | 30–100 (deficient <20) | 🔴 L (see Section 4) |
| BNP | 186 pg/mL (01/30/2024, CARD) | <100 (often higher in CKD) | 🔴 H |
| Troponin I | <0.01 ng/mL (01/30/2024, CARD) | negative | 🟢 |
| INR | 1.0 (01/30/2024, CARD) | 0.8–1.2 | 🟢 |
| QTc | 448 ms (01/30/2024, CARD) | men: ≤430 normal, 431–450 borderline | 🔴 borderline (watch QT-prolonging drugs, e.g. metoclopramide; watch K swings) |
| Respiratory rate | 16 /min (01/30/2024, CARD) | 12–20 | 🟢 |
| LVEF (echo) | 60% (2019, no date given) → 52% (01/30/2024, CARD) | male 52–72% (ASE) | 🟢 at the lower limit; cardiology calls it mildly reduced because of the drop |
| Septum / posterior wall | 1.3 cm / 1.2 cm (01/30/2024, CARD) | male 0.6–1.0 cm | 🔴 LVH |
| Stress test | No ischemia; 6.1 METs (01/30/2024) | — | 🟢 |
| Transplant serologies | HIV, HBsAg, HCV negative; CMV IgG and EBV IgG positive; PRA 4%; ABO A+ (12/14/2023) | — | informational |

## 7. Markers requested but not found in the uploaded files

- **Thyroid markers (TSH, free T4, T3): none.** `endocrine_and_thyroid_notes.txt` covers only diabetes. The only "thyroid" words in any file refer to **para**thyroid (PTH). I can't chart thyroid trends. If thyroid labs exist, please upload them.
- **Iron studies (ferritin, TSAT, serum iron, TIBC): none.** Ordered 06/15/2022; no results anywhere.
- **Hematology visit notes: not included** in the upload. No hematology consult or iron-deficiency workup document was provided.
- **Never measured in 5 years:** lipid panel, urine albumin/creatinine ratio (only total-protein UPCR from 07/2022 on), B12 (relevant after years of metformin). Also, **no statin appears in any medication list.**
- **Present but not described in your request:** the cardiology clearance note, a partial *draft* hospital discharge summary, and transplant evaluation labs. All three were used.

---

## 8. Data quality: unusual or probably inaccurate data

**Highest clinical impact**

1. **Another person's data is in the transplant file.** A living-donor evaluation (ID T-0241, DOB 03/22/1991: creatinine 0.88, K 3.9, BP 118/72, BMI 24.1) is attached to this patient's transplant labs. **It was completely excluded.** It should be removed from this patient's chart.
2. **Endocrinology 05/14/2024 says HbA1c 8.5% is "Below transplant program threshold of 8.0%."** 8.5% is **above** 8.0%. If this wording is copied forward, it could cause a listing error.
3. **Vitals entry 07/14/2023 probably belongs to someone else:** 165 lb (37–40 lb lighter than every nearby entry), BP 122/78, glucose 91, SpO2 99%. There is no matching visit note, and 07/14 is the patient's birthday, so a DOB may have been entered as the visit date. Shown as 🟡 and excluded from interpretation.
4. **Vitals entry 08/12/2023 is dated while the patient was in the hospital** (admitted 08/10, discharged 08/14/2023). Either the date or the source is wrong. Shown as 🟡.
5. **Several potassium values are questionable or conflicting:**
   - 01/10/2023: 5.6, flagged possible hemolysis; PM recheck 5.1.
   - 08/10/2023: outpatient 6.4, suspected hemolysis; admission 6.1.
   - 01/30/2024: 5.9, prolonged tourniquet time.
   - **01/25/2024: pharmacy says 5.9, PCP chart says 5.7** for the same draw.
   - **06/15/2022: "K 3.9" is only in the nephrology note (patient recollection)**; the lab file has no potassium for that date.
6. **CKD stage labels don't match the eGFR values.** "Stage 3b" was used at eGFR 58 (03/04/2022) and 49 (07/28/2022); both are G3a. "Stage 4" has been used since 08/2023 (hospital discharge diagnosis, then nephrology from 10/10/2023) at eGFR 31–37; those are all G3b. No eGFR below 30 is recorded anywhere. Please confirm the stage used for transplant and dialysis documentation.
7. **Medication record conflicts** (no single reconciled list exists):
   - Endocrinology documents **insulin glargine and aspart, but the pharmacy record has no insulin fills.**
   - Cardiology's 01/30/2024 list includes **epoetin and furosemide 40 mg**, but those were first dispensed on **04/19/2024 and 03/16/2024**.
   - Endocrinology on 02/22/2023 lists "repaglinide 2 mg TID … at max," but 2 mg was first dispensed 05/20/2023 as 60 tablets per 30 days (twice daily). The labeled maximum is 16 mg/day, not 6.
   - **Sevelamer:** 270 units per 30 days does not match the documented 800 mg TID, and "1600 mg" is not a standard single-tablet strength. The 08/14/2023 dose increase cites "Phos 5.6," but no phosphorus of 5.6 existed until 10/10/2023, and on 08/14 the patient was being discharged with sevelamer on hold.
   - The 10/10/2023 calcitriol increase has no matching fill. Ferrous sulfate was filled once. Metoclopramide (05/30/2023) has no fill; if he is taking it, it needs a renal dose reduction.
   - **The hospital discharge medication list (page 2) is missing**, so it is unclear which held medications were restarted.

**Units, dates and flags**

8. **Glucose units are mixed in `lab_results.csv`.** Four values are mmol/L with no units. Two different ranges were used: 3.9–6.1 mmol/L (≈70–110 mg/dL) and 70–100 mg/dL. As a result, 03/04/2022 (5.9 mmol/L ≈ 106 mg/dL) was flagged NORMAL.
9. **Flow-sheet glucose conflicts with lab results.** 03/04/2022: 147 vs lab ≈106. The 147 is identical to the next visit's value, which suggests it was copied forward. 11/02/2023: 168 vs lab ≈133.
10. **Date formats are inconsistent.** The archive uses DD/MM/YYYY (for example, "03/02/2022" = 3 Feb 2022). `lab_results.csv` uses MM/DD for results but DD/MM for the DOB. The CSV row "04/03/2022" matches the 04/04/2022 visit note exactly, so it is charted as 04/03/2022, the same visit.
11. **Archive flags are wrong.** eGFR 64 (09/2020) and 62 (02/2021) are flagged LOW although both are ≥60. eGFR 60 (02/2022) is flagged LOW. eGFR units are written "ml/min" instead of mL/min/1.73m².
12. **Hemoglobin 06/15/2022 (11.8) has a specimen-delay warning**, and an earlier note cites 12.2. The nephrology note says "PCP had 11.8 on 9/22," but no CBC was drawn on 09/22/2022.

**Source reliability and lower-impact items**

13. The **hospital discharge summary is an unfinalized draft** with page 2 missing; full note via HIM at ext. 4400. Its values were used but should be checked against the final record. The 04/04/2022 **draft** PCP note (illegible BP) was replaced by the amended note, and the amended values were used.
14. The **vitals log was transcribed from paper in 06/2024.** The ambiguous characters were resolved using matching physician notes: "I52" = 152 and "8O" = 80 are confirmed; "I49" = 149 is consistent with the note.
15. Minor items:
    - Endocrinology says HbA1c differences were due to "fasting status," but HbA1c does not depend on fasting.
    - Endocrinology's 05/30/2023 BP (160/99) is identical to the 05/18/2023 flow-sheet BP, which may be a copy-forward.
    - Cardiology's note cites "eGFR ~31–34," but 31 was not measured until 04/17/2024.
    - The PCP header says "Age: 65 at most recent note," but he was 64 on 01/10/2023.

---

## 9. Summary

### Immediate risks (highest first)

1. **Hyperkalemia:** latest 6.0, ≥5.6 since 10/2023, on maximum-dose ACE inhibitor, with a prior admission and a missed hold. Risk of dangerous heart rhythms.
2. **Severe uncontrolled hypertension** (169/103; 184/112 episode) with heart damage already present (LVH, EF 60 → 52%, BNP 186). It blocks transplant listing, and the new ESA may raise BP further.
3. **Rapidly progressive CKD:** eGFR 31, falling about 12.7 per year; UPCR 620. Nausea and poor appetite may be uremic symptoms. Kidney failure planning is time-sensitive.
4. **Worsening metabolic acidosis** (CO2 16), which also raises potassium.
5. **Anemia** (Hgb 9.4) with **no iron workup or GI evaluation documented**, on a newly started ESA.
6. **CKD mineral-bone disease:** phosphorus 6.1, PTH 276 (about 4x the upper limit), vitamin D deficiency not treated.
7. **Malnutrition risk:** albumin 2.8, 13 lb weight loss.
8. **Diabetes above the transplant threshold** (8.5%), and HbA1c is not fully reliable here.
9. **Medication safety:** five prescribers with no reconciled list; no insulin fills on record; a metoclopramide prescription alongside borderline QTc and CKD.

### Comprehensive treatment plan (all recommendations above, by urgency)

**Within days**
- Repeat K on a non-hemolyzed sample, with an ECG if ≥6.0.
- Start a potassium binder and low-K diet. Reduce lisinopril if K stays >5.5 despite the binder, and give clear hold instructions.
- Repeat the BMP after changes.
- Confirm which medications he is actually taking: insulin, ESA start date, furosemide dose, sevelamer dose.

**Within 2–4 weeks**
- **Blood pressure:** intensify treatment (diuretic optimization; beta-blocker, chlorthalidone or hydralazine as prescriber chooses), with home BP monitoring.
- **Bicarbonate:** titrate toward ≥22.
- **SGLT2 inhibitor:** start, if no contraindication.
- **Anemia:** iron studies, B12, folate and reticulocyte count. GI evaluation if iron deficient. IV iron as indicated. Monthly Hgb on ESA, target ≤11.5.
- **Vitamin D:** replete 25-OH vitamin D.
- **Dietitian:** renal dietitian referral covering K, phosphorus, sodium, protein and calories.

**Ongoing**
- **Diabetes:** CGM; keep titrating insulin to <8.0%; reconsider GLP-1 RA once appetite and weight are stable.
- **Phosphorus and PTH:** binder optimization; calcitriol adjusted with corrected calcium.
- **Proteinuria:** check UACR every 3–6 months; finerenone once K ≤5.0.
- **Nutrition:** monitor albumin and dry weight.

### Recommended changes to the care plan

1. **One reconciled medication list** shared by PCP, nephrology, endocrinology, cardiology and pharmacy, updated at every visit.
2. **Monitoring schedule:**
   - BMP (with K, CO2, corrected Ca, phosphorus) monthly until K and CO2 are stable, then every 3 months.
   - Hgb monthly on ESA.
   - HbA1c every 3 months, together with CGM data.
   - UACR, PTH and 25-OH vitamin D every 3–6 months.
   - **Add a lipid panel and consider a statin.** KDIGO and ADA recommend one for a patient his age with diabetes and CKD, and none is on record.
3. **Lab practice:** potassium drawn in a way that avoids hemolysis, with same-day repeat of hemolyzed results. One glucose unit (mg/dL) and ISO dates (YYYY-MM-DD) in the lab archive. Flags recalculated against a stated reference range.
4. **Transplant readiness checklist**, tracked explicitly:
   - HbA1c <8.0%.
   - BP <140/90.
   - Age-appropriate cancer screening, including colonoscopy.
   - Hepatitis B surface antibody status and vaccination.
   - Dental clearance.
   - Cardiology follow-up.
5. **Kidney replacement therapy planning:** dialysis option education, vascular access status, and advance care planning, now that eGFR is near 30.
6. **Retrieve missing records and correct the chart:**
   - Iron studies, hematology notes and any thyroid labs.
   - Hospital discharge page 2 (HIM ext. 4400).
   - The 2019 echo report.
   - Remove the donor data (Section 8.1).
   - Correct the endocrinology threshold statement (Section 8.2).
