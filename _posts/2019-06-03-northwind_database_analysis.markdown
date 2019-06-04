---
layout: post
title:      "Northwind Database Analysis"
date:       2019-06-04 02:13:31 +0000
permalink:  northwind_database_analysis
---

## Module 2 Project - Blog Post

### Assignment

The Module 2 Project involved analyzing Northwind Traders, a fictitious company created by Microsoft to allow beginning data scientists to practice their skills. Northwind Traders is an importer/exporter of speciality goods from around the world and the SQL database contained information on:

* Suppliers
* Customers
* Shipping Companies
* Orders 
* Order Details 
* Products 
* Employees 
* Sales 
* Inventory
* Territories 

The project prompt was an ambiguous one to say the least; analyze four hypotheses of your choosing that provide value to Northwind Traders. I thought about questions that could not only provide valuable insights to the company, but also provide some tangible next steps. 

### Question #1: Do discounts have a statistically significant impact on the number of products that customers order? If so, at what levels? 

**Null Hypothesis: The average quantity ordered by customers who do receive a discount is no different from that of customers who do not receive a discount.**

**Alternative Hypothesis: The average quantity ordered by customers who receive a discount is greater than 21.72 (the average quantity ordered by customers who did not receive a discount).**

In order to answer this question, I conducted a two-sample t-test to see whether there was a statistically significant difference between the average order size of non-discounted orders versus that of discounted orders. After checking that my data followed t-test assumptions (normality, randomness, independence), I separated non-discounted orders into a control group and discounted orders into an experimental group. 

My t-test was statistically significant and the Cohen's d measurement was 6.1, indicating that discount had a medium effect size on order sizes. Therefore, I was able to reject the null.

I then performed an ANOVA test to see what specific discount levels had a statistically significant difference from non-discounted orders. **After conducting an ANOVA test and a Tukey HSD test, and using the Bonferroni Correction to adjust for the multi-comparisons, I found that the 5%, 15%, 20%, and 25% discounts were statistically significant!**

### Question #2: Does time of year have a statistically significant impact on freight costs?

**Null Hypothesis: There is no difference in average freight price for each month.**

**Alternative Hypothesis: There is at least one average freight price that is different amongst all months.**

Similar to the first question, I used an ANOVA test and a Tukey HSD test to find if there was a statistically significant difference in freight prices each month. However, the p-value of the ANOVA test was .518, indicating that it was insigificant and I was unable to reject the null.

### Question #3: Is there a difference in unit price between supplier regions?

**Null Hypothesis: There is no difference in average unit price between supplier regions.**

**Alternative Hypothesis: There is at least one average unit price that is different amongst supplier regions.**

After some quick data visualizations, it was easy to confirm that pricing was not different amongst supplier regions. However, I used an ANOVA test to confirm, and I did just that when the returned p-value was insiginificant. 

### Question #4: Is there a difference in shipping company performance?

**Null Hypthesis: There is no difference in how quickly shipping companies ship order.**

**Alternative Hypothesis: Shipping companies ship orders at different speeds.**

Northwind Traders use 3 different shipping companies to perform their transporting: Federal Shipping, Speedy Express, and United Package. 

To calculate the number of days it took for an order to make its entire journey from start to finish, I subtracted the "Ordered Date" column from the "Received Date" column. I then used an ANOVA test to see if there was a statistically significant difference in the average time it took to deliver a package for each shipping company. The p-value came back insiginficant, so I was unable to reject the null hypothesis. 


### Conclusions 

* Continue to offer discounts in order to maximize order quantities and appease customers
* Freight cost doesn't differ across the year, focus planning shipments around logistical ease and customer expectations.
* Supplier costs don't differ, so Northwind should reevaluate what suppliers provide them with the most operational efficiency for deliveries. 




