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
    DECLARE String category_choice = ""
    DECLARE Real amount = 0.0

