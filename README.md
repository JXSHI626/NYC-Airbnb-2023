# 🏙️ Case Study: NYC Airbnb 2023
*Eploring pricing patterns, owner strategies, and supply-demand dynamics using tidyverse*
## 📌 Project Overview
This project analyzes the New York City Airbnb 2023 public dataset (from Kaggle) to uncover insights from multiple perspectives: owners, Airbnb platform, and city hosuing management.

The analysis follows a full data analytics workflow:  
* **Business Understanding**  
* **Data Structure Understanding**  
* **Data Cleaning**  
* **Exploratory Data Analysis (EDA)**  
* **Visualization**  
* **Key Insights & Business Recommendations**

All work is implemented in R Markdown, with tidyverse as the primary toolkit.

## 🧰 Tools & Packages
* **R tidyverse**: dplyr, ggplot2, tidyr, stringr  
* **lubridate**: date format conversion  
* **knitr/rmarkdown**: reproducible reporting

## 🔎 Key Business Questions
This project address three perspectives:
### ✔ Owner Perspective
* Which neighbourhoods are more profitable?
* How does room type relate to pricing?
* Doew review frequency refelct occupancy demand?
### ✔ Airbnb Perspective
* Are there supply shortages in certian areas?
* How concentrated is the owner market?
* What factors drive listing competitiveness?
### ✔ City Perspective
* Where is housing density highest?
* Which regions have the strongest short-term rental activity?

## 🧹 Data Cleaning
Major cleaning steps (tidyverse):

* Remove invalid or unrealistic prices  
* Replace 0 price using median by neighbourhood group  
* Filter *minimum_nights* outliers using IQR method
* Clean *reviews_per_month* with NA handling
* Parse *last_review* into date format
* Remove duplicate records
* Drop useless *license* column

Final cleaned dataset: ~41k valid listing properties

## 📊 EDA & Visualization
### 🗺️ 1. Geographic Distribution
Manhattan and Brooklyn dominate supply and pricing, showing strong demand concentration.

### 💵 2. Price Structure
Pricing is jointly shaped by:  
* **Location**: Manhattan most expensive
* **Room Type**: Hotel > Entire home / Apartment > Private > Shared

### 👤 3. Host Market Structure
NYC Airbnb is a fragmented market with a clear "long-tail" characteristic.  
* **82%** owners possess only 1 property
* **<1%** are multi-property (100+) owners that might be "hotel-like" operators

### ⭐ 4. Reviews & Popularity
Reviews per month is highly right skewed, which means that few listing properties dominate more renter attention, consistent with platform popularity loops.

### 🏘️ 5. Supply-Demand via Availability
* Some neighbourhoods show low availability, implying high demand.
* Zero-availability listing properties may reflect calendar blocking due to NYC regulations.

## 📈 Key Insights Summary
### 🔍 Market Structure
NYC Airbnb diplays highly concentrated demand but highly fragmented supply, resulting in intensive competition in core regions (Manhattan, Williamsburg, Bedford-Stuyvesant).

### 🔍 Pricing Drivers
Price is not random distributed. It is affected by three dimensions:  
*Location × Room Type × Owner Class*

### 🔍 Regulatory Impact
Availability partly reflect policy restrictions and calendar closures, not only booking demand.

## 📝 Deliverables
* **Case_Airbnb_nyc2023.rmd**: Full analysis with code
* **Case_Airbnb_nyc2023.pdf**: Final report with EDA & visualizations

## 🚀 How to Reproduce
```{r}
# install required packages
install.packages(c("knitr", "readr", "skimr", "here", "tidyverse", "leaflet", "maps", "scales"))

# knit report
rmarkdown::render("../Case_Airbnb_nyc2023.Rmd")
```

## 📬 Contact
If you'd like to discuss the analysis or collaborate on data projects, feel free to reach out!
