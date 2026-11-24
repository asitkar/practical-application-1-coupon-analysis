# Will the Customer Accept the Coupon? - EDA and Visualization Analysis

## Project Overview
This project analyzes survey data from Amazon Mechanical Turk to determine what factors influence whether a driver will accept a coupon delivered to their cell phone while driving. The dataset contains various driving scenarios with contextual information such as destination, weather, time of day, and passenger type, and records whether the driver accepted the coupon (`Y = 1` for accepted, `Y = 0` for rejected).

**Jupyter Notebook:** [`prompt_II.ipynb`](./prompt_II.ipynb)

---

## Data Cleaning & Preparation
- **Missing Values:** Handled missing data in columns such as `car`, `Bar`, `CoffeeHouse`, `CarryAway`, `RestaurantLessThan20`, and `Restaurant20To50`.
- **Filtering by Coupon Type:** Ensured that conditional acceptance analysis for specific coupon categories (such as Bar coupons or Coffee House coupons) is strictly filtered to recipients of that specific coupon type (`coupon == 'Bar'` or `coupon == 'CoffeeHouse'`).

---

## Key Findings

### 1. Overall Acceptance Rate
- The overall acceptance rate across all coupon types is **56.84%** (7,210 accepted out of 12,684 total coupon offers).

### 2. Bar Coupon Analysis (`coupon == 'Bar'`)
- **Overall Bar Coupon Acceptance Rate:** **40.99%** (827 accepted out of 2,017 Bar coupons).
- **Bar Visit Frequency:**
  - Drivers who visit bars **more than 3 times a month** (`> 3`): **76.47%** acceptance rate (117 / 153).
  - Remaining Bar coupon recipients (`<= 3` times a month): **38.09%** acceptance rate (710 / 1864).
  - *Finding:* Frequent bar patrons are nearly twice as likely to accept a Bar coupon compared to infrequent or non-visitors.
- **Age Factor (> 25 years old & > 1 bar visit/month):**
  - Drivers who visit bars **more than once a month and are over 25**: **69.52%** acceptance rate (292 / 420).
  - Remaining Bar coupon recipients: **33.50%** acceptance rate (535 / 1597).
- **Passenger & Occupation Filter (`passanger != 'Kid(s)'`):**
  - Drivers who visit bars **> 1 time/month, with non-kid passengers, and not in farming/fishing/forestry**: **70.18%** acceptance rate (393 / 560).
  - Remaining Bar coupon recipients: **29.79%** acceptance rate (434 / 1457).
- **Passenger & Marital Status Filter (`passanger != 'Kid(s)'` & `maritalStatus != 'Widowed'`):**
  - Drivers who visit bars **> 1 time/month, with non-kid passengers, and not widowed**: **70.18%** acceptance rate (393 / 560).
  - Remaining Bar coupon recipients: **29.79%** acceptance rate (434 / 1457).
- **Younger Drivers vs Cheap Restaurant Goers:**
  - Drivers visiting bars **> 1 time/month and under age 30**: **71.77%** acceptance rate (239 / 333).
  - Drivers visiting bars **> 1 time/month, visiting cheap restaurants > 4 times/month, and earning < $50k**: **44.12%** acceptance rate (15 / 34).

### 3. Coffee House Coupon Analysis (`coupon == 'CoffeeHouse'`)
- **Overall Coffee House Acceptance Rate:** **49.92%** (1,995 accepted out of 3,996 Coffee House coupons).
- **Coffee House Visit Frequency:**
  - Drivers who visit Coffee Houses **more than once a month** (`1~3`, `4~8`, `gt8`): **65.93%** acceptance rate (1,097 / 1,664).
  - Drivers who visit Coffee Houses **once or less a month** (`never`, `less1`): **38.14%** acceptance rate (868 / 2,276).
  - *Finding:* Regular Coffee House visitors are significantly more likely (65.93% vs 38.14%) to accept Coffee House coupons.
- **Time of Day Impact:**
  - Morning (10 AM): **63.96%** acceptance rate (575 / 899).
  - Early Afternoon (2 PM): **54.66%** acceptance rate (434 / 794).
  - Morning & Early Afternoon Combined (10 AM & 2 PM): **59.60%** acceptance rate (1,009 / 1,693).
  - Evening/Night (6 PM & 10 PM): **35.29%** acceptance rate (524 / 1,485).
  - Early Morning (7 AM): **56.48%** acceptance rate (462 / 818).
- **Passenger Context:**
  - Drivers traveling with **Friends**: **59.69%** acceptance rate (727 / 1,218).
  - Drivers traveling **Alone**: **47.68%** acceptance rate (1,006 / 2,110).

---

## Target Consumer Profiles & Recommendations

1. **Bar Coupons:** Target drivers who already visit bars regularly (> 1-3 times/month), especially those over 25 without child passengers in the vehicle.
2. **Coffee House Coupons:** Target morning/midday commuters (10 AM and 2 PM), drivers traveling with friends, and frequent coffee house visitors.
