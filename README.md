# 🚖 Dynamic Pricing with Machine Learning  

This project implements **feature engineering and exploratory data analysis (EDA)** for a dynamic ride pricing system. The goal is to build a pricing engine that adjusts fares in real time based on supply-demand, customer behavior, and competitor trends.  

---

## 📌 Dataset  
The dataset (`dynamic_pricing.csv`) includes:  
- Number_of_Riders  
- Number_of_Drivers  
- Location_Category (Urban, Suburban, Rural)  
- Customer_Loyalty_Status (Bronze, Silver, Gold, Platinum)  
- Number_of_Past_Rides  
- Average_Ratings  
- Time_of_Booking (Morning, Afternoon, Evening, Night)  
- Vehicle_Type (Economy, Premium)  
- Expected_Ride_Duration  
- Historical_Cost_of_Ride  

---

## ⚙️ Steps Completed  

### 1. Data Preprocessing  
- Converted columns into proper numeric and categorical types  
- Handled missing values with median (numeric) or `"Unknown"` (categorical)  
- Applied sanity checks (e.g., ratings between 1 and 5)  

### 2. Feature Engineering  
New engineered features were added to capture **supply-demand, customer behavior, and competitor influence**:  
- `Competitor_Price_Index` → relative competitor pricing factor  
- `Cost_per_Min` → ride cost normalized by duration  
- `Driver_to_Rider_Ratio` → supply-demand balance  
- `Inventory_Health_Index` → driver stock vs demand  
- `Loyalty_Score` → numeric encoding of loyalty levels  
- `Peak` → indicator for peak demand times (Evening/Night)  
- `Rider_Driver_Ratio` → demand per driver  
- `Supply_Tightness` → shortage intensity × peak indicator  
- `Vehicle_Factor` → vehicle type multiplier  
- `baseline_price` → rule-based minimum fare  
- `competitor_price` → adjusted price using competitor index  
- `p_complete` → probability of ride completion  
- `price` → final dynamic price (weighted mix of baseline, competitor price, and supply tightness)  

### 3. Exploratory Data Analysis (EDA)  
- Distribution of ride costs  
- Riders vs Drivers scatter plot  
- Average price by location and booking time  
- Correlation heatmap for numerical features  

---

## 📊 KPIs Generated  
- Average and median ride price  
- Riders per driver ratio  
- Demand-supply gap insights  

---

## ✅ Next Steps  
- Train ML models (XGBoost / LightGBM) for predicting prices  
- Build a baseline rule-based pricing engine for comparison  
- Deploy via FastAPI + Docker  
- Create React.js dashboard for monitoring KPIs 
