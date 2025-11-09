# 🛫Flight Performance Dashboard (Power BI)

## 📖 Project Overview
This Power BI project analyzes **Flight performance** using data on delays, routes, aircraft types, and seasonal trends.  
The dashboard provides actionable insights into operational efficiency, delay patterns, and performance factors across different flight routes and times.

---

## 📊 Dataset Overview
The dataset contains the following key fields:

| Column Name | Description |
|--------------|-------------|
| `Flight_ID` | Unique identifier for each flight |
| `Route` | Origin–Destination combination |
| `Scheduled_Departure_Hours` | Scheduled flight departure time (in hours) |
| `Actual_Departure_Hours` | Actual departure time (in hours) |
| `Delay_Minutes` | Number of minutes a flight was delayed |
| `Aircraft_Type` | Aircraft model used for the flight |
| `Season` | Season of operation (e.g., Summer, Winter) |
| `Reason_for_Delay` | Primary cause of delay (Weather, Technical, Operational, etc.) |
| `Departure_Airport` | Airport where flight departs |
| `Destination_Airport` | Airport where flight arrives |
| `Flight_Date` | Date of the flight |

---

## 📈 Dashboard Visuals

### 1. 🟦 **Card Visuals – KPI Overview**
**Purpose:**  
To provide at-a-glance performance metrics.

**Metrics Displayed:**
- Total Flights Operated  
- Average Delay (Minutes)  
- On-Time Performance (%)  
- Most Frequent Delay Reason  

**Implementation Steps:**
1. Insert **Card visuals** from the Visualizations pane.  
2. Assign relevant measures:
   - `COUNTROWS(Flights)` → Total Flights
   - `AVERAGE(Delay_Minutes)` → Average Delay
   - `CALCULATE(...)` → On-Time % (flights with Delay_Minutes ≤ 15)
3. Apply bold, centered formatting with distinctive background colors for readability.

**Insights:**
KPI cards summarize flight performance and immediately indicate if operational goals are being met.

---

### 2. 📊 **Bar Chart: Average Delay by Route**
**Purpose:**  
Identify which routes experience the highest average delays.

**Implementation Steps:**
1. Insert a **Clustered Column Chart**.  
2. Assign fields:
   - **X-axis:** `Route`
   - **Y-axis:** `Average of Delay_Minutes`
3. Sort values **descending** by `Delay_Minutes` for ranking.
4. Add **data labels** and rename the chart title.

**Insights:**
Highlights underperforming routes and supports resource optimization (e.g., prioritizing on-time improvements on specific routes).

---

### 3. 🍩 **Donut Chart: Distribution of Delay Reasons**
**Purpose:**  
Show the proportion of total delays attributed to each reason.

**Implementation Steps:**
1. Insert a **Donut Chart**.  
2. Assign:
   - **Legend:** `Reason_for_Delay`
   - **Values:** `Count of Reason_for_Delay`
3. Turn **on data labels** for clarity.  
4. Apply distinct colors for each delay type.

**Insights:**
Easily reveals whether delays are mainly due to weather, technical issues, or operational inefficiencies.

---

### 4. 📈 **Line Chart: Trend of Average Delay Over Time**
**Purpose:**  
Display how flight delays change over months or seasons.

**Implementation Steps:**
1. Insert a **Line Chart**.  
2. Assign:
   - **X-axis:** `Flight_Date`
   - **Y-axis:** `Average of Delay_Minutes`
   - Optional: **Legend:** `Season`
3. Format the date axis to monthly or weekly intervals.

**Insights:**
Identifies **temporal trends**, such as increased delays during specific seasons or holiday peaks.

---

### 5. 🗺️ **Map Visual: Flight Route Distribution**
**Purpose:**  
Visualize all departure and destination airports to understand network spread.

**Implementation Steps:**
1. Insert a **Map visual (or Filled Map)**.  
2. Assign:
   - **Location:** `Departure_Airport`
   - **Destination:** `Destination_Airport`
   - **Size:** `Count of Flight_ID`
3. Enable **Zoom controls** and set map theme to “Aerial.”

**Insights:**
Shows key flight hubs, busiest routes, and geographical distribution of operations.

---

### 6. 🔵 **Scatter Chart: Relationship Between Scheduled and Actual Departure**
**Purpose:**  
Analyze the relationship between **scheduled departure times** and **actual departure times**, highlighting how delays vary across different flight routes.

**Implementation Steps in Power BI:**
1. Insert a **Scatter Chart** visual.  
2. Assign the following fields:
   - **X-axis:** `Scheduled_Departure_Hours`
   - **Y-axis:** `Actual_Departure_Hours`
   - **Size:** `Delay_Minutes`
   - **Legend:** `Route`
   - **Details:** `Flight_ID`
3. Format both axes as **numeric hours (0–24)** or **time format**.
4. Add **tooltips** to show detailed flight information.
5. Use distinct color coding per route.

**Insights:**
- Identifies clusters of late departures.
- Large bubbles indicate flights with longer delays.
- The diagonal (where X = Y) shows on-time flights — points above represent late departures.

---

## 🎛️ Slicers and Interactivity

**Slicers Implemented:**
- `Season`
- `Aircraft_Type`
- `Route`
- `Reason_for_Delay`

**Purpose:**
Allow users to **filter all visuals dynamically** and explore performance patterns under different conditions (e.g., seasonal trends, aircraft efficiency).

**Implementation Steps:**
1. Insert **Slicer visuals**.
2. Assign the respective fields.
3. Change slicer orientation to **dropdown** for compactness.
4. Ensure each slicer affects **all visuals** (via “Edit Interactions”).

---

## 🧠 Key Insights from the Dashboard
- Certain routes consistently experience **higher delays**, likely due to operational constraints.
- **Technical and weather-related issues** are leading causes of delays.
- **Peak travel seasons** correspond with increased delay averages.
- Visuals enable **management and decision-makers** to pinpoint problem areas and improve scheduling.

---

## 💡 Conclusion
This Power BI dashboard provides a **comprehensive view of Kenya Airways' flight performance**, allowing data-driven decisions for improved operational efficiency.  
It demonstrates the use of **interactive slicers**, **multiple visualization types**, and **clean KPI summaries** for professional airline performance analysis.

---

## 🧰 Tools and Technologies
- **Power BI Desktop**
- **Microsoft Excel** (for data cleaning)
- **DAX (Data Analysis Expressions)**
- **Data Visualization and Storytelling principles**

---

## 👩‍💻 Author
**Joey Gichure**  
Data Analyst | Power BI Developer  
📊 Passionate about turning data into meaningful insights.

