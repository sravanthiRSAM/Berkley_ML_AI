# Will the Customer Accept the Coupon?

**Practical Application Assignment 5.1 — UC Berkeley Professional Certificate in ML/AI**

## Overview

This project analyzes data from the UCI Machine Learning Repository, collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios — including destination, time of day, weather, and passengers — and asks whether the driver would accept a coupon delivered to their phone. The goal is to distinguish between drivers who accepted a coupon and those who did not.

**[Link to Jupyter Notebook](prompt.ipynb)**

## Dataset

The dataset contains 12,684 survey responses with 26 attributes covering:

- **User attributes**: gender, age, marital status, education, occupation, income, and behavioral frequencies (bar visits, coffee house visits, restaurant visits, etc.)
- **Contextual attributes**: driving destination, weather, temperature, time of day, and passenger type
- **Coupon attributes**: coupon type and expiration window

There are five coupon types: Coffee House, Restaurant(<$20), Carry out & Take away, Bar, and Restaurant($20–$50).

## Key Findings

### Overall Acceptance

Approximately **56.93%** of all coupons offered were accepted by drivers. However, acceptance rates vary significantly by coupon type, with cheaper and more convenient options seeing the highest acceptance while bars and expensive restaurants see more rejection.

### Bar Coupons (41.19% overall acceptance)

- Drivers who visit bars **more than 3 times per month** accept bar coupons at **76.17%**, nearly double the **37.27%** rate of those who go 3 or fewer times.
- Drivers who visit bars **more than once per month AND are over 25** accept at **68.98%** vs. **33.77%** for all others — a 35-percentage-point gap.
- Drivers with **no kids as passengers** and **non-farming occupations** who visit bars more than once a month accept at **70.94%** vs. just **29.79%** for others.
- **Younger drivers** (under 30) who frequently visit bars are the most receptive demographic.

### Coffee House Coupons (49.63% overall acceptance — Independent Investigation)

- **Visit frequency** is the strongest predictor: frequent visitors (>1/month) accept at **65.90%** vs. **34.03%** for infrequent visitors.
- **Morning coupons** (7AM–10AM) have a **53.64%** acceptance rate, vs. **46.31%** for afternoon/evening.
- Drivers with **friends** accept at **59.74%** vs. **43.39%** for those driving alone.
- **Longer expiration** (1 day) yields **58.06%** acceptance vs. **42.91%** for 2-hour coupons.
- The **best-case profile** (frequent visitor, morning, no urgent destination) achieves an **81.09%** acceptance rate, while the **worst case** (infrequent, going to work) is just **29.69%**.

## Recommendations

1. **Target existing customers**: Drivers who already frequent a business type are 2–3x more likely to accept coupons. Focus coupon delivery on known patrons.
2. **Timing matters**: Deliver coffee house coupons in the morning, bar coupons in the evening. Match the coupon to the time when acceptance is naturally highest.
3. **Consider the context**: Drivers heading to "no urgent place" are the most receptive. Avoid targeting drivers commuting to work with non-essential coupons.
4. **Extend expiration windows**: 1-day expiration coupons consistently outperform 2-hour coupons across all types.
5. **Demographic targeting**: Younger adults (21–30) without children in the car are the most coupon-receptive segment for both bars and coffee houses.

## Repository Structure

```
├── README.md              # This file — nontechnical summary of findings
├── prompt.ipynb           # Jupyter notebook with full analysis and visualizations
└── data/
    └── coupons.csv        # Source dataset from UCI ML Repository
```

## How to Run

1. Clone the repository
2. Install dependencies: `pip install pandas numpy matplotlib seaborn jupyter`
3. Open the notebook: `jupyter notebook prompt.ipynb`
4. Run all cells sequentially
