# Used Car Price Prediction & Inventory Optimization

## Executive Summary
After analyzing a dataset of **426,000** vehicle listings, we have developed a machine learning framework to identify the primary drivers of vehicle resale value. 
Our most accurate model achieves a **~70% accuracy** rate, allowing us to predict fair market value with an average margin of error of approximately **\$4,100**.

## Data Overview
**Total Observations:** 426,880 listings.
**Features Analyzed:** 18 distinct variables including price, year, manufacturer, model, condition, fuel, odometer, and title status.
**Temporal Range:** Vehicles ranging from vintage collectibles (1920s) to late-model year 2023-2024 units.

### Data Preparation & Modeling Workflow
We utilized a robust Scikit-Learn Pipeline to ensure data integrity and prevent leakage:

* **Cleaning:** Handled missing values via SimpleImputer (Median strategy). To ensure data integrity, the dataset underwent a rigorous cleaning process where we isolated significant variables by removing duplicates and outliers. Our final analysis focused exclusively on vehicles within a price bracket of $500 to $150,000. 

* **Feature Engineering:** Created car_age from year data to better reflect depreciation. 

* **Encoding:** Used TargetEncoder for high-cardinality features (Region/Model) and OneHotEncoder for mechanical specs.

* **Transformation:** Integrated a TransformedTargetRegressor to handle Log-Scale math automatically.

## Critical Depreciation Factors
We have isolated the variables that most significantly reduce a vehicle's market price, providing a baseline for more competitive procurement.
- **Age Impact:** The most critical factor; depreciation follows a non-linear path with the sharpest decline occurring in the initial 3 to 5 years.
- **Mileage Milestones:** While loss of value is constant, a major price drop is observed once a vehicle crosses 100,000 miles.
- **Brand Strength:** High-end brands like Porsche and Lexus retain significantly more value (15–20% higher) than entry-level manufacturers at comparable mileage.


## Model Performance & Reliability
Our **Random Forest** modeling approach proved best for integrated pricing tools, maintaining a stable 70% accuracy with a standard $4,100 margin.
Residual tests show errors are distributed normally, meaning our pricing remains consistent and unbiased across all inventory classes, from budget to luxury.

## Tactical Recommendations for Inventory Tuning
We suggest the following updates to our current buying strategies based on the data:
1. **Target the High-Demand Window:** Focus acquisitions on vehicles that are **4–6 years old** and have **less than 80,000 miles**.
2. **Unified Pricing Systems:** Deploy the **Log-Price Pipeline** to standardize trade-in valuations across all sales locations.
3. **Avoid Regional Mismatches:** Be cautious of low-demand features in specific regions, such as diesel engines in urban centers, to prevent stale inventory.

## Summation and Forward Planning
This model serves as a financial **safeguard**, utilizing a **Log-Transformed** structure to mitigate the risk of price outliers. **Next Phase:** We can proceed with a **"What-If" Scenario** to calculate potential profit gains from further error reduction.

## Setup and Installation

### Project Structure
* `data/vehicles.csv`: The raw dataset containing all car info.
* `car_price_depreciation.ipynb`: A comprehensive Jupyter Notebook containing data cleaning, exploratory data analysis (EDA), and modeling.

### Prerequisites
You will need Python 3.x and the following libraries:
* `pandas`
* `seaborn`
* `matplotlib`
* `plotly`
* `sklearn`

### Running the Analysis
1. Clone the repository:
   `git clone https://github.com/tnralakus/used-car-price-depreciation.git`
2. Navigate to the directory and launch Jupyter:
   `jupyter notebook car_price_depreciation.ipynb`
