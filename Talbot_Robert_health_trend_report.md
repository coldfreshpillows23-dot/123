# Longitudinal Health Marker Trend Report

| | |
|---|---|
| **Patient** | Robert J. Talbot — Male — DOB 07/14/1958 |
| **Age over record** | 60 (Feb 2019) to 65 (May 2024) — reference ranges below are for an **adult male aged 60–65** |
| **MRNs** | PCP 004-882-19 · Hospital WR-004882 · Nephrology NEP-2022-0447 · Endo END-1194 · Cardiology CAR-5582 · Transplant TRANS-2023-0819 |
| **Actual data range** | **02/14/2019 → 05/14/2024 (≈5 years 3 months)**. Dense data from 03/2022 on. 2019–2021 values are semi-annual archive results only. |
| **Sources** | 10 files (listed below). Every plotted value is traceable to a source code in the table under each chart. |

> **Please read first: differences between the records received and the request**
> - **No thyroid data exist in any file.** The file named `endocrine_and_thyroid_notes.txt` covers diabetes only. There are no TSH, free T4, or T3 results, so **no thyroid chart can be produced** (see §13).
> - **No iron studies** (ferritin, iron, TIBC, TSAT) and **no hematology visit notes** were in the upload. Iron studies were ordered on 06/15/2022, but no results appear anywhere (see §13).
> - No primary care *annual summaries* were found. PCP progress notes cover only 03/2022–01/2023. There was also no standalone medication reconciliation. I used the pharmacy dispensing record instead, and the hospital med-rec page is missing.
> - Three files you did not mention **were** included and used: cardiology clearance (01/2024), transplant evaluation labs (12/2023), and an **unfinalized, truncated** hospital discharge draft (08/2023).
> - **Values for a different person (living-donor T-0241, DOB 1991) are attached to the transplant file. They were excluded entirely.**
>
> If any hematology, thyroid, or later PCP records exist, please upload them and I will add them.

## How to read the charts

- **Colour (GitHub):** each chart sits in a `diff` block. **Rows outside the reference range start with `-` and render red. Rows inside the range start with `+` and render green.** Points and connecting lines therefore appear red wherever the value is out of range.
- **Plain text editor (no colour):** the same `-` / `+` in column 1 marks out-of-range / in-range rows. Points are drawn as **`X` = outside reference range**, **`o` = within range**, and **`?` = questionable value**. A `?` value is present in the source but flagged, for example suspected hemolysis or a suspected wrong-patient row. It is plotted, but it is **excluded from trend interpretation** and is not connected by lines.
- A dashed `ULN`/`LLN` row marks the upper/lower reference limit.
- **Gaps:** the x-axis lists every date on which *any* marker in that chart was measured (oldest at left). A `~` on the `no data ->` row means the marker was **not measured on that date**. Lines are **not** drawn across gaps.
- The x-axis is **by encounter, not to time scale** (e.g., 2019–2021 draws are ~6 months apart, 2023 draws only weeks apart). Rows are rounded to the nearest gridline, and **exact values are in the table under each chart** (`H`/`L` = high/low).
- **Panel grouping:** multi-analyte blood tests are grouped into shared-axis charts rather than one chart per value. The **CBC is one chart (§9)**. CMP components are grouped by clinical question: renal (§1), electrolytes/acid–base (§3), and albumin (§5), with glucose in the glycemic section (§7). CMP liver/protein results exist for only one date and appear in §14.
- **Treatment recommendations are written for the treating provider to consider. They are not orders.** Each one is triggered per the report rules (≥2 out-of-range values in a chart).

| Code | Source file |
|---|---|
| ARC | `old_baseline_labs_2019_2020.txt (PCP lab archive)` |
| LAB | `lab_results.csv (Westfield Regional lab)` |
| NEPH | `nephrology_clinic_notes.txt (in-house draws)` |
| HOSP | `hospital_discharge_partial.txt (UNFINALIZED DRAFT)` |
| TX | `transplant_eval_bloodwork.txt` |
| CARD | `cardiology_clearance_note.txt` |
| ENDO | `endocrine_and_thyroid_notes.txt` |
| VIT | `vitals_and_weights_log.txt (nursing log)` |
| PCP | `physician_notes_redacted.txt` |
| RX | `pharmacy_med_record.csv (dispensing record; medication context only, no values plotted)` |


## At-a-glance: most urgent findings (details in the Summary)
1. **Potassium 6.0 mEq/L on 04/17/2024** on lisinopril 40 mg (last dispensed 02/10/2024). He was hospitalized for K⁺ 6.1 in 08/2023, and **the 04/17/2024 nephrology plan does not address potassium.**
2. **Uncontrolled stage 2 hypertension.** Readings have risen to 166–172/100–106 in 2024, with LVH and LVEF down from 60% to 52%. Cardiology's listing condition (<140/90) is unmet.
3. **Progressive CKD (eGFR 70 → 31).** This comes with worsening metabolic acidosis (CO₂ 16), hyperphosphatemia (6.1), rising PTH (276), and falling albumin (2.8).
4. **Anemia (Hgb 14.8 → 9.4).** An ESA was started 04/19/2024 with **no iron studies documented anywhere**.
5. **HbA1c 8.5–8.7%**, above the transplant program's 8.0% threshold. The 05/14/2024 endocrine note wrongly calls 8.5% "below" it.

---
# Part A — Kidney function and chemistry

## 1. Kidney function — CMP renal markers (Creatinine, eGFR, BUN)

```diff
  Creatinine (mg/dL)
-         2.10 |
-         2.00 |                                                X.                  .X
-         1.90 |                                               .  .X.         .X..X.
-         1.80 |                                              .      .X..X..X.
-         1.70 |                                            .X
-         1.60 |                                      .X..X.
-         1.50 |                             .X..X..X.
-         1.40 |                       .X..X.
      ULN 1.35 :- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
+         1.30 |           .o..o..o..o.
+         1.20 |  .o..o..o.
+         1.10 |o.
    no data -> |

  eGFR (mL/min/1.73m2)
+           70 |o..o.
+           65 |     .o..o.
+           60 |           .o.   .o.
        LLN 60 :- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
-           55 |              .X.   .X..X.
-           50 |                          .X..X..X.
-           45 |                                   .X..X.
-           40 |                                         .X..X
-           35 |                                              ..  .X..X..X..X     X.
-           30 |                                                X.                  .X
    no data -> |                                                               ~

  BUN (mg/dL)
-           50 |                                                X
-           45 |                                               . ..
-           40 |                                              .    X       .X     X
-           35 |                                             X           X.
-           30 |                                .X
-           25 |                     X..X..X..X.
        ULN 20 :- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
+           20 |
+           15 |o
+           10 |
    no data -> |   ~  ~  ~  ~  ~  ~                 ~  ~  ~           ~        ~     ~

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  02 09 03 09 02 08 02 03 04 06 07 09 11 01 04 05 08 08 10 11 12 01 03 04
          year  19 19 20 20 21 21 22 22 22 22 22 22 22 23 23 23 23 23 23 23 23 24 24 24
```

| # | Date | Creatinine (mg/dL) | eGFR (mL/min/1.73m²) | BUN (mg/dL) | Source(s) | Notes |
|---|---|---|---|---|---|---|
| 1 | 02/14/2019 | 1.12 | 70 | 14 | ARC |  |
| 2 | 09/22/2019 | 1.16 | 68 | — *(gap)* | ARC |  |
| 3 | 03/10/2020 | 1.19 | 66 | — *(gap)* | ARC |  |
| 4 | 09/18/2020 | 1.22 | 64 | — *(gap)* | ARC | archive flagged LOW despite >60 |
| 5 | 02/28/2021 | 1.25 | 62 | — *(gap)* | ARC |  |
| 6 | 08/11/2021 | 1.29 | 59 **L** | — *(gap)* | ARC |  |
| 7 | 02/03/2022 | 1.31 | 60 | — *(gap)* | ARC |  |
| 8 | 03/04/2022 | 1.34 | 58 **L** | 22 **H** | LAB |  |
| 9 | 04/03/2022 | 1.39 **H** | 55 **L** | 24 **H** | LAB |  |
| 10 | 06/15/2022 | 1.44 **H** | 51 **L** | 26 **H** | LAB |  |
| 11 | 07/28/2022 | 1.47 **H** | 49 **L** | 27 **H** | NEPH |  |
| 12 | 09/22/2022 | 1.51 **H** | 48 **L** | 28 **H** | LAB |  |
| 13 | 11/03/2022 | 1.54 **H** | 45 **L** | — *(gap)* | NEPH |  |
| 14 | 01/10/2023 | 1.58 **H** | 44 **L** | — *(gap)* | LAB |  |
| 15 | 04/04/2023 | 1.65 **H** | 41 **L** | — *(gap)* | NEPH |  |
| 16 | 05/18/2023 | 1.71 **H** | 39 **L** | 34 **H** | LAB |  |
| 17 | 08/10/2023 | 2.04 **H** | 32 **L** | 48 **H** | HOSP | admission, AKI; during AKI - not for staging |
| 18 | 08/14/2023 | 1.89 **H** | 35 **L** | 40 **H** | HOSP | discharge |
| 19 | 10/10/2023 | 1.82 **H** | 37 **L** | — *(gap)* | NEPH |  |
| 20 | 11/02/2023 | 1.79 **H** | 36 **L** | 36 **H** | LAB |  |
| 21 | 12/14/2023 | 1.84 **H** | 34 **L** | 38 **H** | TX |  |
| 22 | 01/30/2024 | 1.93 **H** | — *(gap)* | — *(gap)* | CARD |  |
| 23 | 03/14/2024 | 1.89 **H** | 33 **L** | 40 **H** | LAB |  |
| 24 | 04/17/2024 | 1.95 **H** | 31 **L** | — *(gap)* | NEPH |  |


**Reference ranges (male, 60–65 y):** Creatinine 0.74–1.35 mg/dL. eGFR ≥60 mL/min/1.73m² (the average for healthy men aged 60–69 is ≈85, and <60 defines CKD G3). BUN 7–20 mg/dL per Westfield lab; the transplant lab uses 8–25, and many labs allow up to ~23 mg/dL over age 60. **KDIGO stages:** G3a 45–59, G3b 30–44, G4 15–29, G5 <15.

**Clinical observation — DECLINING (progressive).** Creatinine rose 1.12 → 1.95 mg/dL and eGFR fell 70 → 31, which moves the patient from G2 to **late G3b, bordering G4**.
- Decline was ~3–4 mL/min/yr from 2019 to early 2022, then **~13 mL/min/yr from 03/2022 to 04/2024** (58 → 31). This is well above KDIGO's ">5 mL/min/yr" rapid-progression threshold.
- BUN rose 14 → 40 mg/dL.
- There was an **AKI episode on 08/10/2023** (Cr 2.04, BUN 48). It recovered only to a new, higher baseline.
- eGFR has been out of range since 08/2021 and creatinine since 04/2022.
- ⚠ From 2023 onward, the reported eGFR values are **3–6 points lower** than race-free CKD-EPI 2021 gives for the same creatinine. For example, Cr 1.95 at age 65 gives ≈37.5, not 31 (see Data Integrity). Reported values are plotted unchanged.

**Treatment recommendations (multiple out-of-range values):**
1. **Confirm true GFR with cystatin C (eGFRcr-cys)** and ask the lab which equation it reports. Accuracy matters here because staging, drug dosing, and transplant/dialysis timing all depend on it. Falling albumin and weight also suggest muscle loss, which distorts creatinine-based estimates.
2. **Start an SGLT2 inhibitor** if there is no contraindication (KDIGO 2022/2024, 1A: T2D + CKD with eGFR ≥20). It slows CKD progression and reduces proteinuria and heart-failure risk. Watch volume status (he is on furosemide) and hold it on sick days. Its glucose-lowering effect is modest at this eGFR.
3. Keep RAS blockade **only with active potassium management** (§3). Review all drugs for renal dosing and avoid NSAIDs and other nephrotoxins.
4. **Kidney-failure readiness:** AV-access planning was referred on 04/04/2023, but no placement is documented. Confirm its status. Continue transplant work-up, and note that many programs start preemptive listing credit at eGFR ≤20.

## 2. Urine protein — Urine protein-to-creatinine ratio (UPCR)

```diff
  UPCR (mg/g)
-          650 |
-          600 |                X
-          550 |             ...
-          500 |            X
-          450 |         ...
-          400 |       .X
-          350 |  ..X..
-          300 |X.
-          250 |
-          200 |
-          150 |
      ULN <150 :- - - - - - - - -
+          100 |
    no data -> |

               ++---+---+---+---+
         month  07  11  04  10  04
          year  22  22  23  23  24
```

| # | Date | UPCR (mg/g) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 07/28/2022 | 280 **H** | NEPH |  |
| 2 | 11/03/2022 | 340 **H** | NEPH |  |
| 3 | 04/04/2023 | 420 **H** | NEPH |  |
| 4 | 10/10/2023 | 510 **H** | NEPH |  |
| 5 | 04/17/2024 | 620 **H** | NEPH |  |


**Reference range:** UPCR <150 mg/g (KDIGO A1). 150–500 is A2 and >500 is A3. Not age/sex dependent.

**Clinical observation — DECLINING (worsening proteinuria).** UPCR more than doubled, 280 → 620 mg/g. It reached **A3 (>500 mg/g) from 10/2023** despite maximum-dose lisinopril. This is not nephrotic range. Nephrology drew it only 5 times, and no urine albumin-to-creatinine ratio (UACR) was found.

**Treatment recommendations (multiple out-of-range values):**
1. Add an **SGLT2 inhibitor** (§1), which reduces proteinuria on top of ACE inhibition.
2. Control **blood pressure to target** (§9). Uncontrolled BP is the most modifiable driver here.
3. Consider a **GLP-1 receptor agonist** (semaglutide showed kidney-outcome benefit in the FLOW trial), balanced against his nausea and poor appetite (§6). **Finerenone is not appropriate while K⁺ is >5.0.**
4. Order a **UACR**, which KDIGO prefers for staging and for the Kidney Failure Risk Equation.

## 3. Electrolytes & acid–base — CMP (Potassium, Sodium, CO₂/bicarbonate)

```diff
  Potassium (mEq/L)
-          6.2 |
-          6.0 |                                 X              ?    .X
-          5.8 |                                  .    X..X..X     X.
-          5.6 |                 .X  ?     X          .
-          5.4 |               X.         .        . .
-          5.2 |         X    .          .          X
       ULN 5.1 :- - - - - - - - - - - - - - - - - - - - - - - - - - - -
+          5.0 |        . .. .          o
+          4.8 |            o
+          4.6 |       .
+          4.4 |      o
+          4.2 |    ..
+          4.0 |o..o
+          3.8 |
    no data -> |                              ~

  Sodium (mEq/L)
-          146 |
       ULN 145 :- - - - - - - - - - - - - - - - - - - - - - - - - - - -
+          144 |
+          142 |
+          140 |   o
+          138 |         o..o                                o
+          136 |
       LLN 136 :- - - - - - - - - - - - - - - - - - - - - - - - - - - -
-          134 |
    no data -> |~     ~        ~  ~  ~  ~  ~  ~  ~  ~  ~  ~     ~  ~  ~

  CO2 / bicarbonate (mEq/L)
-           30 |
        ULN 29 :- - - - - - - - - - - - - - - - - - - - - - - - - - - -
+           28 |
+           26 |
+           24 |
+           22 |            o
        LLN 22 :- - - - - - - - - - - - - - - - - - - - - - - - - - - -
-           20 |                  X..X     X..X     X.
-           18 |                               .. ..  .X..X..X     X.
-           16 |                                 X                   .X
-           14 |
    no data -> |~  ~  ~  ~     ~        ~                       ~

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  02 03 08 04 07 09 11 01 01 04 05 08 08 10 11 12 01 03 04
          year  19 20 21 22 22 22 22 23 23 23 23 23 23 23 23 23 24 24 24
```

| # | Date | Potassium (mEq/L) | Sodium (mEq/L) | CO2 / bicarbonate (mEq/L) | Source(s) | Notes |
|---|---|---|---|---|---|---|
| 1 | 02/14/2019 | 4.1 | — *(gap)* | — *(gap)* | ARC |  |
| 2 | 03/10/2020 | 4.0 | 139 | — *(gap)* | ARC |  |
| 3 | 08/11/2021 | 4.4 | — *(gap)* | — *(gap)* | ARC |  |
| 4 | 04/03/2022 | 5.2 **H** | 138 | — *(gap)* | LAB |  |
| 5 | 07/28/2022 | 4.8 | 137 | 22 | NEPH |  |
| 6 | 09/22/2022 | 5.4 **H** | — *(gap)* | — *(gap)* | LAB |  |
| 7 | 11/03/2022 | 5.5 **H** | — *(gap)* | 21 **L** | NEPH |  |
| 8 | 01/10/2023 | 5.6 ? | — *(gap)* | 20 **L** | LAB | lab: possible hemolyzed specimen |
| 9 | 01/10/2023 (PM) | 5.1 | — *(gap)* | — *(gap)* | PCP | same-day PM point-of-care recheck |
| 10 | 04/04/2023 | 5.5 **H** | — *(gap)* | 20 **L** | NEPH |  |
| 11 | 05/18/2023 | — *(gap)* | — *(gap)* | 19 **L** | LAB |  |
| 12 | 08/10/2023 | 6.1 **H** | — *(gap)* | 15 **L** | HOSP | admission (outpatient 6.4 same episode, ?hemolysis) |
| 13 | 08/14/2023 | 5.2 **H** | — *(gap)* | 19 **L** | HOSP | discharge |
| 14 | 10/10/2023 | 5.8 **H** | — *(gap)* | 18 **L** | NEPH |  |
| 15 | 11/02/2023 | 5.7 **H** | — *(gap)* | 18 **L** | LAB |  |
| 16 | 12/14/2023 | 5.7 **H** | 138 | 17 **L** | TX |  |
| 17 | 01/30/2024 | 5.9 ? | — *(gap)* | — *(gap)* | CARD | cardiology: possible hemolysis, prolonged tourniquet |
| 18 | 03/14/2024 | 5.8 **H** | — *(gap)* | 17 **L** | LAB |  |
| 19 | 04/17/2024 | 6.0 **H** | — *(gap)* | 16 **L** | NEPH |  |


**Reference ranges (male, 60–65 y):** Potassium 3.5–5.1 mEq/L (Westfield; transplant lab 3.5–5.5). Sodium 136–145 mEq/L. CO₂ 22–29 mEq/L (transplant lab 23–29). Chloride 98–107 mEq/L (one value, 102; see §14).

**Clinical observation — POTASSIUM DECLINING (worsening hyperkalemia); SODIUM STABLE/NORMAL; CO₂ DECLINING (worsening metabolic acidosis).**
- **Potassium:** 4.0–4.4 through 2021, then **persistently high since 04/2022** (5.2 → **6.0 on 04/17/2024**). The peak was 6.1 at the 08/2023 admission.
  - Excluding the two hemolysis-suspect values (`?`), 11 of the 13 valid readings since 04/2022 are high. The two normal ones are 4.8 (07/2022) and the 5.1 same-day recheck.
  - Two further potassium values (5.9 vs 5.7 for 01/25/2024) appear only as conflicting second-hand notes in the pharmacy record and are **not plotted**.
  - The patient **kept taking lisinopril during a pharmacy potassium hold**.
- **Sodium:** 137–139, normal throughout. Sparse (4 values), but no concern.
- **CO₂:** fell steadily, 22 → **16 mEq/L**, despite sodium bicarbonate since 01/2023 and a dose increase in 11/2023.

**Treatment recommendations (multiple out-of-range values):**
1. **Urgent: repeat K⁺ now** on a non-hemolysed sample (plasma, minimal tourniquet, no fist clenching). Get an **ECG** if K⁺ is ≥6.0, and manage acutely per protocol. The last value (6.0) has no documented response.
2. **Start a potassium binder** (patiromer or sodium zirconium cyclosilicate) so the ACE inhibitor can continue. KDIGO 2024 favours K⁺-lowering measures over stopping RAS blockade. If K⁺ stays ≥6.0 despite this, reduce the lisinopril dose.
3. **Intensify alkali therapy.** Titrate sodium bicarbonate toward serum bicarbonate ≥22 (KDIGO 2012). KDIGO 2024 suggests at least considering treatment when bicarbonate is <18. Correcting acidosis also lowers K⁺ and slows bone and muscle loss. Account for the **sodium load** given his BP and edema.
4. Refer to a **renal dietitian** for a low-potassium diet (also needed for phosphorus and protein). Screen for salt substitutes (KCl), NSAIDs, and other K⁺-raising agents.
5. **Teach the patient** about potassium safety and medication holds, since he took lisinopril during the hold.

## 4. CKD–Mineral & Bone Disorder (Phosphorus, PTH, Calcium)

```diff
  Phosphorus (mg/dL)
-          6.2 |
-          6.0 |                       .X..X
-          5.8 |                    .X.
-          5.6 |               X..X.
-          5.4 |             ..
-          5.2 |        .X..X
-          5.0 |   X..X.
-          4.8 |  .
-          4.6 |
       ULN 4.5 :- - - - - - - - - - - - - -
+          4.4 | .
+          4.2 |o
+          4.0 |
    no data -> |

  PTH, intact (pg/mL)
-          300 |
-          275 |                           X
-          250 |
-          225 |                    .X
-          200 |                  X.
-          175 |
-          150 |
-          125 |            X
-          100 |      X
-           75 |X
        ULN 65 :- - - - - - - - - - - - - -
+           50 |
    no data -> |   ~     ~     ~        ~

  Calcium (mg/dL)
-         11.0 |
      ULN 10.5 :- - - - - - - - - - - - - -
+         10.5 |
+         10.0 |
+          9.5 |
+          9.0 |o                    o
+          8.5 |
       LLN 8.5 :- - - - - - - - - - - - - -
-          8.0 |
    no data -> |   ~  ~  ~  ~  ~  ~     ~  ~

               ++--+--+--+--+--+--+--+--+--+
         month  07 09 11 01 04 05 10 12 03 04
          year  22 22 22 23 23 23 23 23 24 24
```

| # | Date | Phosphorus (mg/dL) | PTH, intact (pg/mL) | Calcium (mg/dL) | Source(s) | Notes |
|---|---|---|---|---|---|---|
| 1 | 07/28/2022 | 4.2 | 68 **H** | 9.1 | NEPH |  |
| 2 | 09/22/2022 | 4.9 **H** | — *(gap)* | — *(gap)* | LAB |  |
| 3 | 11/03/2022 | 5.0 **H** | 92 **H** | — *(gap)* | NEPH |  |
| 4 | 01/10/2023 | 5.2 **H** | — *(gap)* | — *(gap)* | LAB |  |
| 5 | 04/04/2023 | 5.3 **H** | 124 **H** | — *(gap)* | NEPH |  |
| 6 | 05/18/2023 | 5.5 **H** | — *(gap)* | — *(gap)* | LAB |  |
| 7 | 10/10/2023 | 5.6 **H** | 198 **H** | — *(gap)* | NEPH |  |
| 8 | 12/14/2023 | 5.8 **H** | 221 **H** | 9.2 | TX |  |
| 9 | 03/14/2024 | 5.9 **H** | — *(gap)* | — *(gap)* | LAB |  |
| 10 | 04/17/2024 | 6.1 **H** | 276 **H** | — *(gap)* | NEPH |  |


**Reference ranges (adult male):** Phosphorus 2.5–4.5 mg/dL. Intact PTH 10–65 pg/mL. Calcium 8.5–10.5 mg/dL. 25-OH vitamin D 30–100 ng/mL (one value, **18 L**; see §14).

**Clinical observation — DECLINING (progressive secondary hyperparathyroidism and hyperphosphatemia).**
- **Phosphorus** rose 4.2 → **6.1 mg/dL** with almost no interruption. It has been high since 09/2022 despite sevelamer (started 09/2022, increased 08/2023).
- **PTH** quadrupled, 68 → **276 pg/mL (≈4× ULN)**, despite calcitriol since 04/2023.
- **Calcium** was normal on the only two draws (9.1, 9.2), so it is poorly monitored.
- **Vitamin D was deficient (18 ng/mL)** on 12/2023, with no documented repletion.

**Treatment recommendations (multiple out-of-range values):**
1. **Verify the sevelamer regimen and adherence.** Pharmacy quantities don't match the prescribed sig, and "1600 mg" is not a standard tablet strength (see Data Integrity). Confirm it is taken **with meals**, and add renal dietitian phosphate counselling (processed-food additives).
2. **Replete 25-OH vitamin D** with nutritional vitamin D (cholecalciferol/ergocalciferol). KDIGO 2017 advises correcting modifiable factors, including vitamin D deficiency and high phosphate intake, when PTH rises in non-dialysis CKD.
3. **Reassess calcitriol.** KDIGO 2017 advises against routine calcitriol in G3a–G5 non-dialysis CKD, reserving it for severe, progressive hyperparathyroidism. Calcitriol also raises gut phosphate absorption and may be contributing to the phosphorus rise.
4. Monitor **calcium, phosphorus, and alkaline phosphatase every 1–3 months and PTH every 3–6 months**, and **correct acidosis** (§3).

## 5. Serum albumin (CMP protein marker)

```diff
  Albumin (g/dL)
+          3.9 |
+          3.8 |
+          3.7 |o..
+          3.6 |   .o.
+          3.5 |      ..o.
       LLN 3.5 :- - - - - - - - - - - - - - - - - - -
-          3.4 |          .
-          3.3 |           .X..
-          3.2 |               .X
-          3.1 |                 ...  ..X.
-          3.0 |                    X.    .
-          2.9 |                           .X...X..
-          2.8 |                                   .X
-          2.7 |
    no data -> |

               ++---+---+---+---+---+---+---+---+---+
         month  07  09  11  01  04  10  11  12  03  04
          year  22  22  22  23  23  23  23  23  24  24
```

| # | Date | Albumin (g/dL) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 07/28/2022 | 3.7 | NEPH |  |
| 2 | 09/22/2022 | 3.6 | LAB |  |
| 3 | 11/03/2022 | 3.5 | NEPH |  |
| 4 | 01/10/2023 | 3.3 **L** | LAB |  |
| 5 | 04/04/2023 | 3.2 **L** | NEPH |  |
| 6 | 10/10/2023 | 3.0 **L** | NEPH |  |
| 7 | 11/02/2023 | 3.1 **L** | LAB |  |
| 8 | 12/14/2023 | 2.9 **L** | TX |  |
| 9 | 03/14/2024 | 2.9 **L** | LAB |  |
| 10 | 04/17/2024 | 2.8 **L** | NEPH |  |


**Reference range (adult male 60–65 y):** 3.5–5.0 g/dL. Levels fall slightly with age, but <3.5 is abnormal at any adult age. Total protein was 6.1 g/dL (low-normal) in 12/2023 (§14).

**Clinical observation — DECLINING.** Albumin fell 3.7 → **2.8 g/dL** and has been below range since 01/2023. This coincides with **decreased appetite and nausea** (endo/PCP notes), **~13 lb weight loss** (§11), and rising proteinuria. Proteinuria (620 mg/g) is far from nephrotic range, so the drop more likely reflects **protein-energy wasting and inflammation with worsening acidosis and uremia**. Low albumin is also a strong mortality marker in CKD and matters for transplant candidacy.

**Treatment recommendations (multiple out-of-range values):**
1. Get a **formal nutrition assessment** from a renal dietitian (Subjective Global Assessment). Aim for protein ~0.8 g/kg/day (KDIGO 2024 G3–G5 non-dialysis), and **avoid over-restriction in a patient who is losing weight**.
2. **Correct metabolic acidosis** (§3), which drives protein breakdown.
3. Assess whether the **anorexia, nausea, and the 08/2023 confusion are uremic symptoms**. These can be an indication to plan kidney replacement therapy sooner.
4. **Review metoclopramide:** renally dose-adjust it and monitor for extrapyramidal effects.
---
# Part B — Glycemic control

## 6. Hemoglobin A1c

```diff
  HbA1c (%)
-          8.8 |
-          8.6 |                                         .X..X..X..X..X
-          8.4 |                                   .X..X.
-          8.2 |                              X..X.
-          8.0 |                            ..
-          7.8 |                           X
-          7.6 |                         ..
-          7.4 |                       .X
-          7.2 |                    .X.
-          7.0 |              .X..X.
-          6.8 |           .X.
-          6.6 |        .X.
-          6.4 |     .X.
-          6.2 |  .X.
-          6.0 |X.
-          5.8 |
      ULN <5.7 :- - - - - - - - - - - - - - - - - - - - - - - - - - - -
+          5.6 |
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  02 09 03 09 02 08 02 03 04 09 01 02 05 05 09 12 01 03 05
          year  19 19 20 20 21 21 22 22 22 22 23 23 23 23 23 23 24 24 24
```

| # | Date | HbA1c (%) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 02/14/2019 | 5.9 **H** | ARC |  |
| 2 | 09/22/2019 | 6.2 **H** | ARC |  |
| 3 | 03/10/2020 | 6.4 **H** | ARC |  |
| 4 | 09/18/2020 | 6.6 **H** | ARC |  |
| 5 | 02/28/2021 | 6.8 **H** | ARC |  |
| 6 | 08/11/2021 | 7.0 **H** | ARC |  |
| 7 | 02/03/2022 | 7.1 **H** | ARC |  |
| 8 | 03/04/2022 | 7.2 **H** | LAB |  |
| 9 | 04/03/2022 | 7.4 **H** | LAB | 30 days after prior A1c |
| 10 | 09/22/2022 | 7.8 **H** | LAB |  |
| 11 | 01/10/2023 | 8.1 **H** | LAB |  |
| 12 | 02/22/2023 | 8.2 **H** | ENDO | point-of-care |
| 13 | 05/18/2023 | 8.3 **H** | LAB |  |
| 14 | 05/30/2023 | 8.4 **H** | ENDO |  |
| 15 | 09/06/2023 | 8.6 **H** | ENDO |  |
| 16 | 12/14/2023 | 8.5 **H** | TX |  |
| 17 | 01/18/2024 | 8.7 **H** | ENDO |  |
| 18 | 03/14/2024 | 8.6 **H** | LAB |  |
| 19 | 05/14/2024 | 8.5 **H** | ENDO | ~3.5 wk after ESA start; may read falsely low |


**Reference range:** Normal <5.7%. 5.7–6.4% is prediabetes and ≥6.5% is diabetes, regardless of age or sex. **Patient-specific targets:** ADA general goal <7.0%. A less strict goal of <8.0% is acceptable for an older adult with CKD and comorbidities. **The transplant program requires <8.0% for listing.**

**Clinical observation — DECLINING (worsening glycemic control).**
- HbA1c rose steadily, 5.9% (2019) → **8.7% (01/2024)**, then 8.5% (05/2024).
- It reached 7.0% in 08/2021 and **has been above the 8.0% transplant threshold since 01/2023**, despite repaglinide, then glargine (02/2023), then prandial aspart (09/2023).
- The 05/14/2024 "slight improvement" came **~3.5 weeks after the ESA was started**. ESA therapy, anemia, and advanced CKD all make HbA1c **read falsely low**, so true control may be worse.
- ⚠ The endocrine note of 05/14/2024 states 8.5% is "below" the 8.0% threshold. **That is incorrect: it is above.**

**Treatment recommendations (multiple out-of-range values):**
1. **Start continuous glucose monitoring (CGM)**, which was discussed 01/2024 but has no documented start. Use the glucose management indicator (GMI) / time-in-range, because HbA1c is unreliable with CKD, anemia, and ESA therapy (KDIGO 2022 Diabetes-in-CKD).
2. Add an **SGLT2 inhibitor** for kidney and heart protection (§1). If targets remain unmet, consider a **long-acting GLP-1 RA** (KDIGO 2022), started low and titrated slowly given nausea and poor appetite.
3. **Reconcile glucose-lowering drugs.** It is unclear whether repaglinide continues alongside prandial aspart. Two prandial agents plus falling GFR means **high hypoglycemia risk**, since insulin clearance drops as GFR declines.
4. **Confirm the diabetes-education referral** (09/2023) was completed, and coordinate endocrinology with the transplant team, as the endocrine note proposes.

## 7. Blood glucose — laboratory (serum/plasma)

```diff
  Glucose, lab (mg/dL)
-          210 |
-          200 |                                    X
-          190 |                                   . ..
-          180 |                                       X     X.
-          170 |                                  .            .X
-          160 |                             .X..X      .   .
-          150 |                     X..X..X.            . .
-          140 |            X..X    .
-          130 |          ..    .                         X
-          120 |  .X..X..X       . .
-          110 |X.                X
-          100 |
        ULN 99 :- - - - - - - - - - - - - - - - - - - - - - - - -
+           90 |
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  02 09 03 02 08 02 03 04 06 09 01 05 08 08 11 12 03
          year  19 19 20 21 21 22 22 22 22 22 23 23 23 23 23 23 24
```

| # | Date | Glucose, lab (mg/dL) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 02/14/2019 | 108 **H** | ARC |  |
| 2 | 09/22/2019 | 115 **H** | ARC |  |
| 3 | 03/10/2020 | 118 **H** | ARC |  |
| 4 | 02/28/2021 | 124 **H** | ARC |  |
| 5 | 08/11/2021 | 138 **H** | ARC |  |
| 6 | 02/03/2022 | 143 **H** | ARC |  |
| 7 | 03/04/2022 | 106 **H** | LAB | reported 5.9 mmol/L; lab flagged NORMAL vs 3.9-6.1 mmol/L |
| 8 | 04/03/2022 | 147 **H** | LAB |  |
| 9 | 06/15/2022 | 150 **H** | LAB | reported 8.3 mmol/L |
| 10 | 09/22/2022 | 152 **H** | LAB |  |
| 11 | 01/10/2023 | 164 **H** | LAB | reported 9.1 mmol/L |
| 12 | 05/18/2023 | 162 **H** | LAB |  |
| 13 | 08/10/2023 | 203 **H** | HOSP |  |
| 14 | 08/14/2023 | 179 **H** | HOSP |  |
| 15 | 11/02/2023 | 133 **H** | LAB | reported 7.4 mmol/L |
| 16 | 12/14/2023 | 178 **H** | TX |  |
| 17 | 03/14/2024 | 168 **H** | LAB |  |


**Unit handling:** four lab results were reported **without units, in mmol/L** (03/04/2022, 06/15/2022, 01/10/2023, 11/02/2023). This was done per the lab's own footnote. They were converted at ×18.016 to plot on one axis, and the **original value is shown in Notes**. No other values were altered.

**Reference range (adult, fasting):** 70–99 mg/dL (3.9–5.5 mmol/L). 100–125 is impaired fasting glucose and ≥126 is diabetic range. **Fasting status is not documented for most lab draws**, so some values may be non-fasting.

**Clinical observation — DECLINING (rising glucose).** Lab glucose climbed from 108 (2019) to the 160s–170s in 2023–2024, with a peak of 203 at the 08/2023 admission. Every value is above range. This matches the HbA1c trend.
- 03/04/2022 (5.9 mmol/L ≈ 106 mg/dL) was flagged **NORMAL** by the lab against its mmol/L range, yet it is above the same lab's 70–100 mg/dL range.
- 11/02/2023 (≈133) is unusually low compared with its neighbours.

**Treatment recommendations (multiple out-of-range values):** Follow the HbA1c plan in §6 (CGM, SGLT2i/GLP-1 RA, regimen reconciliation). In addition, **ask the lab to report all glucose in mg/dL with units** and to **record fasting status** on requisitions.

## 8. Blood glucose — clinic point-of-care (nursing log + endocrinology visits)

```diff
  Glucose, POC (mg/dL)
-          180 |                                    X     X.
-          170 |                  X.             ?     ?    .X..X
-          160 |           .X    .  .X..X..X
-          150 |?  X..X..X.  .. .
-          140 |               X
-          130 |
-          120 |
-          110 |
-          100 |
        ULN 99 :- - - - - - - - - - - - - - - - - - - - - - - - -
+           90 |                              ?
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  03 04 06 09 01 01 02 03 05 05 07 08 09 11 01 03 05
          year  22 22 22 22 23 23 23 23 23 23 23 23 23 23 24 24 24
```

| # | Date | Glucose, POC (mg/dL) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 03/04/2022 | 147 ? | VIT | lab same day 5.9 mmol/L (~106); identical to 04/04 value |
| 2 | 04/04/2022 | 147 **H** | VIT |  |
| 3 | 06/15/2022 | 149 **H** | VIT | logged "I49"; PCP note confirms 149 |
| 4 | 09/22/2022 | 152 **H** | VIT |  |
| 5 | 01/10/2023 | 162 **H** | VIT |  |
| 6 | 01/10/2023 (PM) | 138 **H** | VIT | PM recheck |
| 7 | 02/22/2023 | 171 **H** | ENDO |  |
| 8 | 03/15/2023 | 158 **H** | VIT |  |
| 9 | 05/18/2023 | 162 **H** | VIT |  |
| 10 | 05/30/2023 | 158 **H** | ENDO |  |
| 11 | 07/14/2023 | 91 ? | VIT | suspected wrong-patient row |
| 12 | 08/12/2023 | 171 ? | VIT | patient was inpatient 8/10-8/14 |
| 13 | 09/06/2023 | 176 **H** | ENDO |  |
| 14 | 11/02/2023 | 168 ? | VIT | lab same day 7.4 mmol/L (~133) |
| 15 | 01/25/2024 | 175 **H** | VIT |  |
| 16 | 03/14/2024 | 168 **H** | VIT |  |
| 17 | 05/09/2024 | 174 **H** | VIT |  |


**Reference range:** as in §7 (fasting 70–99 mg/dL). Endocrinology targets pre-meal glucose of 80–130 mg/dL (the glargine titration rule is "FBG >130").

**Clinical observation — DECLINING (rising glucose).** Valid clinic values rose from 147–152 (2022) to mostly **158–176 (2023–2024)**, plus one PM recheck of 138. None are in range. Endocrinology also notes that the home log shows "frequent 180–220, several >250" after the hospitalization (no dates or values given, so not plotted).
- The 07/14/2023 value (91) is from a suspected wrong-patient row.
- The 08/12/2023 value was logged while the patient was an inpatient.
- The 03/04/2022 and 11/02/2023 values conflict with same-day lab results. All four are marked `?`.
- On most other dates the "POC" value **exactly equals the lab value**, so this column may be **copied from lab results rather than measured independently**.

**Treatment recommendations (multiple out-of-range values):** Same plan as §6. Also **clarify what the nursing-log glucose column represents** (fingerstick vs. transcribed lab value) so the two data streams aren't double-counted.

---
# Part C — Hematology

## 9. Complete Blood Count (CBC) — Hemoglobin, Hematocrit, WBC, Platelets

```diff
  Hemoglobin (g/dL)
+         15.0 |o
+         14.5 | ..
+         14.0 |   o..o
+         13.5 |       .
      LLN 13.5 :- - - - - - - - - - - - - - - - - - - - - - - - -
-         13.0 |        .
-         12.5 |         X
-         12.0 |            ?  X
-         11.5 |                ..
-         11.0 |                  X..X.
-         10.5 |                       .X..X.
-         10.0 |                             .X..X..X..X.
-          9.5 |                                         .X..X..X
-          9.0 |
    no data -> |

  Hematocrit (%)
+         44.0 |
+         42.0 |
        LLN 41 :- - - - - - - - - - - - - - - - - - - - - - - - -
-         40.0 |
-         38.0 |
-         36.0 |            X
-         34.0 |
-         32.0 |
-         30.0 |                                       X
-         28.0 |
    no data -> |~  ~  ~  ~     ~  ~  ~  ~  ~  ~  ~  ~     ~  ~  ~

  WBC (K/uL)
-         12.0 |
      ULN 11.0 :- - - - - - - - - - - - - - - - - - - - - - - - -
+         10.0 |
+          8.0 |      o     o                          o
+          6.0 |
       LLN 4.5 :- - - - - - - - - - - - - - - - - - - - - - - - -
-          4.0 |
    no data -> |~  ~     ~     ~  ~  ~  ~  ~  ~  ~  ~     ~  ~  ~

  Platelets (K/uL)
+          260 |
+          240 |
+          220 |            o
+          200 |                                       o
+          180 |
+          160 |
       LLN 150 :- - - - - - - - - - - - - - - - - - - - - - - - -
-          140 |
    no data -> |~  ~  ~  ~     ~  ~  ~  ~  ~  ~  ~  ~     ~  ~  ~

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  02 03 02 02 06 07 11 01 04 05 08 10 11 12 01 03 04
          year  19 20 21 22 22 22 22 23 23 23 23 23 23 23 24 24 24
```

| # | Date | Hemoglobin (g/dL) | Hematocrit (%) | WBC (K/µL) | Platelets (K/µL) | Source(s) | Notes |
|---|---|---|---|---|---|---|---|
| 1 | 02/14/2019 | 14.8 | — *(gap)* | — *(gap)* | — *(gap)* | ARC |  |
| 2 | 03/10/2020 | 14.2 | — *(gap)* | — *(gap)* | — *(gap)* | ARC |  |
| 3 | 02/28/2021 | 14.0 | — *(gap)* | 7.1 | — *(gap)* | ARC |  |
| 4 | 02/03/2022 | 12.4 **L** | — *(gap)* | — *(gap)* | — *(gap)* | ARC |  |
| 5 | 06/15/2022 | 11.8 ? | 35.4 **L** | 7.2 | 212 | LAB | PCP: "please verify"; processing delay; another note cites 12.2 |
| 6 | 07/28/2022 | 12.0 **L** | — *(gap)* | — *(gap)* | — *(gap)* | NEPH |  |
| 7 | 11/03/2022 | 11.2 **L** | — *(gap)* | — *(gap)* | — *(gap)* | NEPH |  |
| 8 | 01/10/2023 | 10.9 **L** | — *(gap)* | — *(gap)* | — *(gap)* | LAB |  |
| 9 | 04/04/2023 | 10.7 **L** | — *(gap)* | — *(gap)* | — *(gap)* | NEPH |  |
| 10 | 05/18/2023 | 10.4 **L** | — *(gap)* | — *(gap)* | — *(gap)* | LAB |  |
| 11 | 08/10/2023 | 9.9 **L** | — *(gap)* | — *(gap)* | — *(gap)* | HOSP |  |
| 12 | 10/10/2023 | 10.0 **L** | — *(gap)* | — *(gap)* | — *(gap)* | NEPH |  |
| 13 | 11/02/2023 | 10.1 **L** | — *(gap)* | — *(gap)* | — *(gap)* | LAB |  |
| 14 | 12/14/2023 | 9.9 **L** | 30.1 **L** | 7.8 | 198 | TX |  |
| 15 | 01/30/2024 | 9.5 **L** | — *(gap)* | — *(gap)* | — *(gap)* | CARD |  |
| 16 | 03/14/2024 | 9.7 **L** | — *(gap)* | — *(gap)* | — *(gap)* | LAB |  |
| 17 | 04/17/2024 | 9.4 **L** | — *(gap)* | — *(gap)* | — *(gap)* | NEPH | ESA started 04/19/2024 |


**Reference ranges (adult male, 60–65 y):** Hemoglobin 13.5–17.5 g/dL (WHO defines anemia in men as <13.0). Hematocrit 41–53%. WBC 4.5–11.0 K/µL. Platelets 150–400 K/µL. RBC 4.5–5.9 M/µL and MCV 80–100 fL are single values (§14). **KDIGO ESA guidance:** do not intentionally raise Hgb above 11.5 g/dL.

**Clinical observation — HEMOGLOBIN DECLINING; WBC/PLATELETS STABLE/NORMAL.**
- Hemoglobin fell **14.8 → 9.4 g/dL** over 5 years. The first low value was 12.4 on 02/2022, and it has fallen ~1.3 g/dL per year since. Hematocrit fell 35.4 → 30.1%.
- WBC (7.1–7.8) and platelets (198–212) are normal, so this is an **isolated anemia**. The only indices (12/2023) are **normocytic** (MCV 91), which fits anemia of CKD. A normal MCV does **not** exclude iron deficiency in CKD.
- Oral iron started 06/2022, and **epoetin alfa started 04/19/2024**.
- **No ferritin, TSAT, iron/TIBC, reticulocyte, B12 or folate results exist in the records.** The 06/15/2022 value (11.8) is marked `?` because the PCP asked for it to be verified.

**Treatment recommendations (multiple out-of-range values):**
1. **Obtain iron studies now**: ferritin, TSAT, plus reticulocyte count, B12, and folate. KDIGO 2012 anemia guidance is to assess and correct iron status **before/with ESA**: give iron if TSAT ≤30% and ferritin ≤500 ng/mL. **IV iron** may be preferable given nausea and the uncertain response to oral iron.
2. If **iron deficiency is confirmed in a 65-year-old man, evaluate for GI blood loss** (colonoscopy/EGD as indicated, and confirm colorectal-cancer screening status).
3. **ESA safety:** check Hgb every 2–4 weeks during initiation and **target ≤11.5 g/dL**. ESA can **worsen hypertension**, which is already uncontrolled (§10), so monitor BP closely.
4. **Retrieve the hematology consult notes** (referral 06/15/2022); none were received.

---
# Part D — Vital signs

## 10. Blood pressure (systolic / diastolic)

```diff
  Systolic BP (mmHg)
-          185 |                              X
-          180 |
-          175 |
-          170 |                                         .X.   .X..X
-          165 |                                 ?     X.   .X.
-          160 |X        X.         .X..X             .
-          155 | ..    ..  .X.   .X.                 .
-          150 |   X..X       .X.                   X
-          145 |
-          140 |
-          135 |
-          130 |
-          125 |
-          120 |                           ?
   normal <120 :- - - - - - - - - - - - - - - - - - - - - - - - - -
+          115 |
    no data -> |

  Diastolic BP (mmHg)
-          115 |
-          110 |                              X
-          105 |                                         .X.   .X..X
-          100 |         X.         .X..X        ?    .X.   .X.
-           95 |X..X.  ..  .X..X..X.                X.
-           90 |     .X
-           85 |
-           80 |
    normal <80 :- - - - - - - - - - - - - - - - - - - - - - - - - -
+           75 |                           ?
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  03 04 06 09 01 01 03 05 05 07 08 08 08 11 01 01 03 05
          year  22 22 22 22 23 23 23 23 23 23 23 23 23 23 24 24 24 24
```

| # | Date | Systolic BP (mmHg) | Diastolic BP (mmHg) | Source(s) | Notes |
|---|---|---|---|---|---|
| 1 | 03/04/2022 | 158 **H** | 96 **H** | VIT |  |
| 2 | 04/04/2022 | 152 **H** | 94 **H** | VIT | BP logged "I52/94"; PCP amended note confirms 152/94 |
| 3 | 06/15/2022 | 148 **H** | 92 **H** | VIT |  |
| 4 | 09/22/2022 | 162 **H** | 98 **H** | VIT | HR logged "8O"; PCP note confirms 80 |
| 5 | 01/10/2023 | 154 **H** | 96 **H** | VIT |  |
| 6 | 01/10/2023 (PM) | 151 **H** | 94 **H** | VIT | PM recheck |
| 7 | 03/15/2023 | 156 **H** | 97 **H** | VIT |  |
| 8 | 05/18/2023 | 160 **H** | 99 **H** | VIT |  |
| 9 | 05/30/2023 | 160 **H** | 99 **H** | ENDO | identical to 05/18 reading |
| 10 | 07/14/2023 | 122 ? | 78 ? | VIT | suspected wrong-patient row |
| 11 | 08/10/2023 | 184 **H** | 112 **H** | HOSP | ED, hypertensive urgency |
| 12 | 08/12/2023 | 164 ? | 102 ? | VIT | patient was inpatient 8/10-8/14 |
| 13 | 08/14/2023 | 148 **H** | 94 **H** | HOSP | discharge |
| 14 | 11/02/2023 | 166 **H** | 101 **H** | VIT |  |
| 15 | 01/25/2024 | 168 **H** | 104 **H** | VIT |  |
| 16 | 01/30/2024 | 166 **H** | 100 **H** | CARD | R arm; L arm 164/98 |
| 17 | 03/14/2024 | 172 **H** | 106 **H** | VIT |  |
| 18 | 05/09/2024 | 169 **H** | 103 **H** | VIT |  |


**Reference range (adults, all ages):** Normal <120/<80 mmHg (ACC/AHA 2017). 120–129/<80 is elevated, 130–139/80–89 is stage 1, and ≥140/≥90 is stage 2. **Patient-specific targets:** **<140/90 is a cardiology condition for transplant listing.** KDIGO 2021 recommends SBP <120 if tolerated, and ADA recommends <130/80.

**Clinical observation — DECLINING (worsening hypertension).**
- Every valid reading is **stage 2**. BP rose from 148–162/92–98 (2022) to **166–172/100–106 (2024)**.
- There was **hypertensive urgency at 184/112 (08/10/2023)**.
- This is **resistant hypertension**: above goal on lisinopril 40 mg + amlodipine 10 mg + furosemide.
- End-organ effects are already present: **LVH, LVEF 60% → 52%, grade 1 diastolic dysfunction, BNP 186**, and rising proteinuria.
- The 07/14/2023 reading (122/78) is from a suspected wrong-patient row, and 08/12/2023 was logged during hospitalization (both `?`). The 05/30/2023 endocrine reading is identical to 05/18/2023 (possible copy-forward).

**Treatment recommendations (multiple out-of-range values):**
1. **Confirm with home BP monitoring or 24-h ambulatory BP, and assess adherence.** The dispensing record shows amlodipine filled only once (03/2022), and it may be incomplete.
2. **Optimize volume:** consider twice-daily or higher-dose loop diuretic for eGFR ~30 with edema, and dietary sodium <2 g/day. Note the sodium load from bicarbonate.
3. Add a fourth agent. **Chlorthalidone** works even in advanced CKD (CLICK trial) and **also lowers K⁺**; monitor Na⁺, K⁺, creatinine, and glucose. Alternatively, or in addition, consider a **beta-blocker** (e.g., carvedilol) given LVH and mildly reduced EF. **Avoid spironolactone/MRAs while K⁺ ≥5.5.**
4. Re-check BP 2–4 weeks after each change, and **watch for an ESA-related BP rise**.

## 11. Weight (and BMI context)

```diff
  Weight (lb)
-          220 |
-          215 |        .X
-          210 |X..X..X.  ..
-          205 |            X..X..X.          ?  X.
-          200 |                    .X..X          .X..X..X..X..X..X
-          195 |
-          190 |
-          185 |
-          180 |
        BMI 25 :- - - - - - - - - - - - - - - - - - - - - - - - - -
+          175 |
+          170 |
+          165 |                           ?
+          160 |
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  03 04 06 09 01 01 03 05 05 07 08 11 01 01 01 03 05 05
          year  22 22 22 22 23 23 23 23 23 23 23 23 24 24 24 24 24 24
```

| # | Date | Weight (lb) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 03/04/2022 | 212 **H** | VIT |  |
| 2 | 04/04/2022 | 209 **H** | VIT | BP logged "I52/94"; PCP amended note confirms 152/94 |
| 3 | 06/15/2022 | 208 **H** | VIT |  |
| 4 | 09/22/2022 | 215 **H** | VIT | HR logged "8O"; PCP note confirms 80 |
| 5 | 01/10/2023 | 206 **H** | VIT |  |
| 6 | 01/10/2023 (PM) | 206 **H** | VIT | PM recheck |
| 7 | 03/15/2023 | 204 **H** | VIT |  |
| 8 | 05/18/2023 | 202 **H** | VIT |  |
| 9 | 05/30/2023 | 202 **H** | ENDO |  |
| 10 | 07/14/2023 | 165 ? | VIT | suspected wrong-patient row |
| 11 | 08/12/2023 | 205 ? | VIT | patient was inpatient 8/10-8/14 |
| 12 | 11/02/2023 | 203 **H** | VIT |  |
| 13 | 01/18/2024 | 200 **H** | ENDO |  |
| 14 | 01/25/2024 | 201 **H** | VIT |  |
| 15 | 01/30/2024 | 201 **H** | CARD | BMI 28.0 documented |
| 16 | 03/14/2024 | 200 **H** | VIT |  |
| 17 | 05/09/2024 | 199 **H** | VIT |  |
| 18 | 05/14/2024 | 199 **H** | ENDO |  |


**Reference range:** Height is documented as 5'11" (PCP 03/2022, cardiology 01/2024). A normal BMI of 18.5–24.9 at that height is **≈133–179 lb**, which is the boundary used for row colour. BMI is documented once (28.0 on 01/30/2024). Where other BMIs are mentioned here, they are arithmetic from the recorded weight and height, not new data.

**Clinical observation — DECLINING (unintentional weight loss), still overweight.** Weight fell from **212–215 lb (2022, BMI ~30) to 199 lb (05/2024, BMI ~27.8)**, about a 6–7% loss. It is accompanied by poor appetite, nausea, and falling albumin (§5).
- The 09/2022 peak (215 lb) coincided with new leg edema, so **fluid shifts confound this trend**.
- The 07/14/2023 value (165 lb, i.e. −37 lb in 8 weeks and then +40 lb in 4 weeks) is physiologically implausible and is marked `?`.

**Treatment recommendations (multiple out-of-range values):** **Do not pursue intentional weight loss.** Despite BMI >25, the pattern points to possible protein-energy wasting. Instead: renal dietitian assessment (§5), weigh at each visit with an edema assessment to separate fluid from tissue change, and treat drivers of anorexia (acidosis, uremia, nausea).

## 12. Heart rate, oxygen saturation, temperature

```diff
  Heart rate (bpm)
+          100 |
+           95 |
+           90 |                                      .o.
+           85 |           .o.      .o     ?  o..o..o.   .o
+           80 |o..o.   .o.   .o..o.
+           75 |     .o.
+           70 |                        ?
+           65 |
+           60 |
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  03 04 06 09 01 01 03 05 07 08 11 01 01 03 05
          year  22 22 22 22 23 23 23 23 23 23 23 24 24 24 24
```

| # | Date | Heart rate (bpm) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 03/04/2022 | 78 | VIT |  |
| 2 | 04/04/2022 | 82 | VIT | BP logged "I52/94"; PCP amended note confirms 152/94 |
| 3 | 06/15/2022 | 76 | VIT |  |
| 4 | 09/22/2022 | 80 | VIT | HR logged "8O"; PCP note confirms 80 |
| 5 | 01/10/2023 | 84 | VIT |  |
| 6 | 01/10/2023 (PM) | 81 | VIT | PM recheck |
| 7 | 03/15/2023 | 79 | VIT |  |
| 8 | 05/18/2023 | 83 | VIT |  |
| 9 | 07/14/2023 | 70 ? | VIT | suspected wrong-patient row |
| 10 | 08/12/2023 | 86 ? | VIT | patient was inpatient 8/10-8/14 |
| 11 | 11/02/2023 | 85 | VIT |  |
| 12 | 01/25/2024 | 87 | VIT |  |
| 13 | 01/30/2024 | 84 | CARD |  |
| 14 | 03/14/2024 | 88 | VIT |  |
| 15 | 05/09/2024 | 86 | VIT |  |

**Reference range:** 60–100 bpm (adult). **Observation — STABLE, within range, mild upward drift.** Heart rate rose from 76–82 (2022) to 84–88 (2024). The drift may reflect anemia or deconditioning. All values are normal, so no treatment recommendation is triggered. The `8O` on 09/22/2022 was read as 80, confirmed by the PCP note.

```diff
  SpO2 (%)
+          100 |
+           99 |                        ?
+           98 |     .o
+           97 |o..o.  ..  .o..o..o.
+           96 |         o.         .o
+           95 |                           ?  o..o..o.   .o
        LLN 95 :- - - - - - - - - - - - - - - - - - - - - -
-           94 |                                      .X.
-           93 |
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  03 04 06 09 01 01 03 05 07 08 11 01 01 03 05
          year  22 22 22 22 23 23 23 23 23 23 23 24 24 24 24
```

| # | Date | SpO2 (%) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 03/04/2022 | 97 | VIT |  |
| 2 | 04/04/2022 | 97 | VIT | BP logged "I52/94"; PCP amended note confirms 152/94 |
| 3 | 06/15/2022 | 98 | VIT |  |
| 4 | 09/22/2022 | 96 | VIT | HR logged "8O"; PCP note confirms 80 |
| 5 | 01/10/2023 | 97 | VIT |  |
| 6 | 01/10/2023 (PM) | 97 | VIT | PM recheck |
| 7 | 03/15/2023 | 97 | VIT |  |
| 8 | 05/18/2023 | 96 | VIT |  |
| 9 | 07/14/2023 | 99 ? | VIT | suspected wrong-patient row |
| 10 | 08/12/2023 | 95 ? | VIT | patient was inpatient 8/10-8/14 |
| 11 | 11/02/2023 | 95 | VIT |  |
| 12 | 01/25/2024 | 95 | VIT |  |
| 13 | 01/30/2024 | 95 | CARD |  |
| 14 | 03/14/2024 | 94 **L** | VIT |  |
| 15 | 05/09/2024 | 95 | VIT |  |

**Reference range:** 95–100% on room air (adult). **Observation — mild DECLINE.** SpO₂ fell from 96–98% (2022) to **94–95% (2024)**. Only **one** value is below range (94% on 03/14/2024), so no formal recommendation is triggered. Given exertional dyspnea, BNP 186, edema, and EF 52%, a **volume-status assessment** at the next visit is worthwhile.

```diff
  Temperature (F)
+         99.0 |
+         98.8 |
+         98.6 |                        ?
+         98.4 |      o
+         98.2 |o.  .. ..         o..o              o.
+         98.0 |  .o     o.      .         ?  o.  ..  .o
+         97.8 |           .o.  .               .o
+         97.6 |              .o
+         97.4 |
+         97.2 |
+         97.0 |
    no data -> |

               ++--+--+--+--+--+--+--+--+--+--+--+--+--+
         month  03 04 06 09 01 01 03 05 07 08 11 01 03 05
          year  22 22 22 22 23 23 23 23 23 23 23 24 24 24
```

| # | Date | Temperature (°F) | Source(s) | Notes |
|---|---|---|---|---|
| 1 | 03/04/2022 | 98.2 | VIT |  |
| 2 | 04/04/2022 | 97.9 | VIT | BP logged "I52/94"; PCP amended note confirms 152/94 |
| 3 | 06/15/2022 | 98.4 | VIT |  |
| 4 | 09/22/2022 | 98.1 | VIT | HR logged "8O"; PCP note confirms 80 |
| 5 | 01/10/2023 | 97.8 | VIT |  |
| 6 | 01/10/2023 (PM) | 97.6 | VIT | PM recheck |
| 7 | 03/15/2023 | 98.3 | VIT |  |
| 8 | 05/18/2023 | 98.2 | VIT |  |
| 9 | 07/14/2023 | 98.6 ? | VIT | suspected wrong-patient row |
| 10 | 08/12/2023 | 98.0 ? | VIT | patient was inpatient 8/10-8/14 |
| 11 | 11/02/2023 | 98.1 | VIT |  |
| 12 | 01/25/2024 | 97.7 | VIT |  |
| 13 | 03/14/2024 | 98.3 | VIT |  |
| 14 | 05/09/2024 | 98.1 | VIT |  |

**Reference range:** ≈97.0–99.0 °F oral (adults; older adults often run lower). **Observation — STABLE, all values normal** (valid readings 97.6–98.4 °F). No action needed.
---
# Part E — Markers requested but not available, and single-timepoint results

## 13. Markers with NO data in the uploaded records (no chart possible)

| Marker group | Status in records | Why it matters / suggested action |
|---|---|---|
| **Thyroid (TSH, free T4, T3)** | **Absent from all 10 files**, including `endocrine_and_thyroid_notes.txt` | If thyroid tests were done, please upload them. If not, consider a **TSH**: hypothyroidism can contribute to fatigue, anemia, and lipid abnormalities. |
| **Iron studies (ferritin, iron, TIBC, TSAT)** | Ordered 06/15/2022 (PCP); **no results anywhere**. No hematology notes. | Required to guide iron and ESA therapy (§9). **High priority.** |
| **Lipid panel** | **Absent**; **no statin on any medication list** | KDIGO (CKD, age ≥50) and ADA (T2D, age 40–75) both recommend statin therapy. Check lipids and **start a statin** (e.g., atorvastatin, which needs no renal adjustment) unless contraindicated. |
| **Urine albumin-to-creatinine ratio (UACR)** | Absent (only UPCR) | Preferred by KDIGO for staging and risk prediction (§2). |
| **Alkaline phosphatase, reticulocytes, B12, folate** | Absent | Needed for the CKD–mineral bone disorder (§4) and anemia (§9) work-ups. |

## 14. Single-timepoint results (a trend cannot be drawn from one value)

| Date | Test | Value | Reference (male, 60–65 y) | Status | Source |
|---|---|---|---|---|---|
| 12/14/2023 | Chloride | 102 mEq/L | 98–107 | Normal | TX |
| 12/14/2023 | Magnesium | 1.9 mg/dL | 1.7–2.2 | Normal | TX |
| 12/14/2023 | Total protein | 6.1 g/dL | 6.0–8.3 | Low-normal | TX |
| 12/14/2023 | Total bilirubin / ALT / AST | 0.6 mg/dL / 18 U/L / 22 U/L | 0.2–1.2 / 7–56 / 10–40 | Normal | TX |
| 12/14/2023 | RBC | 3.31 M/µL | 4.5–5.9 | **LOW** | TX |
| 12/14/2023 | MCV / MCHC | 91 fL / 32.8 g/dL | 80–100 / 32–36 | Normal (normocytic) | TX |
| 12/14/2023 | 25-OH Vitamin D | 18 ng/mL | 30–100 | **LOW (deficient)** | TX |
| 12/14/2023 | PRA / ABO / serologies | 4% / A+ / HIV, HBsAg, HCV neg; CMV & EBV IgG pos | — | Informational | TX |
| 01/30/2024 | BNP | 186 pg/mL | <100 | **HIGH** | CARD |
| 01/30/2024 | Troponin I / INR | <0.01 ng/mL / 1.0 | <0.04 / 0.8–1.2 | Normal | CARD |
| 01/30/2024 | Respiratory rate | 16 /min | 12–20 | Normal | CARD |
| 01/30/2024 | ECG QTc | 448 ms | ≤430 normal; 431–450 borderline (men) | Borderline | CARD |
| 01/30/2024 | LVEF (echo) | 52% (60% on an undated 2019 echo) | ≥55% | **Mildly reduced, declining** | CARD |
| 01/30/2024 | Nuclear stress test | No ischemia; 6.1 METs | — | Normal perfusion | CARD |

---
# Summary — Immediate risks, comprehensive plan, and data integrity

**Record span:** 02/14/2019 – 05/14/2024 (≈5 y 3 m). **Overall picture:** a 65-year-old man with T2DM and hypertension whose **diabetic kidney disease has progressed rapidly since 2022** (eGFR 58 → 31). All the expected CKD complications have accumulated together: hyperkalemia, metabolic acidosis, hyperphosphatemia with rising PTH, anemia, and hypoalbuminemia. Blood pressure and glycemic control are worsening at the same time. He is a renal-transplant candidate, but **both listing conditions (BP <140/90 and HbA1c <8.0%) are currently unmet.**

## Immediate risks (highest priority first)
1. **Hyperkalemia.** K⁺ 6.0 on 04/17/2024, high on 11 of 13 valid draws since 04/2022, and a prior admission for K⁺ 6.1. Lisinopril 40 mg was last dispensed 02/10/2024, and he took it during a pharmacy hold. **No management is documented for the latest value.** Risk: arrhythmia.
2. **Uncontrolled, resistant stage 2 hypertension** (169/103 on 05/09/2024) with prior hypertensive urgency and established LVH. LVEF has fallen 60 → 52% and BNP is raised. The **newly started ESA may raise BP further.**
3. **Rapid CKD progression toward G4/G5.** eGFR has fallen ~13 mL/min/yr, with CO₂ 16, phosphorus 6.1, PTH 276, and possible uremic symptoms (anorexia, nausea, confusion in 08/2023). **Dialysis access status is undocumented.**
4. **Anemia (Hgb 9.4) on a new ESA without documented iron studies.** Risks are ESA under-response, missed iron deficiency or GI blood loss, and ESA-related cardiovascular risk if Hgb overshoots.
5. **Malnutrition signals:** albumin 2.8 and −13 to −16 lb weight loss with poor appetite.
6. **Hypoglycemia/hyperglycemia risk.** HbA1c is 8.5–8.7% and may be understated by the ESA. Insulin is used alongside possible repaglinide while GFR falls.

## Consolidated treatment recommendations (from §§1–11; for provider review)
| # | Recommendation | Addresses | Priority |
|---|---|---|---|
| 1 | Repeat K⁺ on a non-hemolysed sample; ECG if ≥6.0; start a K⁺ binder (patiromer/SZC); reduce lisinopril only if K⁺ stays ≥6.0; low-K⁺ diet; patient education on holds | §3 | **Urgent** |
| 2 | Confirm BP out of office (home/ambulatory), check adherence, optimize loop diuretic, limit sodium to <2 g/day, add chlorthalidone (also lowers K⁺) and/or carvedilol. Targets: <140/90 for listing, SBP <120 per KDIGO if tolerated | §10 | **Urgent** |
| 3 | Start an SGLT2 inhibitor (eGFR ≥20) for kidney, heart, and proteinuria benefit | §1, §2, §6 | High |
| 4 | Iron studies, retics, B12, folate; iron repletion (consider IV) if TSAT ≤30% / ferritin ≤500; GI evaluation if iron-deficient; ESA target Hgb ≤11.5 with close BP monitoring | §9 | High |
| 5 | Titrate sodium bicarbonate toward bicarbonate ≥22 | §3, §5 | High |
| 6 | Confirm GFR with cystatin C (eGFRcr-cys); clarify the lab's eGFR equation | §1 | High |
| 7 | CGM with GMI/time-in-range; consider a GLP-1 RA (slow titration); reconcile repaglinide vs. aspart; confirm diabetes education | §6–8 | High |
| 8 | Replete vitamin D (cholecalciferol); reassess calcitriol; verify the sevelamer dose and meal timing; dietitian phosphate counselling; monitor Ca/Phos/ALP/PTH | §4 | Moderate |
| 9 | Renal dietitian nutrition assessment (protein ~0.8 g/kg/d, no over-restriction); **no intentional weight loss**; assess for uremic symptoms; renally dose metoclopramide | §5, §11 | Moderate |
| 10 | Lipid panel and statin | §13 | Moderate |
| 11 | Order UACR; consider TSH | §2, §13 | Routine |

## Suggested changes to the overall healthcare plan
- **Run one shared medication reconciliation** across PCP, endocrinology, nephrology, cardiology, and pharmacy. The lists conflict on the sevelamer dose, repaglinide dose and frequency, furosemide dose, epoetin start date, and bicarbonate dose. Insulin and metoclopramide are missing from the dispensing record.
- **Coordinate lab draws across specialties.** HbA1c and chemistries are duplicated within days or weeks (e.g., 05/18 and 05/30/2023; 12/14/2023, 01/18/2024, 01/30/2024, 03/14/2024). For an anemic patient, a shared monthly lab schedule would reduce blood loss and conflicting values.
- **Track a transplant-readiness checklist:** BP <140/90 (unmet), HbA1c <8.0% (unmet), cardiology follow-up, vitamin D repletion, nutrition status, tissue typing/crossmatch (pending), and dialysis access.
- **Set a hyperkalemia safety protocol:** a standing order for a repeat K⁺ within 24–72 h of any value ≥5.5, a clear hold/restart communication pathway between pharmacy and prescriber, and patient education.
- **Fix data quality:** standardize glucose to mg/dL with units, document fasting status, audit the nursing vitals log for misfiled rows, and obtain the **finalized hospital discharge summary** (HIM ext. 4400) and **hematology notes**.
- **Increase visit frequency.** Nephrology draws are ~6 months apart (10/2023 → 04/2024) while eGFR falls ~1 mL/min per month. KDIGO suggests monitoring at least every 3–4 months at this stage and risk level.

## Unusual or potentially inaccurate data (identified before finalizing this summary)
**High impact — affects interpretation or safety**
1. **Wrong-person data:** living-donor values (T-0241, DOB 03/22/1991: Cr 0.88, K 3.9, BP 118/72, BMI 24.1) are appended to the transplant file. **Excluded.**
2. **Nursing vitals 07/14/2023** (122/78, HR 70, **165 lb**, SpO₂ 99%, glucose 91) is inconsistent with every surrounding value; a 37-lb swing in weeks is implausible. The date is also the patient's birthday, possibly a registration mix-up. **Suspected wrong-patient row.** Plotted as `?`.
3. **Nursing vitals 08/12/2023** is dated while the patient was **hospitalized (08/10–08/14/2023)**. Plotted as `?`.
4. **Endocrine 05/14/2024** calls HbA1c 8.5% "below" the 8.0% transplant threshold. **It is above.**
5. **eGFR values from 2023 onward are lower than standard equations predict.** Race-free CKD-EPI 2021 gives Cr 1.95 at 65 y ≈37.5 (reported 31), Cr 1.89 ≈38.9 (reported 33), and Cr 1.84 ≈40.2 (reported 34). 2019–2022 values match CKD-EPI 2009 closely. The equation is undocumented. Reported values are plotted unchanged.
6. **CKD staging mislabelled** against the notes' own eGFRs: PCP 03/04/2022 "Stage 3b" at eGFR 58 (actually 3a); nephrology 10/10/2023 "Stage 4" at 37 (3b); hospital "CKD Stage 4" with discharge eGFR 35 (3b); cardiology "Stage 4 (eGFR ~31–34)" (3b).
7. **Potassium conflicts and hemolysis:** 01/10/2023 (5.6, possible hemolysis; same-day point-of-care recheck 5.1); 08/2023 outpatient 6.4 (hemolysis suspected, draw date unknown, not plotted); 01/30/2024 (5.9, prolonged tourniquet). The pharmacy record cites **5.9 vs 5.7 for 01/25/2024** with no source lab report (not plotted). A "recheck 5.6" has no draw date; it is noted only at the 02/10/2024 fill. Nephrology's "K 3.9 for 06/15/2022" is **patient-reported only**; no potassium was drawn that day.
8. **Mixed glucose units:** four glucose values in mmol/L have no units. 5.9 mmol/L (≈106 mg/dL) was flagged NORMAL against the mmol/L range even though it exceeds the same lab's mg/dL range. The nursing-log glucose differs from same-day lab on 03/04/2022 (147 vs ≈106) and 11/02/2023 (168 vs ≈133). Otherwise it mirrors lab values exactly, suggesting it may be transcribed rather than measured.

**Moderate — medication and record discrepancies**

9. **Sevelamer:** the PCP ordered 800 mg TID (3 tabs/day), but the 09/2022 dispensing was 270 tabs/30 days (9/day). The 08/2023 fill is "1600 mg" (not a standard tablet strength) ×270 and cites "**Phos 5.6**", a value not recorded until **10/10/2023**.
10. **Repaglinide:** on 02/22/2023 the endocrine note says "2 mg TID … at max". The pharmacy filled 1 mg until 05/20/2023, quantities imply BID, and the labelled maximum is 4 mg per meal (16 mg/day). The note also calls metformin "contraindicated" at eGFR 44; the FDA contraindication threshold is <30.
11. **Cardiology 01/30/2024 medication list** (patient-reported) includes epoetin and furosemide 40 mg, which were **first dispensed 04/19/2024 and 03/16/2024**.
12. **Timeline error:** the endocrine 09/06/2023 note says "3 weeks *prior to* hospital admission". The documented admission was 08/10/2023, *before* that visit. Either the date is wrong or a second admission is undocumented.
13. **Hemoglobin citations:** nephrology (11/03/2022) says "PCP had 11.8 on 9/22"; no Hgb was drawn on 09/22/2022 (11.8 was 06/15/2022). The 06/15/2022 value was itself flagged "please verify" (processing delay; another note cites 12.2). Plotted as `?`.
14. **Hospital discharge summary** is an unfinalized draft: page 2 (remaining labs, discharge medications) is missing and it is marked "should NOT be used as the final clinical record". Its values are plotted and labelled `HOSP`, but they need verification.

**Minor — transcription and formatting**

15. The vitals log has OCR-style character errors: `09:l5`, `I52/94`, `I49`, `8O`. These were resolved against PCP notes as 152/94, 149, and 80. Endocrine BP 160/99 on 05/30/2023 duplicates 05/18/2023 exactly.
16. Date formats are mixed: the archive uses DD/MM/YYYY, and the lab CSV uses DD/MM for DOB but MM/DD for results. The lab file dates one draw 04/03/2022 while the PCP note says labs were drawn 04/04/2022. HbA1c was repeated 3 times within ~2 months in early 2022, an interval too short to be informative.
17. The archive is titled "2019–2020", labelled "Period 2019–2021", and contains 02/2022 results. eGFR 64 is flagged LOW although the PCP lab's stated reference is >60 (the archive lists no range). The PCP header says "Age 65 at most recent note", but the patient was 64 on 01/10/2023.
18. The dispensing record appears incomplete: no insulin, metoclopramide, or calcitriol increase, and no amlodipine refills after 03/2022.

*All charted values come directly from the source files. The only transformations are the labelled mmol/L→mg/dL conversions and the BMI arithmetic noted in §11. Nothing was estimated or imputed. Gaps are shown as gaps.*
