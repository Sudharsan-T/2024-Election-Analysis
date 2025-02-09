# **Election Analysis Dashboard**

### **Dashboard Link**: [Insert Power BI Link]

## **Problem Statement**

This dashboard provides a comprehensive analysis of the **2024 Indian General Election** results. It helps users explore election trends, party performance, and voter dynamics at national, state, and constituency levels. By using interactive visualizations, the dashboard allows users to:

- Understand **party-wise seat distribution**.
- Analyze **state-level** and **constituency-level** election outcomes.
- Compare the performance of **NDA vs. I.N.D.I.A. alliances**.
- Identify **key winning candidates and their vote margins**.

Since the NDA alliance secured a **majority** with **292 seats (54%)**, while the I.N.D.I.A. alliance secured **234 seats (43%)**, political strategists can evaluate their electoral performance and refine future strategies accordingly.

### **Steps Followed**

- **Step 1**: Load election results data into Power BI Desktop (Dataset: CSV file).
- **Step 2**: Open Power Query Editor & enable **column distribution, column quality, and column profile** in the View tab.
- **Step 3**: Change **column profiling to analyze the entire dataset**.
- **Step 4**: Ensure **no missing values** except for a few constituencies where vote margin data was unavailable.
- **Step 5**: Null values in **vote margin calculations** were ignored as they were minimal.
- **Step 6**: Selected a theme in the **Report View** for better visual aesthetics.
- **Step 7**: Added a **bar chart** to represent **total seats won** by each party/alliance.
- **Step 8**: Included **Slicers** for filtering based on **State, Party, Candidate, and Vote Margin**.
- **Step 9**: Created two **card visuals** to display **total seats won by NDA and I.N.D.I.A. alliances**.
- **Step 10**: Used a **stacked bar chart** to compare **state-wise seat distribution**.
- **Step 11**: Implemented **tooltips** to display additional details such as **winning candidate and total votes** upon hovering over a state.
- **Step 12**: Inserted text boxes to display **Election Year (2024)** and **Major Alliances**.
- **Step 13**: Used the **Shapes** and **Image** options to add the **Election Commission Logo** to the report.
- **Step 14**: Created a **calculated column** to categorize constituencies based on winning margin:

  ```DAX
  Winning Margin Category =
      IF(election_data[Winning Margin] < 5000, "Close Contest",
      IF(election_data[Winning Margin] < 25000, "Moderate Win",
      "Landslide Win"))
  ```

- **Step 15**: Created a **measure** to count total constituencies:
  
  ```DAX
  Total Constituencies = COUNT(election_data[Constituency])
  ```
  
- **Step 16**: Created a **measure** for percentage of seats won by NDA:
  
  ```DAX
  % NDA Seats = (DIVIDE(election_data[NDA Seats], 543) * 100)
  ```
  
- **Step 17**: Created a **measure** for percentage of seats won by I.N.D.I.A.:
  
  ```DAX
  % INDIA Alliance Seats = (DIVIDE(election_data[INDIA Alliance Seats], 543) * 100)
  ```
  
- **Step 18**: The report was **published to Power BI Service**.

# **Snapshot of Dashboard (Power BI Service)**

![Insert Dashboard Screenshot]

# **Insights**

A multi-page report was created on Power BI Desktop and then published to Power BI Service.

### **[1] National-Level Seat Distribution**

- **Total Seats**: 543
- **NDA Alliance**: **292 seats (54%)**
- **I.N.D.I.A. Alliance**: **234 seats (43%)**
- **Other Parties**: **17 seats (3%)**

### **[2] Party-Wise Breakdown**

#### **NDA Alliance**:
- BJP: **240 seats**
- TDP: **16 seats**
- JD(U): **12 seats**
- Others: **24 seats**

#### **I.N.D.I.A. Alliance**:
- INC: **99 seats**
- SP: **37 seats**
- AITC: **29 seats**
- Others: **69 seats**

### **[3] State-Level Analysis**

- **Largest NDA Victory**: [Insert State Name] (Highest NDA seats)
- **Largest I.N.D.I.A. Victory**: [Insert State Name] (Highest I.N.D.I.A. seats)
- **State with Closest Contest**: [Insert State Name] (Lowest winning margin)

### **[4] Constituency-Level Insights**

#### **Example: Kolhapur, Maharashtra**
- **Winner**: INC (Sanjay Sadashivrao)
- **Winning Vote Share**: **54.15%**
- **Runner-Up**: Shiv Sena (43.03%)
- **Total Votes Cast**: **1,393,326**
- **Vote Margin**: **139,332 votes**

### **[5] Winning Margin Categories**

- **Close Contests (<5,000 votes)**: **X% constituencies**
- **Moderate Wins (5,000-25,000 votes)**: **Y% constituencies**
- **Landslide Wins (>25,000 votes)**: **Z% constituencies**

### **[6] Key Takeaways**

- **NDA secured a majority** but with competitive margins in key states.
- **I.N.D.I.A. alliance performed strongly in urban and southern regions.**
- **Several constituencies were decided by narrow margins, indicating strong electoral competition.**
- **State-wise trends show BJP dominance in northern states, while I.N.D.I.A. led in the south and east.**

# **Conclusion**

This Power BI dashboard provides a **comprehensive and interactive** analysis of the **2024 Indian General Elections**, allowing users to explore election outcomes at multiple levels. The insights gained can help political analysts, media, and policymakers **understand voting patterns, party strengths, and regional preferences**.

**Published by**: [Your Name]  
**Date**: [Insert Date]

