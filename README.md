![logo_s](https://github.com/user-attachments/assets/8a9426d8-44e3-4592-9679-6a94e138d045)

# I-STAR
I-STAR is a shiny app that may be used by educators to generate easy statistical and psychometric reports for their exams.

## Internal Consistency
Internal consistency refers to how well the items in a test work together to measure the same skill or knowledge area. It is a key aspect of test reliability, helping us understand whether the test items are consistent in what they aim to assess. In this report, we include two commonly reported statistics: **Cronbach’s Alpha** and **Standardized Alpha**.
Cronbach’s Alpha is based on the actual item scores, while Standardized Alpha adjusts for differences in item scales by using correlations between items. Both values range from 0 to 1, with higher values indicating stronger internal consistency. Generally, values above 0.70 are acceptable for classroom assessments, values above 0.80 are considered good, and values above 0.90 suggest excellent reliability—though very high values might also indicate that some items are redundant.
It’s important to interpret these values in context. For example, a test with fewer items may show a lower alpha even if the items are well designed. On the other hand, tests with more items or a larger number of students tend to produce more stable and reliable estimates. For teachers, these statistics help evaluate whether test items are aligned and support meaningful, consistent assessment of student understanding.


## Item Statistics Table
The Item Statistics Table provides a detailed overview of how each question on the test performed across all students. It includes key measures such as the average score, standard deviation, minimum and maximum observed scores, and indicators of how well each item aligns with the overall test performance. These statistics help identify items that may be too easy, too difficult, or not effectively distinguishing between higher- and lower-performing students.
By reviewing this table, teachers can spot items that may need revision or removal. For example, items with very low variability or weak correlations with the total test score may not be contributing useful information. This analysis supports evidence-based decisions to improve the quality and fairness of future assessments, ensuring that each question contributes meaningfully to measuring student learning.
Interpreting the Item Statistics Table
The Item Statistics Table summarizes how each test item performed and helps teachers evaluate the quality and effectiveness of individual questions. Here’s how to interpret each column:
•	**Item_ID**: Identifies the specific test item.

•	**Diff.** (Difficulty Index): Represents how difficult the item was for students. Values closer to 0 indicate harder items, while values closer to 1 indicate easier items.

•	**Avg.score**: The average score students received on that item. Lower scores suggest the item was more difficult or potentially unclear.

•	**SD** (Standard Deviation): Shows how much variation there was in student responses. A higher SD means more variation; a low SD may indicate most students gave similar answers.

•	**Min. / Max**.: The lowest and highest scores achieved on that item.

•	**Obs.min. / Obs.max**.: The number of students who got the lowest or highest possible score on the item.

•	**RIT_pbis** (Point-Biserial Correlation): Indicates how well performance on the item correlates with overall test performance. Values above 0.20 are generally acceptable, and negative values suggest the item may not be functioning properly.

•	**RIR_DI** (Rest-Item Correlation or Discrimination Index): Reflects how well the item differentiates between high- and low-performing students. Higher values mean better discrimination.

•	**PBIS_Flag**: Flags items with low or negative point-biserial values. These items may need to be reviewed for clarity, alignment, or fairness.

By reviewing this table, teachers can identify strong items that contribute positively to the test, as well as items that may need revision to better assess student understanding


## 📊 What Is the Alpha Drop Table?

The **Alpha Drop Table** shows how the **overall reliability** of a test (measured by **Cronbach’s alpha**) would change **if each item were removed** from the test.

It’s a diagnostic tool to help **identify weak or problematic items** that might be **hurting the reliability** of your test.



## 🔍 Key Columns in the Table

When you run `psych::alpha(data)$alpha.drop` in R, the table typically includes:

| Column          | What It Means                                                                 |
| --------------- | ----------------------------------------------------------------------------- |
| **raw\_alpha**  | The Cronbach's alpha value **if that item is dropped** from the scale         |
| **std.alpha**   | The standardized alpha (based on z-scored items), if that item is dropped     |
| **G6(smc)**     | Guttman’s Lambda 6 using squared multiple correlations                        |
| **average\_r**  | Average correlation between that item and all other items                     |
| **s** (item SD) | The standard deviation of the item                                            |
| **r.drop**      | The correlation between that item and the total score **excluding** that item |


## ✅ How to Interpret It

### 1. **raw\_alpha / std.alpha**

* If removing an item **increases alpha**, it means the item is **not contributing positively** to reliability.
* If alpha **decreases**, the item is **helpful** and consistent with others.

> 👉 **Look for items where alpha increases when dropped — these may need review.**


### 2. **r.drop**

* Correlation of the item with the total test score (excluding itself).
* **Values below 0.30** may indicate the item **does not align** well with the overall test.
* High values (e.g., > 0.50) mean the item fits well.

> ❗ **Low r.drop suggests the item may be poorly written or measuring something else.**



### 3. **average\_r**

* The item's average correlation with the other items.
* Helps detect items that don't "fit in" with the overall test.



### 🔎 Example Use:

Suppose your overall Cronbach’s alpha is **0.78**, but when you drop **Item 4**, alpha increases to **0.81**. This suggests:

* **Item 4** may be problematic (misunderstood, irrelevant, or inconsistently answered)
* Consider revising or removing that item to improve test reliability


## 📘 Summary

The Alpha Drop Table helps you:

* Evaluate each item's **contribution to reliability**
* Identify **inconsistent** or **low-quality** items
* Make decisions about **revising or removing** items to improve your assessment


## Item Response Distributions
The Item Response Distribution Graphs provide a visual summary of how students responded to each individual test item. Each bar in the graph represents the percentage of students who selected or scored a particular response value. These graphs help teachers quickly identify whether an item was too easy (e.g., most students scored the highest value), too difficult (e.g., most scored at the lowest), or had a balanced distribution.
Well-performing items often show a spread of responses that distinguish between students of varying ability levels. In contrast, items where nearly all students chose the same response may not be providing useful information about student differences. These visualizations support teachers in identifying patterns, spotting unexpected response trends, and making informed decisions about item clarity, difficulty, and alignment with learning objectives.
