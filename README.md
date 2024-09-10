# SuperKart Sales Prediction

## Introduction
Sales forecasting is a critical process for businesses as it involves predicting future sales revenue based on historical data, industry trends, and the current sales pipeline. Accurate sales forecasts are essential for improving decision-making, reducing risks, and optimizing operations across various organizational functions. They assist in planning sales operations by region, help the supply chain manage inventory, and establish benchmarks for future growth.

SuperKart, a chain of supermarkets and food marts, aims to predict future sales revenue for its outlets. This forecast will enable the company to strategize sales operations across different tier cities and optimize inventory planning.

## Objective
The objective of this analysis is to develop a model that predicts future sales revenue for SuperKart’s outlets. This forecast will help the company in optimizing inventory, improving sales operations, and ensuring efficient resource allocation based on anticipated demand across different city tiers and store types.

## Dataset
The dataset contains information on various product and store attributes. Each record represents the total sales for a particular product in a specific store. The attributes provided include product weight, sugar content, allocated display area, product type, maximum retail price (MRP), store details, and sales revenue.

### Data Dictionary
| Attribute                   | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **Product_Id**               | Unique identifier of each product, consisting of two letters followed by a number. |
| **Product_Weight**           | The weight of each product.                                                 |
| **Product_Sugar_Content**    | Sugar content of each product (low sugar, regular, no sugar).                |
| **Product_Allocated_Area**   | Ratio of the allocated display area of each product to the total display area of all products in a store. |
| **Product_Type**             | Broad category for each product (meat, snack foods, dairy, etc.).            |
| **Product_MRP**              | Maximum retail price of each product.                                        |
| **Store_Id**                 | Unique identifier of each store.                                             |
| **Store_Establishment_Year** | The year in which the store was established.                                 |
| **Store_Size**               | Size of the store (high, medium, low).                                       |
| **Store_Location_City_Type** | Type of city in which the store is located (Tier 1, Tier 2, Tier 3).         |
| **Store_Type**               | Type of store based on the products sold (Departmental Store, Supermarket Type 1, etc.). |
| **Product_Store_Sales_Total**| Total revenue generated by the sale of a product in a specific store.        |

## Exploratory Data Analysis (EDA)
A comprehensive EDA was performed to understand the structure of the dataset and the relationships between features. The key insights from this analysis include:

- **Product_Store_Sales_Total Distribution**: The sales distribution showed a normal curve with a slight right skew, and some outliers indicate high-performing products or stores.
- **Product_MRP Distribution**: The product MRP values are normally distributed, with a few outliers representing significantly more expensive or cheaper products.
- **Product_Allocated_Area Distribution**: The allocated display area of products showed a right-skewed distribution, indicating that a few products dominate store display areas.
- **Product_Weight**: The product weight distribution followed a normal curve, with a few outliers representing either very light or very heavy products.

### Categorical Feature Analysis
- **Product_Id**: The majority of products (74.6%) fell into the 'FD' category, indicating a large portion of products belong to this category.
- **Product_Sugar_Content**: More than half of the products (55.7%) had low sugar content, reflecting a focus on health-conscious consumers.
- **Product_Type**: Fruits and vegetables were the most common product type, followed by snack foods.
- **Store_Id**: Store OUT004 accounted for over 53% of total store entries, suggesting a significant concentration of data around this store.
- **Store_Size**: Most stores (68.8%) were categorized as medium-sized.
- **Store_Location_City_Type**: The majority of stores (71.5%) were located in Tier 2 cities, indicating a focus on mid-sized urban areas.
- **Store_Type**: Supermarket Type 2 accounted for over 50% of the stores, indicating this is the most common store format.

## Correlation Analysis
Key findings from the correlation matrix include:
- **Product_Weight**: Showed a strong positive correlation (0.74) with sales revenue, indicating that heavier products tend to generate higher sales.
- **Product_MRP**: Had a strong positive correlation (0.79) with sales revenue, suggesting that more expensive products are linked to higher total sales.
- **Store_Establishment_Year**: Showed weak negative correlations with key variables, indicating that newer stores tend to have lighter, cheaper, and lower-selling products, though the relationships are not significant.

## Outliers Analysis
Outliers were observed in features like Product_Weight, Product_Allocated_Area, and Product_MRP. These outliers were not removed because they represent realistic variations in product characteristics and store operations.

## Model Development and Evaluation
A linear regression model was developed to predict the total sales revenue based on the features in the dataset. The model demonstrated strong performance, with the following evaluation metrics:

### Training Set Evaluation:
- **RMSE**: 449.24
- **MAE**: 259.78
- **MAPE**: 9.97%
- **R²**: 0.821

### Test Set Evaluation:
- **RMSE**: 438.66
- **MAE**: 260.30
- **MAPE**: 9.78%
- **R²**: 0.833

### Model Insights:
- The model explained 82.1% and 83.3% of the variance in sales on the training and test sets, respectively, indicating a strong fit.
- Error metrics such as RMSE, MAE, and MAPE were consistent between training and test sets, suggesting good generalization to unseen data.

## Residual Analysis and Assumptions Testing
- **Residuals Mean**: The mean of the residuals was close to zero, indicating no systematic bias in the model's predictions.
- **Goldfeld-Quandt Test**: A p-value of 0.815 indicated no significant evidence of heteroscedasticity in the residuals, confirming that the assumption of homoscedasticity holds.

## Key Business Insights and Recommendations
### Store and City Type Analysis:
- **Supermarket Type 2** stores contribute the most to sales. Efforts should focus on inventory optimization and promotions in these stores.
- **Tier 2 cities** show lower sales performance compared to Tier 1 and Tier 3. Tailored marketing strategies can boost sales in these regions.

### Product Sales Performance:
- **Food items** generate the highest revenue. These should be the focus of inventory and sales strategies.
- **Higher MRP and heavier products** tend to have higher sales. Inventory management should prioritize these products, ensuring adequate stock levels for high-performing items.

## Conclusion
The linear regression model developed for predicting SuperKart’s sales shows strong performance and provides valuable insights into sales patterns. The model can be used for future sales forecasting, inventory management, and operational decision-making. The business recommendations derived from the model's insights can help SuperKart optimize its sales strategies across different store types, city tiers, and product categories.

## Technologies Used
- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**

## License
This project is licensed under the MIT License. See the LICENSE file for more details.
