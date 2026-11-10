# Digital Opportunity Analysis for Local Businesses (Madrid)

**Which well-reviewed local businesses in Madrid have no website, and are therefore the best prospects for digital services?**

A small end-to-end analytics project: data cleaning, exploratory analysis, hypothesis testing and a Tableau dashboard.

## Business question

A web-design or digital-marketing service needs to know where it can add the most value. This project looks for businesses that already have a strong reputation (so they are worth working with) but no web presence (so there is room to improve).

## Data

- 62 local businesses in Madrid (retail, restaurants, pubs and others).
- Fields: name, business type, rating, number of reviews, has a website (yes/no) and offers an online service (yes/no).
- Exactly half of the businesses have a website; 68% do not offer any online service.

## Method

1. **Cleaning:** website and online-service flags converted to 0/1, missing values checked.
2. **Exploratory analysis:** rating and review distributions compared between businesses with and without a website.
3. **Hypothesis testing:** Welch's t-tests (unequal variances) on rating and on reviews. Reviews are heavily skewed, so the test was repeated on log-transformed counts.
4. **Opportunity definition:** a business is "high reputation" when its rating is above 4.5 and it has more than 100 reviews. Those without a website are the target list.
5. **Dashboard:** results exported to Excel and visualised in Tableau.

## Key findings

| Question | Result |
|---|---|
| Does having a website go with a better rating? | No clear difference: mean 4.54 with a website vs 4.44 without (Welch t-test, p = 0.34). |
| Does having a website go with more reviews? | Yes: mean 1,186 reviews (median 525) with a website vs 225 (median 70) without. Welch t-test p = 0.004 on raw counts and p = 0.0003 on log-transformed counts. |
| Who are the best prospects? | 19 of the 62 businesses are high reputation. 11 have a website and **8 do not**: those 8 are the target list for digital services. |

In short: ratings are similar either way, but businesses without a website are far less visible, and eight of them already have the reputation to benefit from fixing that.

## Dashboard

The Tableau workbook (`Business Opportunity Dashboard.twbx`) highlights the businesses with the highest opportunity, built from `source for tableau.xlsx`.

## Limitations

- Small sample (62 businesses): the results are indicative, not conclusive.
- Observational data: businesses with a website may simply be larger, older or in different sectors, so the review gap is not proof that a website causes more reviews.
- The "high reputation" thresholds (4.5 stars, 100 reviews) are a judgement call.
- The notebook reads local files from the author's machine; update the paths to run it elsewhere.

## Repository contents

- `Business opportunity.ipynb`: cleaning, exploratory analysis and hypothesis tests (Python).
- `Business Opportunity Dashboard.twbx`: Tableau dashboard.
- `source for tableau.xlsx`: cleaned dataset used by the dashboard.

## Tools

Python (pandas, NumPy, SciPy, Matplotlib, Seaborn), Jupyter Notebook and Tableau.

## Author

Javier Peñaloza: Data Science & AI. [LinkedIn](https://www.linkedin.com/in/javier-pe%C3%B1aloza-tallia-74276b73/)
