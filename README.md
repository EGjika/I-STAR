# I-STAR
I-STAR is a shiny app that may be used by educators to generate easy statistical and psychometric reports for their exams.




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

---

Let me know if you'd like to show **color coding** for these statistics in your Shiny table, or explain this inside the app for users!
