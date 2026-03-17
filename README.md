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

### Bar Coupons Hypothesis

- **Frequency of bar visits matters most**: Drivers who already visit bars more than 3 times a month are significantly more likely to accept bar coupons. This is the strongest indicator. Habitual bar-goers are naturally more receptive of the coupons.
- **Age plays a role**: Younger drivers (under 30) and those over 25 who are frequent bar visitors both show higher acceptance rates. The combination of youth and existing bar-going behavior is a strong indicator..
- **Passenger context matters**: Drivers without children as passengers are more likely to accept bar coupons, which makes sense taking kids to a bar is less practical.
- **Economic factors**: Drivers who eat at cheap restaurants frequently and have lower incomes also show higher acceptance, suggesting price-conscious consumers who dine out often are open to bar coupon deals..

### Coffee House Coupons (Independent Investigation)

- **Visit frequency** is the strongest predictor: frequent visitors (>1/month) accept at **65.90%** vs. **34.03%** for infrequent visitors.
- **Morning coupons** (7AM–10AM) have a **53.64%** acceptance rate, vs. **46.31%** for afternoon/evening.
- Drivers with **friends** accept at **59.74%** vs. **43.39%** for those driving alone.
- **Longer expiration** (1 day) yields **58.06%** acceptance vs. **42.91%** for 2-hour coupons.
- The **best-case profile** (frequent visitor, morning, no urgent destination) achieves an **81.09%** acceptance rate, while the **worst case** (infrequent, going to work) is just **29.69%**.

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
