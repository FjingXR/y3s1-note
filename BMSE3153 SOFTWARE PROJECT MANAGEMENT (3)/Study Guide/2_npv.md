# 2. Net Present Value (NPV)

## Concept
NPV accounts for the **time value of money**: RM100 received today is worth more than RM100 received in 5 years. The **discount rate (r)** is treated as the organisation's **target rate of return**.

## Formula
Discount Factor for year t:

    DF_t = 1 / (1 + r)^t        where DF_0 = 1.0000

Discounted Cash Flow:

    DCF_t = CashFlow_t × DF_t

NPV (project appraisal layout, costs vs benefits):

    Discounted Cost   = Σ (Cost_t × DF_t)
    Discounted Benefit = Σ (Benefit_t × DF_t)
    NPV = Discounted Benefit − Discounted Cost

## How to Comment on the Result
| NPV | Meaning | Decision |
| --- | --- | --- |
| **NPV > 0** | PV of inflows > PV of outflows; project beats the target return | **Accept / attractive** |
| **NPV = 0** | Project just meets the target return | Marginal (usually accept) |
| **NPV < 0** | PV of costs > PV of benefits; does NOT achieve target return | **Reject** (net loss) |

> If the organisation sets a higher target return (e.g. 15%), it rejects any project with NPV ≤ 0.

## Rounding Rules (from tutorials)
- Discount factors → **4 decimal places**
- All other figures → **nearest integer**
- (ROI, when asked → 2 decimal places; see file 3)

---

## Worked Example A — Lecture Project 1 @10% (slide 38)
| Year | Cash Flow (RM) | DF @10% | Discounted CF |
| --- | --- | --- | --- |
| 0 | −100,000 | 1.0000 | −100,000 |
| 1 | 10,000 | 0.9091 | 9,091 |
| 2 | 10,000 | 0.8264 | 8,264 |
| 3 | 10,000 | 0.7513 | 7,513 |
| 4 | 20,000 | 0.6830 | 13,660 |
| 5 | 100,000 | 0.6209 | 62,090 |
| | | **NPV** | **618** |

**Comment:** NPV = +RM618 > 0 → the project is profitable and acceptable.

## Worked Example B — Lecture Project 3 @10% (slide 39)
| Year | Cash Flow (RM) | DF @10% | Discounted CF |
| --- | --- | --- | --- |
| 0 | −100,000 | 1.0000 | −100,000 |
| 1 | 30,000 | 0.9091 | 27,273 |
| 2 | 30,000 | 0.8264 | 24,792 |
| 3 | 30,000 | 0.7513 | 22,539 |
| 4 | 30,000 | 0.6830 | 20,490 |
| 5 | 30,000 | 0.6209 | 18,627 |
| | | **NPV** | **13,721** |

**Comment:** NPV = +RM13,721 > 0 → profitable. Project 3 is MORE beneficial than Project 1 (13,721 > 618) even though both have the same net profit, because Project 3 returns cash earlier.

## Worked Example C — Lecture Project 2 @10% (slide 41) — NEGATIVE case
| Year | Cash Flow (RM) | DF @10% | Discounted CF |
| --- | --- | --- | --- |
| 0 | −1,000,000 | 1.0000 | −1,000,000 |
| 1 | 200,000 | 0.9091 | 181,820 |
| 2 | 200,000 | 0.8264 | 165,280 |
| 3 | 200,000 | 0.7513 | 150,260 |
| 4 | 200,000 | 0.6830 | 136,600 |
| 5 | 300,000 | 0.6209 | 186,270 |
| | | **NPV** | **−179,770** |

**Comment:** NPV = −RM179,770 < 0 → NOT worth pursuing. PV of costs exceeds PV of benefits; it fails to achieve the 10% target return (a net loss).

---

## Worked Example D — Tutorial 1, Question 3 (Project ABC @12%)
Cash flow: Y0 = −50,000; Y1–Y3 = 20,000 each; Y4 = 30,000. Discount rate = 12%.

DF @12%: DF0=1.0000, DF1=0.8929, DF2=0.7972, DF3=0.7118, DF4=0.6355

| Year | Cash Flow (RM) | DF @12% | Discounted CF |
| --- | --- | --- | --- |
| 0 | −50,000 | 1.0000 | −50,000 |
| 1 | 20,000 | 0.8929 | 17,858 |
| 2 | 20,000 | 0.7972 | 15,944 |
| 3 | 20,000 | 0.7118 | 14,236 |
| 4 | 30,000 | 0.6355 | 19,065 |
| | | **NPV** | **17,103** |

**Comment:** NPV = +RM17,103 > 0 → the project is **attractive and should be accepted**; it earns more than the 12% target return.

---

## Worked Example E — Tutorial 1, Question 4 (Project X & Y @10%)
DF @10%: DF0=1.0000, DF1=0.9091, DF2=0.8264, DF3=0.7513

**Project X** — Costs: Y0=100,000; Y1=50,000; Y2=40,000; Y3=30,000. Benefits: Y1=70,000; Y2=60,000; Y3=20,000.

| | Y0 | Y1 | Y2 | Y3 | Total |
| --- | --- | --- | --- | --- | --- |
| Discounted Cost | 100,000 | 45,455 | 33,056 | 22,539 | **201,050** |
| Discounted Benefit | 0 | 63,637 | 49,584 | 15,026 | **128,247** |

NPV = 128,247 − 201,050 = **−72,803**

**Comment:** NPV < 0 → Project X should be **rejected** (does not meet the 10% target return).

**Project Y** — Cost: Y0=100,000. Benefit: Y0=0.

| | Y0 |
| --- | --- |
| Discounted Cost | 100,000 |
| Discounted Benefit | 0 |

NPV = 0 − 100,000 = **−100,000**

**Comment:** NPV < 0 → Project Y should be **rejected** (pure cost, no benefit).

**Most profitable:** Neither is profitable (both negative). If forced to choose, Project X (−72,803) loses less than Project Y (−100,000), but the correct exam answer is **reject both**.
