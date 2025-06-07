# CREDIT-RISK-ANALYSIS
**INSIGHTS INTO TDI'S LOAN PORTFOLIO: VISUALIZING CUSTOMER RISK & FINANCIAL BEHAVIOR WITH DATA**

## **INTRODUCTION**
In today’s competitive financial landscape, understanding borrower behavior is key to reducing risk, increasing repayment rates, and improving overall profitability. The Data Immersed (TDI), a financial service company, provides individual and small business loans across the United States. To improve decision-making and reduce defaults, TDI has decided to examine its loan portfolio.

This project focuses on identifying patterns in loan approvals, defaults, and customer demographics. By analyzing the provided dataset using Excel, the aim is to uncover insights about borrower risk, payment behavior, and interest rate impact, helping TDI make smarter, data-driven lending decisions.

![Screenshot (216)](https://github.com/user-attachments/assets/76d080fd-5abd-4586-9aef-c1e162e4c70a)

![Screenshot (220)](https://github.com/user-attachments/assets/89e33e11-39dc-4d60-8047-a73a85cec8d5)

## **INDUSTRY TYPE OF DATA**
This project falls under the Financial Services Industry. It is useful for financial institutions, credit analysts, loan officers, and business decision-makers involved in lending and risk management.

## **PROJECT OBJECTIVES**
The goal of this project is to help The Data Immersed (TDI) better understand what is really happening in their loan portfolio. By digging into the data, we want to uncover what makes some loans perform better than others and why some customers struggle to repay.

- Figure out the key things that should be considered before approving a loan, not just credit score, but deeper insights like job type, income, and more.
- Spot patterns around loan defaults to understand what puts a customer at risk, especially when it comes to income level and employment history.
- See how interest rates affect repayment. Do higher rates mean higher risk, or is there more to the story?
- Break down how loan amounts and purposes vary between different types of customers.
- Check for regional trends in loan performance, are some areas doing better or worse than others, and why?
- Ultimately, find ways to make better loan decisions, reduce default rates, and improve profits without compromising customer satisfaction.

## **DATA CLEANING STEPS TAKEN**
1. I started by downloading the zipped dataset, extracted it, and converted the main file into an Excel format for easier cleaning. Then, I created a separate worksheet ("Rough Worksheet") where I cleaned each column individually, copying data over from the original to keep things organized.
2. 2 blank rows were found, and I simply highlighted and deletied them.
3. For the purpose of removing duplicates, I used Conditional Formatting on the Member ID column to highlight duplicate entries. Then sorted them to the top, and used Excel’s Remove Duplicates feature to delete 15 duplicate rows.
4. For clarity, I renamed columns with clearer, more descriptive titles to make the dataset easier to read and work with. Then, I used the IF function to convert state abbreviations into full state names for better clarity.
5. I replaced empty job title cells with "Others" using Find & Replace. Then used TRIM to remove extra spaces, LOWER to convert to lowercase, and PROPER to format titles properly.
6. Used the IFS function to map grade letters (A–G) in the Risk Level column to readable risk categories like “Minimal Risk,” “Very High Risk,” etc., then pasted the results as values into the original dataset.
7. Cleaned the Homeownership status column with TRIM, then used an IF formula to classify codes (like “R”, “MO”) into readable labels like Rent, Mortgage, Own, etc.
8. I fixed all date columns using Excel’s Text to Columns feature and date formatting options. Made sure all date values were consistent and in the right format (D/M/Y).
9. Using the TRIM function, I removed unwanted spaces from columns like Job Length, Loan Status, and Loan Purpose. Then, I used PROPER to standardize text formatting in Loan Purpose.
10. Cleaned up the Loan Term column by using Text to Columns to remove spaces and convert terms to numeric values.
11. Used TRIM to remove extra spaces and an IF function to map codes like “SV” and “Not V” into readable values like “Source Verified” and “Not Verified”.
12. Found 2 blanks in the Annual Income column. Calculated the average income and filled in the blanks using Find & Replace. Then used IFS to group income levels into descriptive labels like “Small Earners” or “Wealthy Earners”.
13. For Decimal Formatting, I used the “Decrease Decimal” button on key numeric fields like DTI Ratio, Loan Installment, Interest Rate, and Loan Amount to round to 2 decimal places.
14. For Currency Formatting, I changed all relevant columns dealing with money into proper currency format.
15. In terms of grouping, I grouped Total Credit Account values into categories using IF (e.g., “Low Credit (1–20)”, “Very High Credit (61–80)”, etc.) for easier segmentation.
16. Found 3 blanks in the Loan Amount column. Filled them with the column’s average using the same method as income. Did the same for missing values in the Total Payment column.
17. Verified there were no blanks or extra spaces in important fields like DTI Ratio, Loan Installment, and Interest Rate using Find & Replace.

18. To achieve an in depth analysis, I added some new calculated fields:
Monthly Income: Calculated by dividing the Annual Income by 12.
Debt-to-Income (DTI) Ratio: Took the monthly loan installment, divided it by the monthly income, then multiplied by 100. This helped show how much of a customer’s income goes toward loan repayment.
DTI Category: Used an IF formula to classify DTI values:
- Low (DTI ≤ 36%)
- Manageable (36% < DTI ≤ 43%)
- High (DTI > 43%)

## **DATA ANALYSIS**
Before diving into specific metrics, I explored the TDI dataset to look for patterns that can guide my analysis. By visualizing key trends, I got valuable insights that can improve loan management and understand borrower behavior better.

**KEY METRICS**
- TDI has disbursed a total of $435.75M in loans, that is the full amount borrowers have received across the board.
- There were 38,574 loan applications in total, giving us a good volume of data to work with.
- The average interest rate across all these loans is 12.05%, which is not too high and not too low.
- When we look at the total payments made by borrowers who finished repaying, it adds up to $473.07M. Thus means that TDI has brought in more than it gave out.

  **INSIGHTS**
- Based on borrower repayment behaviour, 83.33% of the loans are fully paid, which is a great sign. It shows most borrowers are reliable and TDI’s lending process is working well. 13.83% of loans are charged off, the ones that were not repaid, and about 2.85% of loans are still current, which means they are in progress, but it is worth monitoring closely to spot any signs of future repayment issues.
- When looking at job length by income, it turns out that borrowers who have been in their jobs for 10+ years earn the most, bringing in a total income of $724.81 million. Interestingly, borrowers with shorter job lengths (like 1–5 years) sometimes earn more than those who have been at their jobs for 6, 7, 8, or even 9 years. This shows that longer time on the job doesn’t always mean higher income, something TDI should keep in mind when verifying employment details before approving loans.
- On the loan purpose by interest rate side, the goal is to understand which loan types are costlier for borrowers and riskier for TDI, and it shows that the average interest rate overall is 12.05%, and that helps us compare how each loan category stacks up. Loans for Small Business (13.03%), Debt Consolidation (12.50%), and House loans (12.38%) carry interest rates above average, which could mean they come with more risk for borrowers and TDI.
- On the safer side, Car loans have the lowest average rate at 10.59%, making them less risky for both the company and borrowers. Medical and personal loans are also relatively safe, sitting just under the average at around 11%.
- When we look at why people are borrowing and how much they are taking, Debt Consolidation, Credit Card, and Home Improvement loans come out on top in terms of total loan amount. These categories involve big expenses, so borrowers usually take larger loans. But slicing the data by loan status shows that out of $232M in Debt Consolidation loans, about $36M has been charged off, which is a red flag. It looks like people borrow big to pay off multiple debts, but still struggle to repay, which proves the risk factor for this loan type.
- Home Improvement loans are also large, probably due to renovations or repairs, but they don’t seem as risky. Small Business loans could go either way. If a business is struggling or just starting out, repayment becomes shaky, which increases risk.
- On the Loan Issue Date by Loan Amount, January started slow with just $7,000 in loans. By February, there was an increase to $37,000, showing early signs of growth. From February to May, things stayed steady, Then between July and November, loan amounts skyrocketed to $232 million, with November alone hitting the peak. But just as fast as it rose, December dropped back down to $5,000.
- When we look at how much people borrow based on their home status, those with mortgages are borrowing the most, about $219.32M. Renters come next with $185.77M and Homeowners borrow the least, just $29.60M. Since they already own their homes, they might not need as much financial support.
- Based on how TDI checks borrower info before approving loans, Verified borrowers, those whose income, job, and credit info were manually confirmed through documents, got the biggest share: $196.96M. Not Verified borrowers got $139.69M. For these, TDI just trusted the info the borrower provided without doing any deep checks. Lastly, Source Verified borrowers, where TDI actually confirmed things directly (like calling up employers or banks), got the least: $99.09M, which is more reliable.
- For how much people earn with how many credit lines they have, low to middle earners tend to have a lot of credit lines, even if their income isn’t all that high, which means they might have trouble keeping up with repayments. TDI should probably be extra careful here. Before handing out more credit, it’s worth checking if the borrower can really handle it financially.
- Comparing a borrowers income and how much they’re borrowing, turns out, high, small, and middle-high earners are taking out the biggest loans. if someone has a low income but a high loan amount, their chances of default go up. TDI may want to dig deeper during evaluations to avoid lending more than a borrower can realistically handle.
- Comparing loan amounts based on how long borrowers choose to repay, most people go for the 36-month term, with loans totaling $273.03M, compared to $162.72M for the 60-month option.
- Based on regional view of demand, California leads big with $78.48M, followed by New York at $42.07M, and Texas at $31.24M. Clearly, these are hotspots for TDI’s loan activity. On the flip side, Maine ($9K) and Nebraska ($32K) show the lowest numbers, which might point to lower demand or smaller populations.
- Analyzing with DTI ratios and income, Low DTI equals Lower Risk and High DTI equals Higher Risk. This means that, borrowers with Low DTI use a small part of their income to pay off debt, while borroers with High DTI ratio are already spending a large chunk of their income on debt payments, making them riskier to lend to.

## **RECOMMENDATIONS**

1. Offer smaller, lower-interest loans to low-income borrowers to reduce risk and attract reliable payers. For middle-income borrowers, watch larger loans closely, while high-income borrowers can be safely offered bigger loans to boost profits

2. TDI should be stricter with larger loans by requiring stronger credit scores or verified income to reduce the chances of defaults. 

3. Offering financial education to low-income borrowers can help them manage loans better and build financial stability. Offering flexible repayment plans can also help reduce defaults and improve repayment consistency

4. Emphasizing income and job verification during the approval process can improve portfolio quality and reduce risky loans. 

5. Don’t rely too heavily on job length as an income signal: 
   Long job tenure doesn’t always equal higher income. Focus more on actual income rather than how long someone’s been at their job when assessing repayment ability.

6. Be cautious with Small Business and Debt Consolidation loans: 
   These carry higher-than-average interest rates and charged-off amounts. Consider stricter vetting or smaller amounts to reduce risk exposure.

7. Lean into Car and Medical Loans, they are safer.
   These loan types show lower interest rates and fewer red flags, making them a lower-risk product category to promote.

8. Use seasonality to your advantage.
   Loan demand spikes between July and November. Plan targeted promotions during these months. Also, due to increase in demand, tighten verification process befor approval to reduce default reates. Lastly, introduce special offers with marketing strategies tied to festive promotions and rewards in December to avoid the usual dip. 

9. Prioritize verified borrowers.
   Borrowers with verified income, job, and credit details accounted for the largest and safest loan amounts. It’s worth the extra effort.

10. Be cautious with self-reported data.
    "Not Verified" borrowers received a substantial loan volume but carry more risk. Shift towards more verification to protect TDI.

11. Homeowners don’t borrow as much, so focus on renters and mortgage holders.
    These two groups have higher borrowing needs and may respond better to tailored offers or repayment plans.

12. Pay close attention to borrowers with many credit lines and modest income.
    High credit line counts among low earners can signal financial strain. Add this as a flag in your risk model. 

13. Match loan size with real income.
    Avoid granting large loans to low-income earners. It’s a strong risk indicator and may lead to default. Use income-to-loan ratios more aggressively during evaluation. TDI can prioritize approving loans for borrowers with low DTI ratios since they are less likely to default, while being more cautious with high DTI applicants by setting clear debt limits. 

14. Keep promoting the 36-month loan term option, it is in high demand.
    Most borrowers choose this term, so offering flexible features like early payoff rewards or lower fees for this option could increase satisfaction.

15. California, New York, and Texas are top-performing regions. Consider geo-targeted ads and partnership programs in these locations to expand market share.
    For low-demand states like Maine or Nebraska, explore smaller, community-focused campaigns with tailored benefits.

In conclusion, TDI can improve its loan approval process by verifying borrower information more carefully and matching loan amounts to each borrower’s income and credit behavior. By focusing on popular loan terms like 36-month plans and expanding in high-demand regions, TDI can reduce risks, support more customers, and grow sustainabl

