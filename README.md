# Market Basket Analysis in R

## 📌 Project Overview
This project performs Market Basket Analysis using the Apriori algorithm to uncover product associations from transaction data. The dataset was obtained from Kaggle and includes transaction records from a grocery store, providing valuable insights into customer purchasing behaviors.

## 📂 Dataset
groceries.csv: A dataset containing transaction details of groceries purchased by customers, where each row represents a transaction and each column represents a unique product.

## 📊 Methodology
1. Loading The Necessary Libraries
The following libraries are used in this project to perform Market Basket Analysis:
arules: for generating and handling association rules.
arulesViz: for visualizing the rules.
readr: for reading the dataset.

2. Loading The Dataset
The dataset is loaded into R as a transaction object, groceries, using the read.transactions() function. The dataset contains 9,835 transactions and 169 unique items.

3. Apply the Apriori Algorithm
The Apriori algorithm is applied to the dataset to extract association rules with the following parameters:
Support: Minimum frequency of itemsets in the dataset.
Confidence: Conditional probability of finding item B given that item A is present.
Minlen: Minimum length of itemsets.

4. Evaluate Model Performance
The model’s performance is evaluated using the following metrics:

Support: Indicates how frequently an itemset appears in the dataset.

Confidence: Represents the likelihood of finding item B when item A is purchased.

Lift: A measure of how much more likely one item is to be purchased relative to its typical purchase rate, given another item is purchased.

5. Improve Model Performance
To refine the model, association rules are sorted based on lift and confidence to highlight the most meaningful patterns. Subsets of rules related to specific items are also explored for more targeted insights.

## 📊 Insights
1. Most Frequent Items
Based on the dataset's frequent item counts, the most purchased items include:

Whole milk (2513 transactions)

Other vegetables (1903 transactions)

Rolls/buns (1809 transactions)

Soda (1715 transactions)

These items are key indicators of what customers typically purchase, providing a foundation for understanding common purchasing patterns.

2. Transaction Characteristics
Single-item transactions: 2,159 transactions contained only one item.

Multi-item transactions: The maximum number of items in a transaction was 32, with the average being 4.4 items.

Visualization: The distribution of transaction lengths is visualized using histograms, revealing a typical range of 2-4 items per transaction.

3. Association Rules with High Lift
After applying the Apriori algorithm, a few notable association rules emerged:

{herbs} => {root vegetables}: Customers who purchase herbs are nearly 4 times more likely to also purchase root vegetables (Lift = 3.96).

{berries} => {whipped/sour cream}: Berries are frequently bought with whipped/sour cream, suggesting a potential pairing for desserts (Lift = 3.79).

These rules provide actionable insights for improving product placement, promotions, or bundled offers in the store.

4. Insights from Specific Itemsets
By focusing on specific items, such as berries, the following insights were discovered:

{berries} => {whipped/sour cream}: A strong association suggests that marketing or promotions can target customers who buy berries to also consider whipped/sour cream, a pairing suitable for desserts.

{berries} => {yogurt}: Berries are also commonly purchased alongside yogurt, indicating a frequent combination for breakfast or lunch (Lift = 2.28).

5. Rule Evaluation: Actionable, Trivial, and Inexplicable Rules
By examining the generated association rules, they can be categorized as follows:

Actionable: Rules that reveal meaningful and relevant insights, such as the association between berries and whipped cream.

Trivial: Rules that are logical but not particularly useful, e.g., {whole milk} => {whole milk}.

Inexplicable: Rules that lack a clear reason for the association, such as {potted plants} => {whole milk}.

These categories help prioritize the most useful rules for real-world applications.

## 🔍 Conclusion
The Apriori algorithm provides valuable insights into customer purchasing behavior. The analysis identified meaningful patterns, such as the likelihood of purchasing certain products together. By refining the rules based on lift, confidence, and support, we can derive actionable strategies for improving product offerings, marketing, and sales strategies.

The success of this analysis relies on continuous refinement of the model and further exploration of additional rules, ultimately contributing to more effective decision-making in retail operations.
