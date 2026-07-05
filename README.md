# Workplace Cooperation & Stress Analysis

## Overview
Does being cooperative at work make you more stressed? This project investigates the relationship between cooperative behavior and workplace stress using survey data collected from 30+ respondents. Two hypotheses were tested using independent samples t-tests and moderated regression analysis in Excel. The project was completed as part of BUS-631 Organizational Behavior at Utica University.

**Research Question:** Do employees who are cooperative in the workplace feel more stressed?

---

## 🛠️ Tools & Technologies
- Microsoft Excel
- Google Forms (survey collection)
- Independent Samples T-Test
- Moderated Regression Analysis

---

## 📂 Dataset
- **Source:** Primary data collected via Google Forms survey
- **Sample Size:** 30+ responses
- **File:** `Workplace_Cooperation_and_Stress_Survey.csv`
- **Key Variables:**

| Variable | Type | Scale |
|---|---|---|
| Cooperative Behavior | Independent | 7-point Likert (Lu et al., 2013) |
| Workplace Stress | Dependent | 4-item scale (Motowidlo et al., 1986) |
| Job Demands | Moderator | 7-point Likert |

---

## 🔍 Analysis & Solutions

### 1️⃣ Calculate the Median of Cooperative Behavior (Independent Variable)
Used Excel's MEDIAN function to find the midpoint of cooperative behavior scores.

```excel
=MEDIAN(data_range)
```

### 2️⃣ Split Sample into High and Low Cooperative Groups
Created a binary grouping variable using an IF statement — 1 for high cooperative behavior (above median), 0 for low.

```excel
=IF(data > median, 1, 0)
```

### 3️⃣ Hypothesis 1 — T-Test: Cooperative Behavior vs. Workplace Stress
Ran an independent samples t-test comparing stress levels between the high and low cooperative behavior groups.

```excel
=T.TEST(high_group_stress, low_group_stress, 2, 3)
```

### 4️⃣ Hypothesis 2 — Moderated Regression: Job Demands as Moderator
Tested whether job demands moderate the relationship between cooperative behavior and workplace stress by including an interaction term (Cooperative Behavior × Job Demands) in a regression model.

---

## 📊 Key Findings

### Hypothesis 1 — Not Supported
**Hypothesis:** Employees with higher cooperative behavior will report higher workplace stress.

| Metric | Value |
|---|---|
| t-statistic | 1.679 |
| p-value | 0.109 |
| Mean Stress (High Cooperative) | 5.0 |
| Mean Stress (Low Cooperative) | 4.403 |

While the high cooperative group showed slightly higher average stress (5.0 vs. 4.403), the difference was not statistically significant (p = 0.109 > 0.05). We cannot conclude that cooperative behavior leads to higher stress.

### Hypothesis 2 — Not Supported
**Hypothesis:** Job demands will moderate the relationship between cooperative behavior and stress, such that cooperation leads to more stress when job demands are high.

| Metric | Value |
|---|---|
| Interaction term p-value | 0.701 |

The interaction between cooperative behavior and job demands was not significant (p = 0.701 > 0.05). Job demands do not meaningfully change the effect of cooperative behavior on stress levels.

### Additional Finding — Job Demands Significantly Predict Stress ✅
Although the main hypotheses were not supported, job demands on their own were a significant predictor of workplace stress:

| Metric | Value |
|---|---|
| Coefficient | 0.498 |
| p-value | 0.005 |

Higher job demands are associated with higher stress levels, regardless of how cooperative an employee is.

---

## 📈 Overall Model Performance

| Metric | Value |
|---|---|
| R² | 0.288 |
| Model p-value | 0.029 |

The regression model is statistically significant (p = 0.029) and explains 28.8% of the variance in workplace stress. The remaining ~71% is likely driven by factors not included in this study.

---

## Conclusion
Cooperative behavior alone does not significantly predict workplace stress, and job demands do not meaningfully amplify or reduce that relationship. However, job demands independently are a strong and significant driver of stress. This suggests that organizations looking to reduce employee stress should focus on managing workload and job demands rather than discouraging cooperation. Future research should explore additional predictors such as autonomy, social support, and role clarity to better explain the remaining variance in workplace stress.

---

## References
- Lu, L., et al. (2013). Cooperation scale. *International Journal of Project Management.*
- Motowidlo, S. J., et al. (1986). Occupational stress scale. *Journal of Applied Psychology.*
- Diener, E., et al. (1985). Satisfaction with Life Scale. *Journal of Personality Assessment.*# Workplace_Stress_Excel
