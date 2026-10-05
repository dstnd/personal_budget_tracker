# personal_budget_tracker
Project 1: Personal Buget Tracker

**Course:** ITP 100 Software Design & Logic

**Author:** Destinee McGee

**Deliverable:** IPO Chart, Pseudocode, and Flowchart

## 1. Problem Description & Scope
* **Problem:** The Personal Budget Tracker is a console-based program design that allows a user to record income and expenses in different categories. The program validates menu selections and monetary amounts, keeps running totals for each category, and displays a financial summary showing total income, total expenses, net balance, and whether the user made a profit, had a loss, or broke even.
* **Scope:**

  • Features a continuous main loop with two hierarchical submenus (Income and Expense).

  • Validates menu selections by rejecting values outside the available menu options.

  • Validates monetary amounts by rejecting negative numbers.

  • Tracks income in three categories: Design, Coding, and User Documentation.

  • Tracks expenses in three categories: Software, Equipment, and Workspace.

  • Stores and updates category totals in memory during program execution.

  • Calculates total income, total expenses, and net balance when the user requests a financial summary.

  • Determines whether the user is profitable, has a loss, or breaks even for the month.

  • Terminates cleanly when the user selects the Exit option.

## 2. IPO Chart (Input - Process - Output)
| Input | Processing | Output |
| :--- | :--- | :--- |
| • `main_choice` (String: 1–4)<br>• `sub_choice` (String: 1–3)<br>• `amount` (Real: ≥ 0) | 1. Initialize all income and expense category totals to `0.0`.<br>2. Loop the main menu until the user enters `4`.<br>3. Validate that `main_choice` is between 1 and 4.<br>4. If `1` (Log Income):<br>&emsp;a. Display the Income submenu.<br>&emsp;b. Validate `sub_choice` is between 1 and 3.<br>&emsp;c. Prompt for income amount; loop until `amount >= 0`.<br>&emsp;d. Map the choice to Design, Coding, or User Documentation.<br>&emsp;e. Add `amount` to the selected income category.<br>5. If `2` (Log Expense):<br>&emsp;a. Display the Expense submenu.<br>&emsp;b. Validate `sub_choice` is between 1 and 3.<br>&emsp;c. Prompt for expense amount; loop until `amount >= 0`.<br>&emsp;d. Map the choice to Software, Equipment, or Workspace.<br>&emsp;e. Add `amount` to the selected expense category.<br>6. If `3` (Financial Summary):<br>&emsp;a. Calculate `total_income`.<br>&emsp;b. Calculate `total_expenses`.<br>&emsp;c. Calculate `net_balance = total_income - total_expenses`.<br>&emsp;d. Determine whether the user has a profit, loss, or breaks even.<br>&emsp;e. Display the financial summary.<br>7. If `4` (Exit): Display farewell message and terminate. | • Invalid input warning messages<br>• Success confirmation showing the amount and category<br>• Formatted Financial Summary:<br>&emsp;- Total Income<br>&emsp;- Total Expenses<br>&emsp;- Net Balance<br>&emsp;- Profit/Loss/Break-Even Status<br>• Exit farewell message |

---

## 3. Pseudocode

MODULE Main()
    DECLARE Real design_income = 0.0
    DECLARE Real coding_income = 0.0
    DECLARE Real documentation_income = 0.0

    DECLARE Real software_expense = 0.0
    DECLARE Real equipment_expense = 0.0
    DECLARE Real workspace_expense = 0.0

    DECLARE Real total_income = 0.0
    DECLARE Real total_expenses = 0.0
    DECLARE Real net_balance = 0.0

    DECLARE String main_choice = ""
    DECLARE String sub_choice = ""
    DECLARE Real amount = 0.0

    DISPLAY "=========================================="
    DISPLAY "          PERSONAL BUDGET TRACKER         "
    DISPLAY "=========================================="
