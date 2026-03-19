# Will the Customer Accept the Coupon?

## Project Overview

This project analyzes survey data from Amazon Mechanical Turk to determine what factors influence whether a driver will accept a coupon delivered to their cell phone while driving. The dataset contains various driving scenarios with contextual information such as destination, weather, time of day, and passenger type, and records whether the driver accepted the coupon.

**Jupyter Notebook:** [prompt_II.ipynb](./prompt_II.ipynb)

---

## Key Findings

### Overall Acceptance Rate
- The overall coupon acceptance rate across all coupon types is approximately **56.8%**, meaning more than half of drivers in the survey accepted a coupon when offered one.

### Bar Coupons — Deep Dive

1. **Frequent bar-goers accept far more often**: Drivers who visit bars more than 3 times per month accepted bar coupons at a rate of ~**76%**, compared to ~**37%** for those who go 3 or fewer times per month.

2. **Age matters**: Drivers over age 25 who visit bars more than once a month accepted bar coupons at roughly **69%**, compared to all others at ~**34%**.

3. **Passengers & occupation**: Drivers who go to bars more than once a month, had no kid passengers, and were not in farming/fishing/forestry occupations showed an acceptance rate of ~**71%**.

4. **Social context**: Drivers who go to bars more than once a month, had passengers that were not kids, and were not widowed showed ~**71%** acceptance.

5. **Young social drivers**: Drivers under 30 who go to bars more than once a month showed ~**72%** acceptance.

6. **Budget dining crossover**: Drivers who go to cheap restaurants more than 4 times a month and have income under $50K showed ~**46%** bar coupon acceptance.

### Coffee House Coupons — Independent Investigation

1. **Overall coffee house acceptance rate**: ~**50%** of drivers accepted coffee house coupons.

2. **Frequent coffee house visitors**: Drivers who visit coffee houses 1–3 times per month show the highest acceptance rate at ~**65%**.

3. **Time of day effect**: Coffee house coupons offered at **10AM** and **2PM** had significantly higher acceptance rates (~**63%**) compared to evening hours (~**44%**).

4. **Destination impact**: Drivers with no urgent destination accepted coffee house coupons at ~**60%**, compared to ~**50%** for those heading home or to work.

5. **Expiration time**: Coupons with a **1-day** expiration window were accepted more often (~**59%**) than 2-hour coupons (~**43%**).

---

## Summary & Recommendations

### Who is most likely to accept coupons?

- **Bar coupons**: Target drivers who already visit bars frequently (3+ times/month), are under age 30, have adult passengers, and are not in farming/fishing occupations.
- **Coffee house coupons**: Target drivers with no urgent destination, offer coupons in the morning/early afternoon, and give at least 1-day expiration windows.

### Actionable Recommendations

1. **Personalize coupon timing**: Deliver bar coupons in the evening and coffee house coupons in the morning/afternoon for best results.
2. **Consider passenger context**: Drivers with adult passengers (friends, partners) are significantly more likely to accept social venue coupons.
3. **Prioritize loyal customers**: Drivers who already frequent a venue type are far more likely to accept coupons for that same type — retargeting existing customers is highly effective.
4. **Use longer expiration windows**: 1-day expiration coupons outperform 2-hour coupons; giving drivers more flexibility increases acceptance.
5. **Avoid targeting commuters**: Drivers heading to work or with urgent destinations have lower acceptance rates — route-based targeting should focus on leisure trips.

---

## Dataset

The data is from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/603/in+vehicle+coupon+recommendation), collected via Amazon Mechanical Turk. It contains 12,684 records with 26 attributes describing driving scenarios and coupon acceptance.

## Technologies Used

- Python 3
- pandas
- matplotlib
- seaborn
- Jupyter Notebook
