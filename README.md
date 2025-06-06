# CREDIT-RISK-ANALYSIS
**INSIGHTS INTO TDI'S LOAN PORTFOLIO: VISUALIZING CUSTOMER RISK & FINANCIAL BEHAVIOR WITH DATA**

## **INTRODUCTION**
In today’s competitive financial landscape, understanding borrower behavior is key to reducing risk, increasing repayment rates, and improving overall profitability. The Data Immersed (TDI), a financial service company, provides individual and small business loans across the United States. To improve decision-making and reduce defaults, TDI has decided to examine its loan portfolio.

This project focuses on identifying patterns in loan approvals, defaults, and customer demographics. By analyzing the provided dataset using Excel, the aim is to uncover insights about borrower risk, payment behavior, and interest rate impact, helping the company make smarter, data-driven lending decisions.

![Screenshot (216)](https://github.com/user-attachments/assets/76d080fd-5abd-4586-9aef-c1e162e4c70a)

![Screenshot (220)](https://github.com/user-attachments/assets/89e33e11-39dc-4d60-8047-a73a85cec8d5)

## **INDUSTRY TYPE OF DATA**
This project falls under the Financial Services Industry. It is useful for financial institutions, credit analysts, loan officers, and business decision-makers involved in lending and risk management.

## **PROJECT OBJECTIVES**
The goal of this project is to help The Data Immersed (TDI) better understand what is really happening inside their loan portfolio. By digging into the data, we want to uncover what makes some loans perform better than others and why some customers struggle to repay.

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
4. Unnecessary Columns: Dropped irrelevant fields like Customer ID, Loan Application Type, and Sub-grade. Also removed the original DTI Ratio column since it was incorrectly calculated — replaced it with a new, correct version later on.
5. For clarity, I renamed columns with clearer, more descriptive titles to make the dataset easier to read and work with. Then, I used the IF function to convert state abbreviations into full state names for better clarity.
6. I replaced empty job title cells with "Others" using Find & Replace. Then used TRIM to remove extra spaces, LOWER to convert to lowercase, and PROPER to format titles properly.
7. Used the IFS function to map grade letters (A–G) in the Risk Level column to readable risk categories like “Minimal Risk,” “Very High Risk,” etc., then pasted the results as values into the original dataset.
8. Cleaned the Homeownership status column with TRIM, then used an IF formula to classify codes (like “R”, “MO”) into readable labels like Rent, Mortgage, Own, etc.
9. I fixed all date columns using Excel’s Text to Columns feature and formatting options. Made sure all date values were consistent and in the right format (D/M/Y).
10. Using the TRIM function, I removed unwanted spaces from columns like Job Length, Loan Status, and Loan Purpose. Then, I used PROPER to standardize text formatting in Loan Purpose.
11. Cleaned up the Loan Term column by using Text to Columns to remove spaces and convert terms to numeric values.
12. Used TRIM to remove extra spaces and an IF function to map codes like “SV” and “Not V” into readable values like “Source Verified” and “Not Verified”.
13. Found 2 blanks in the Annual Income column. Calculated the average income and filled in the blanks using Find & Replace. Then used IFS to group income levels into descriptive labels like “Small Earners” or “Wealthy Earners”.
14. For Decimal Formatting, I used the “Decrease Decimal” button on key numeric fields like DTI Ratio, Loan Installment, Interest Rate, and Loan Amount to round to 2 decimal places.
15. For Currency Formatting, I changed all relevant columns dealing with money into proper currency format.
16. In terms of grouping, I grouped Total Credit Account values into categories using IF (e.g., “Low Credit (1–20)”, “Very High Credit (61–80)”, etc.) for easier segmentation.
17. Found 3 blanks in the Loan Amount column. Filled them with the column’s average using the same method as income. Did the same for missing values in the Total Payment column.
18. Verified there were no blanks or extra spaces in important fields like DTI Ratio, Loan Installment, and Interest Rate using Find & Replace.

19. To achieve an in depth analysis, I added some new calculated fields:
Monthly Income: Calculated by dividing the Annual Income by 12.
Debt-to-Income (DTI) Ratio: Took the monthly loan installment, divided it by the monthly income, then multiplied by 100. This helped show how much of a customer’s income goes toward loan repayment.
DTI Category: Used an IF formula to classify DTI values:
- Low (DTI ≤ 36%)
- Manageable (36% < DTI ≤ 43%)
- High (DTI > 43%)

## **DATA ANALYSIS**
Before diving into specific metrics, I explored the TDI dataset to look for patterns that can guide my analysis. By visualizing key trends, I got valuable insights that can improve loan management and understand borrower behavior better.
- TDI has disbursed a total of $435.75M in loans, that is the full amount borrowers have received across the board.
- There were 38,574 loan applications in total, giving us a good volume of data to work with.
- The average interest rate across all these loans is 12.05%, which is not too high and not too low.
- Out of all applications, 83.33% got approved, which shows that TDI is fairly open when it comes to giving out loans.
- When we look at the total payments made by borrowers who finished repaying, it adds up to $473.07M. Thus means that TDI has brought in more than it gave out.
- Based on loan approval rating, 83.33% of the loans are fully paid, which is a great sign. It shows most borrowers are reliable and TDI’s lending process is working well. 13.83% of loans are charged off, the ones that were not repaid, and About 2.85% of loans are still current, which means they are in progress, but it is worth monitoring these closely to spot any signs of future repayment issues.
- In terms of actual dollar amounts, $351.35M worth of loans have been fully paid, $65.53M is the total charged-off amount, and $18.87M is currently active (in repayment).
- When looking at job length by income, it turns out that borrowers who have been in their jobs for 10+ years earn the most, bringing in a total income of $724.81 million. Interestingly, borrowers with shorter job lengths (like 1–5 years) sometimes earn more than those who have been at their jobs for 6, 7, 8, or even 9 years. This shows that longer time on the job doesn’t always mean higher income, something TDI should keep in mind when verifying employment details before approving loans.
- On the loan purpose by interest rate side, the goal is to understand which loan types are costlier for borrowers and riskier for TDI, and it shows that The average interest rate overall is 12.05%, and that helps us compare how each loan category stacks up.
- Loans for Small Business (13.03%), Debt Consolidation (12.50%), and House loans (12.38%) carry interest rates above average, which could mean they come with more risk for TDI.
- On the safer side, Car loans have the lowest average rate at 10.59%, making them less risky for both the company and borrowers. Medical and personal loans are also relatively safe, sitting just under the average at around 11%.
- When we look at why people are borrowing and how much they are taking, Debt Consolidation, Credit Card, and Home Improvement loans come out on top in terms of total loan amount. These categories involve big expenses, so borrowers usually take larger loans. But slicing the data by loan status shows that out of $232M in Debt Consolidation loans, about $36M has been charged off, which is a red flag. It looks like people borrow big to pay off multiple debts, but still struggle to repay, which proves the risk factor for this loan type.
- Home Improvement loans are also large, probably due to renovations or repairs, but they don’t seem as risky. Small Business loans could go either way. If a business is struggling or just starting out, repayment becomes shaky, which increases risk.
- On the Loan Issue Date by Loan Amount, January started slow with just $7,000 in loans. By February, there was an increase to $37,000, showing early signs of growth. From February to May, things stayed steady, Then between July and November, loan amounts skyrocketed to $232 million, with November alone hitting the peak. But just as fast as it rose, December dropped back down to $5,000.
- When we look at how much people borrow based on their home status, those with mortgages are borrowing the most, about $219.32M. Renters come next with $185.77M and Homeowners borrow the least, just $29.60M. Since they already own their homes, they might not need as much financial support.
- Based on how TDI checks borrower info before approving loans, Verified borrowers, those whose income, job, and credit info were manually confirmed through documents, got the biggest share: $196.96M. Not Verified borrowers got $139.69M. For these, TDI just trusted the info the borrower provided without doing any deep checks. Lastly, Source Verified borrowers, where TDI actually confirmed things directly (like calling up employers or banks), got the least: $99.09M, which is more reliable.
- For how much people earn with how many credit lines they have, low to middle earners tend to have a lot of credit lines, even if their income isn’t all that high, which means they might have trouble keeping up with repayments.
- This part helps us see if there’s a mismatch between what borrowers earn and how much they’re borrowing.

Turns out, high, small, and middle-high earners are taking out the biggest loans.

That’s a bit of a red flag — if someone has a low income but a high loan amount, their chances of default go up. TDI may want to dig deeper during evaluations to avoid lending more than a borrower can realistically handle.

⏳ Loan Term by Amount
Here, we’re comparing loan amounts based on how long borrowers choose to repay — either 36 or 60 months.

Most people go for the 36-month term, with loans totaling $273.03M, compared to $162.72M for the 60-month option.

Short-Term Loans (36 months): These are more common. While the loan amount might be smaller, monthly payments are higher and risk is more concentrated.

Long-Term Loans (60 months): These let borrowers spread out payments, so they can borrow more, but they end up paying more in total interest.

🌍 Region by Loan Amount
This one maps out where the loans are coming from, giving us a regional view of demand.

California leads big with $78.48M, followed by New York at $42.07M, and Texas at $31.24M. Clearly, these are hotspots for TDI’s loan activity.

On the flip side, Maine ($9K) and Nebraska ($32K) show the lowest numbers — which might point to lower demand or smaller populations.

This insight helps TDI spot where to focus more resources and where to scale back or investigate further.

TDI should probably be extra careful here. Before handing out more credit, it’s worth checking if the borrower can really handle it financially.

