<img width="1024" height="1024" alt="1000069341" src="https://github.com/user-attachments/assets/523ebf03-2351-4765-903a-b891a78791b0" />


Shiny App Access: https://istar.shinyapps.io/ISTAR/ 

# I-STAR
I-STAR is a shiny app that may be used by educators to generate easy statistical and psychometric reports for their exams.

## Internal Consistency
Internal consistency refers to how well the items in a test work together to measure the same skill or knowledge area. It is a key aspect of test reliability, helping us understand whether the test items are consistent in what they aim to assess. In this report, we include two commonly reported statistics: **Cronbach’s Alpha** and **Standardized Alpha**.
Cronbach’s Alpha is based on the actual item scores, while Standardized Alpha adjusts for differences in item scales by using correlations between items. Both values range from 0 to 1, with higher values indicating stronger internal consistency. Generally, values above 0.70 are acceptable for classroom assessments, values above 0.80 are considered good, and values above 0.90 suggest excellent reliability—though very high values might also indicate that some items are redundant.
It’s important to interpret these values in context. For example, a test with fewer items may show a lower alpha even if the items are well designed. On the other hand, tests with more items or a larger number of students tend to produce more stable and reliable estimates. For teachers, these statistics help evaluate whether test items are aligned and support meaningful, consistent assessment of student understanding.


## Item Statistics Table
The Item Statistics Table provides a detailed overview of how each question on the test performed across all students. It includes key measures such as the average score, standard deviation, minimum and maximum observed scores, and indicators of how well each item aligns with the overall test performance. These statistics help identify items that may be too easy, too difficult, or not effectively distinguishing between higher- and lower-performing students.
By reviewing this table, teachers can spot items that may need revision or removal. For example, items with very low variability or weak correlations with the total test score may not be contributing useful information. This analysis supports evidence-based decisions to improve the quality and fairness of future assessments, ensuring that each question contributes meaningfully to measuring student learning.

🧪 How to Read the Item Statistics Table
The Item Statistics Table summarizes how each test item performed and helps teachers evaluate the quality and effectiveness of individual questions. Here’s how to interpret each column:

| Column             | What It Means                                                                                             |
|-------------------|-----------------------------------------------------------------------------------------------------------|
| **Item_ID**        | Identifies the specific test item.                                                                        |
| **Diff.**          | Difficulty index: values closer to 0 indicate harder items; values closer to 1 indicate easier items.     |
| **Avg.score**      | The average score students received on that item. Lower scores may indicate difficulty or confusion.      |
| **SD**             | Standard deviation of scores. High SD = more variation in answers; low SD = similar responses.            |
| **Min. / Max.**    | The lowest and highest scores achieved on that item.                                                      |
| **Obs.min. / Obs.max.** | Number of students who got the lowest or highest possible score on the item.                        |
| **RIT_pbis**       | Point-biserial correlation with total score. Values above 0.20 are desirable; negative values raise flags.|
| **RIR_DI**         | Rest-Item Correlation or Discrimination Index: measures how well the item distinguishes performance levels.|
| **PBIS_Flag**      | Flags items with low or negative point-biserial correlation. These may need revision or review.           |


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


# 🔁 Share your Feedback
Please share your feedback with us so we improve!
Google Form link: https://forms.gle/3fjWT4SivSUodCwg8 

# I-STAR Shiny App View

These are a few screenshot of the shiny app:
The app has a limitation (it only allows the use for at most 25 students and at most 20 items, even if the /csv file will be larger the app will only use teh first 25x20 dimensions). A Warning message will pop up when the data exceeds the default dimensions. Another Pro version will have more options and allow more data.

![image](https://github.com/user-attachments/assets/50cca3a5-c12c-487f-bb09-bffc623d8e4e)

![image](https://github.com/user-attachments/assets/d494fce5-ae8a-49cf-b45a-3690315c2feb)

![image](https://github.com/user-attachments/assets/65e2033a-8aaf-47d0-94ff-f9da168ab1f4)

![image](https://github.com/user-attachments/assets/35fa0099-8453-469b-82e8-d2764014bede)

![image](https://github.com/user-attachments/assets/bade9344-aa6a-4939-a4fb-60e4b87484e8)

![image](https://github.com/user-attachments/assets/00df514c-7c20-4e41-b471-94a1e438a518)

![image](https://github.com/user-attachments/assets/ca3e165e-dafc-4767-b594-1e92b1d773a8)


The Downloadble report (Word document to give the user access of copy-paste and modify)

![image](https://github.com/user-attachments/assets/d08b0b3e-d4ab-4344-b25f-9901ea35f562)

![image](https://github.com/user-attachments/assets/ccc8d478-6508-4c9d-96d0-51a05dafcf24)




