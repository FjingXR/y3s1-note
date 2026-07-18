# 3. Return on Investment (ROI)

## ⚠️ Two Definitions — Know Both
The course shows **two** ROI formulas. The **exam/tutorial convention is the discounted version**, but the simple version also appears in the lecture.

### (A) Simple ROI — Lecture slide 32
    ROI = (Average Annual Profit / Total Investment) × 100%

Used in Lecture Chapter 1 examples:
| Project | Net Profit | Avg Annual Profit | Total Investment | ROI |
| --- | --- | --- | --- | --- |
| 1 | 50,000 | 10,000 | 100,000 | **10%** |
| 2 | 100,000 | 20,000 | 1,000,000 | **2%** |
| 3 | 50,000 | 10,000 | 100,000 | **10%** |
| 4 | 75,000 | 15,000 | 120,000 | **12.5%** |

> Disadvantage (per lecture): ignores the time value of money.

### (B) Discounted ROI — Tutorial exam convention (slide 43, Tutorial Q4 "Use discounted value")
    ROI = (NPV / Total Discounted Cost) × 100%

This is the version to use when the question gives a discount rate and asks for NPV **and** ROI together.

---

## Worked Example A — Lecture Project B @9% (slide 43)
Costs: Y0=100,000; Y1=60,000; Y2=60,000; Y3=50,000.
Benefits: Y1=80,000; Y2=90,000; Y3=180,000.
DF @9%: DF1=0.9174, DF2=0.8417, DF3=0.7722.

- Total Discounted Cost = 100,000 + 60,000(0.9174) + 60,000(0.8417) + 50,000(0.7722)
  = 100,000 + 55,044 + 50,502 + 38,610 = **244,156**
- Total Discounted Benefit = 80,000(0.9174) + 90,000(0.8417) + 180,000(0.7722)
  = 73,392 + 75,753 + 138,996 = **288,141**
- NPV = 288,141 − 244,156 = **43,985**
- **ROI** = (43,985 / 244,156) × 100% = **18.02%**

**Comment:** Positive NPV and ~18% ROI → project is worthwhile.

---

## Worked Example B — Tutorial 1, Question 3 (Project ABC @12%)
From NPV file: Discounted Cost = 50,000, NPV = 17,103.

    ROI = (17,103 / 50,000) × 100% = 34.21%

**Comment:** Strong positive ROI (34.21%) confirms the project is attractive.

## Worked Example C — Tutorial 1, Question 4 (Project X & Y @10%)
From NPV file:
- **Project X:** Discounted Cost = 201,050, NPV = −72,803
  → ROI = (−72,803 / 201,050) × 100% = **−36.21%** → reject.
- **Project Y:** Discounted Cost = 100,000, NPV = −100,000
  → ROI = (−100,000 / 100,000) × 100% = **−100%** → reject.

---

## How to Comment on ROI
| ROI | Meaning | Decision |
| --- | --- | --- |
| **ROI > 0** | Returns more than the discounted cost; profitable | Accept |
| **ROI ≤ 0** | Does not recover its discounted cost | Reject |

> Always pair the ROI comment with the NPV comment (they should agree). Higher positive ROI = more worthwhile.
