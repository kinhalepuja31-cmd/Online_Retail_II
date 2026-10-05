# Online_Retail_II

# Task 28: Customer Repeat Purchase Analysis

Project Overview
This project focuses on evaluating customer retention, transaction behaviors, and purchasing frequencies using historical e-commerce data (Online Retail II dataset).

**Key Definitions**

Repeat Customer: Any individual customer who has completed two or more distinct, valid transactions (`total_orders > 1`) within the analysis timeframe.

One-Time Buyer:A customer who completed exactly one checkout transaction and never returned.

Average Order Value (AOV):** The average monetary spend calculated per distinct checkout invoice.


** Data Cleaning & Preprocessing Steps**
 
To protect calculation integrity and ensure business metrics reflect real economic value, the following systematic cleanup steps were executed using Python (Pandas) in Google Colab:

1.  Removing Unauthenticated Transactions: Inspected and removed records with missing `Customer ID` values (accounting for roughly ~22% of raw data). This prevents anonymous checkouts from artificially grouping into a massive false customer node.
2.  Filtering Out Cancellations: Maintained logical transactional integrity by filtering out all invoice records starting with a `"C"` or `"c"`.
3.  Enforcing Valid Values: Stripped systemic trailing whitespaces from headers to prevent index errors, and eliminated negative or zero values within `Quantity` and `Price` columns to clean out ledger corrections.
4.  Final Analytical Dataset: Formed a highly clean core pool of 8,05,549 valid transaction rows** for structural analysis.

   
**Technical Implementations (Google Colab / Python)**


1. Repeat Purchase Rate Calculation
Monitors the baseline ratio of returning multi-purchase customers against the entire user ecosystem.

2. AOV Group Comparison
Tracks the sequence hierarchy of transactions by assigning a cumulative order rank per consumer, explicitly slicing checkouts into `First-time` vs. `Repeat` cohorts to evaluate baseline average spending differences.

3. Customer Lifecycle Segmentation
Segments the dynamic customer directory into distinct, action-oriented strategic operational buckets:
  `One-time Buyer`: Exactly 1 distinct order.
 `Regular Repeat Buyer`: 2 to 4 distinct orders.
 `Highly Loyal/VIP`: 5 or more distinct orders.
 
** How to Run the Environment**
 
1. Open a blank notebook inside Google Colab.
2. Run your workspace connection cells.
3. Upload both target Excel worksheets simultaneously via the `google.colab.files.upload()` prompt.
4. Execute the structural cleaning and analysis modules sequentially to compute project metrics.

 **Deliverables & Results**
 
Clean Data Array: 8,05,549 valid records prepared for modeling.
Calculated Metrics: Repeat Purchase Rate (%), First-time vs. Repeat AOV (\$), and structural Value Segment counts.
