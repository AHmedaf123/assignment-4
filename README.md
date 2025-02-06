# 📊 Automated Data Processing & Visualization Pipeline  

This project consists of two main scripts:  
1️⃣ Data Processing Pipeline (`raw_to_gold.py`) → Extracts, cleans, processes data, and saves it into structured Excel files.  
2️⃣ Dash Web App (`analysis.py`) → Visualizes the processed data with interactive graphs and filters.  

---

🔹 Overview of Both Scripts

1️⃣ Data Processing Pipeline (`raw_to_gold.py`)
📌 What It Does
- Reads raw Excel data from multiple modules (`TSR`, `LostCargo`, `Blockage`, `FOG`, `RoadCondition`).
    - Filters, cleans, and formats the data :
    - Removes missing values.
    - Extracts date & time.
    - Maps user IDs to names.
    - Converts milliseconds to minutes.
    - Saves structured Gold & Analysis Excel files.
    - Tracks processed files (so they are not reprocessed).
    - Handles errors and logs issues (e.g., missing files, invalid formats).

📊 Output Files
- 📁 Gold File → `./Module/Gold/Module_Gold.xlsx`  
- 📁 Analysis File → `./Module/Analysis/Module_Analysis.xlsx`  
- 📁 Status File → `./Module/Module-status.xlsx` (Tracks processed files)  

📌 Key Features
- Automated data extraction & transformation  
- Error handling & logging  
- Prevents reprocessing old files  
- Supports multiple modules dynamically  

2️⃣ Dash Web App (`analysis.py`)
📌 What It Does
- Loads the processed Analysis Excel files from multiple modules.
    - Creates an interactive web dashboard using `Dash` & `Plotly`.
    - Users can filter data dynamically:
        - Select modules, years, weeks, dates, and users.
    - Generates multiple graphs

📌 How It Works
1. Loads Excel files → Merges all modules into `combined_data`.
2. Creates dropdown filters → Year, week, module, date, user.
3. Uses callbacks to update graphs when a filter is changed.
4. Displays interactive graphs with trends & insights.

#### 📌 Key Features
✅ Interactive data visualization  
✅ Filters to drill down insights  
✅ Real-time updates using callbacks  
✅ Multiple performance & task metrics  

## **📥 Installation**
To install the required dependencies, run:
```bash
pip install -r requirements.txt
```

⚙️ Running the Data Processing Pipeline
Run the data processing script to generate structured data:

```bash
python raw_to_gold.py
```
📌 Expected Output
- The script will process raw Excel files and generate Gold & Analysis files.
- Logs will be displayed, indicating successful processing or errors (e.g., missing files).
- If no new files are found, it will skip processing.

🚀 Running the Dash Web App
Once the data processing is complete, run the interactive dashboard:

```bash
python analysis.py
```
📌 Expected Output
A web server will start at:
```nginx
Running at http://127.0.0.1:8050/
```
Open - http://127.0.0.1:8050 - in your browser to view the dashboard.
You will see interactive graphs:
📊 Number of Users Over Time
⏳ Task Durations
👤 User-Specific Statistics
📈 Performance Metrics
You can use dropdown filters to:
Select specific modules.
Choose a year, week, or date range.
View data by user.
🔹 Example Dashboard Screenshot
