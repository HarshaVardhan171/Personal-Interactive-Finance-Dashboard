# Personal Finance Dashboard in Excel

## Objective
To design a dynamic, interactive, and visually compelling personal finance dashboard using **Microsoft Excel 2016**  
that tracks income, expenses, and savings trends over time to empower better financial decision-making.

---

## Tools Used
- Microsoft Excel 2016  
- Pivot Tables & Charts  
- Data Validation & Lookup Formulas  
- Conditional Formatting & Shape Styling  

---

## Process Overview

### 1. Data Collection & Import
- Exported transaction data directly from bank statements in CSV format.
- Cleaned and standardized the dataset with columns such as:
  - `Transaction Date`, `Description`, `Debit`, `Credit`, `Amount`, `Payee Details`.

### 2. Data Structuring & Categorization
- Created a **Master Table** for unique payees with assigned Subcategories and Categories  
  _(e.g., `Groceries → Food & Dining → Expense`)_
- Used `VLOOKUP` to auto-fill `Subcategory`, `Category`, and `Payment Type`.

### 3. Payment Mode Identification
- Parsed payment modes (e.g., UPI, Debit Card, NEFT, ATM, Interest Credit)  
  using `SEARCH` and `IF` formulas within the description field.

### 4. Interactive Dashboard Design
- Implemented **Pivot Tables** to summarize:
  - Monthly Spend
  - Income
  - Savings
  - Top Expense Categories
- Used:
  - Custom shapes
  - Color themes (soft purples and gradients)
  - Icons and linked text boxes
  - Dynamic visuals tied to pivot outputs

### 5. Dynamic Data Model
- Transformed raw data into structured **Excel Tables** (`Ctrl+T`)  
  for seamless pivot refresh and one-click updates (e.g., monthly data import).

---

## Key Features

- Automated Categorization of Financial Transactions  
- Spend Year-To-Date Summary Across Major Categories  
- Visual Tracking of Discretionary vs. Essential Expenses  
- Easy Refresh Mechanism for Monthly Updates  

---

## Visual Components

### Doughnut Chart: Total Spend by Account

#### Goal:
Visualize how spending is distributed across payment types.

**Steps:**
1. **Pivot Table:**
   - Rows: `Payment Type`
   - Values: `Sum of Debit`
   - Named: `PTPayTypePie`

2. **Doughnut Chart:**
   - Inserted from "Insert Pie or Doughnut Chart"
   - Customizations:
     - Legend: Bottom
     - Data Labels: Percentages only
     - Doughnut Hole: 50%
     - Title: *"Total Spend by Payment Type"*

3. **Dashboard Placement:**
   - Resized & placed in Dashboard sheet
   - Gradient fill background & rounded corners
   - Centered text box for Total Spend using reference workaround

---

### Dual Column Chart: Monthly Expenses vs Net Income

#### Goal:
Side-by-side comparison of monthly expenses and net income.

**Steps:**

**Pivot Table 1 – Expenses:**
- Grouped by `Month`
- Values: `Sum of Debit`
- Named: `PTMntExpBar`

**Chart 1 – Expenses:**
- Clustered Column Chart
- Customizations:
  - Data labels
  - Axis range: 0 to 230,000
  - Gap width: 50%

**Pivot Table 2 – Net Income:**
- Duplicated PT1, replaced with `Amount`
- Named: `PTMntNetIncBar`

**Chart 2 – Net Income:**
- Clustered Column Chart
- Customizations:
  - Axis range: -150,000 to 0
  - Matched styles and placed below Expenses Chart

---

### Line Chart: Monthly Trend by Expense Category

#### Goal:
Track category-wise expenses over months.

**Steps:**
- Pivot Table: `Date` grouped by month, `Category` in columns  
  - Named: `PTCatExpLine`
- Line Chart:
  - Legend on top (as title)
  - Resized to fit all categories
- Cut to Dashboard, applied consistent formatting

---

### Tree Map Chart: Expense Distribution by Category

#### Goal:
Visualize proportional spending across categories.

**Steps:**
- Pivot Table: `Category` → `Subcategory`, `Sum of Debit`
- Copied as static values for Tree Map insertion
- Chart relinked to original pivot table for dynamic update
- Formatting:
  - Wrapped in rounded shape for consistency

---

### Waterfall Chart: Income to Net Balance Flow

#### Goal:
Visualize income breakdown into savings and expenses.

**Steps:**
- Pivot Table: `Category` vs `Sum of Amount`
  - Named: `PTWaterFall`
- Copied values for chart
- Inserted Waterfall Chart
- Linked labels and marked final column as *Total*
- Styled and placed in Dashboard

---

### Top 5 Categories Table with Conditional Formatting

#### Goal:
Highlight top 5 expense subcategories.

**Steps:**
- Pivot Table filtered for Top 5 by `Sum of Debit`
- Pasted linked values into Dashboard
- Applied:
  - Currency formatting
  - Conditional Formatting → Data Bars (Purple)

---

### Slicers for Interactive Filtering

**Steps:**
- Inserted Slicers:
  - `Category`
  - `Date`
- Customized:
  - Renamed headers
  - Hid empty items
- Aligned on dashboard sides
- Connected to multiple Pivot Tables using **Report Connections**:
  - Tree Map
  - Expense Column Chart
  - Waterfall Chart

---

## Outcome

Built an interactive Excel dashboard to:
- Track personal finances
- Visualize income & expenses
- Analyze savings trends
- Compare actual vs. budgeted spending  
using pivot tables, slicers, and dynamic charts.

---

