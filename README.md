
# Syria Telecom's Customer Churn Prediction
## Phase 3 Machine Learning Project

**Author:** Kelvin Ngumo  
**Date:** February 2026  
**Stakeholder:** Syria Telecomocunications


## **Project Goal**
The primary goal of this project is to build a classifier that predicts whether a customer will stop doing business with Syria Telecom's. 

## **The Business Problem**
In the telecommunications industry, acquiring a new customer is significantly more expensive than retaining an existing one. For Syria Telecom's, high churn rates lead to:
* **Revenue Loss:** Immediate loss of monthly subscription fees and usage charges.
* **Increased Marketing Costs:** High spend required to replace lost customers.

## **Objective**
By identifying "at-risk" customers through predictable patterns in usage and service interactions, Syria Telecom's can proactively offer retention incentives (discounts, plan upgrades) to reduce churn and protect the bottom line.


## **Data Source**
The dataset contains 3,333 records of customer activity, including usage minutes, service calls, and plan types.


### **Key Features for Analysis**
* **Target:** `churn` (Boolean)
* **Predictors:** * `customer service calls`: Indicators of customer satisfaction.
    * `total day charge` & `total intl charge`: Financial pressure points.
    * `international plan`: Potential indicator of specific customer needs.


## 1. Overview of the Problem
Our analysis of the subscriber base (3,333 customers) identifies a $14.5\%$ churn rate. While a $85.5\%$ retention rate appears stable, the lost customers represent high-value segments that significantly impact **Monthly Recurring Revenue (MRR)**. This report outlines a shift from reactive customer service to a predictive retention model.

---

## 2. Key Drivers of Churn (The "Why")
Using **Logistic Regression** and **Feature Importance** analysis, we have identified the primary factors driving customers to leave:

* **Service Friction:** *Customer Service Calls* are the strongest predictor of churn. For every additional call a customer makes, their likelihood of leaving increases by $2.8\times$ (Odds Ratio: $2.80$).
* **Plan Mismatch:** The *International Plan* is a high-risk product. Customers with this plan churn at a rate of $42.4\%$, compared to only $11.5\%$ for those without it. This suggests either a pricing issue or a "one-time use" behavior for travel.
* **Daytime Usage Intensity:** High *Total Day Minutes* and charges are strongly correlated with churn. This indicates that our most active daytime users are the most price-sensitive and likely to be "poached" by competitors.



---

## 3. Strategic Insights & "The Sticky Factor"
* **The Loyalty Anchor:** The *Voice Mail Plan* acts as a powerful retention tool. Customers with this plan are $55\%$ less likely to churn (Odds Ratio: $0.45$). This feature creates a "lock-in" effect that increases customer stickiness.
* **The Threshold of No Return:** Churn probability spikes significantly after the **3rd customer service call**. This represents a critical window for intervention.

---

## 4. Predictive Risk Scorecard Results
We have successfully deployed a batch scoring model across the entire database. Customers are now segmented by risk:

| Priority Level | Churn Probability | Strategic Action |
| :--- | :--- | :--- |
| **Critical** | $> 75\%$ | Immediate proactive outreach / Personalized loyalty offer. |
| **High** | $50\% - 75\%$ | Target with specific plan upgrades or service bundles. |
| **Medium** | $25\% - 50\%$ | Monitor for "friction signals" (e.g., new service calls). |
| **Low** | $< 25\%$ | Maintain standard loyalty communication. |

---

## 5. Actionable Recommendations
1.  **Implement a "Red Carpet" Workflow:** Automatically flag any customer reaching 3 service calls for immediate resolution by a senior specialist to prevent them from reaching the "point of no return."
2.  **Voice Mail Migration:** Encourage the adoption of the Voice Mail Plan for standard users. Bundling this for "free" in high-usage plans may yield a higher ROI through improved retention than through direct fees.
3.  **International Plan Audit:** Review the pricing structure of the International Plan. Since nearly half of these users churn, we should consider a "Pay-as-you-go" international tier or a loyalty discount for long-term international users.
4.  **Targeted Retention Offers:** Utilize the `Full_Customer_Churn_Risk_Report.csv` to prioritize retention budget. Focusing 100% of the budget on the "Critical" and "High" segments will maximize revenue protection while minimizing "waste" on customers unlikely to leave.

---

## 6. Conclusion
By operationalizing the **Churn Risk Scorecard**, the company can move from guessing why customers leave to knowing exactly who is at risk. Transitioning to this **Precision Retention Strategy** will allow the business to protect high-revenue accounts and decrease the overall churn rate by addressing service friction before it results in a cancellation.

---
### Data Reference
* **File:** `Full_Customer_Churn_Risk_Report.csv`
* **Model:** Logistic Regression (Balanced Training Set)
* **Key Metric:** $71\%$ Recall for Churning Customers


