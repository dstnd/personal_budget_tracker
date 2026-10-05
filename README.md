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

```
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

    WHILE main_choice != "4"

        DISPLAY ""
        DISPLAY "--- MAIN MENU ---"
        DISPLAY "1. Log Income"
        DISPLAY "2. Log Expense"
        DISPLAY "3. View Financial Summary"
        DISPLAY "4. Exit"
        DISPLAY "Enter your choice (1-4):"
        INPUT main_choice

        WHILE main_choice != "1" AND main_choice != "2" AND
              main_choice != "3" AND main_choice != "4"

            DISPLAY "Invalid. Choice must be 1, 2, 3, or 4. Try Again:"
            INPUT main_choice

        END WHILE


        IF main_choice = "1" THEN

            DISPLAY ""
            DISPLAY "--- INCOME MENU ---"
            DISPLAY "1. Design"
            DISPLAY "2. Coding"
            DISPLAY "3. User Documentation"
            DISPLAY "Enter income category:"
            INPUT sub_choice

            WHILE sub_choice != "1" AND sub_choice != "2" AND
                  sub_choice != "3"

                DISPLAY "Invalid. Please enter 1, 2, or 3. Try Again!"
                INPUT sub_choice

            END WHILE

            DISPLAY "Enter income amount ($):"
            INPUT amount

            WHILE amount < 0

                DISPLAY "Invalid. Please enter amount >= 0:"
                INPUT amount

            END WHILE

            IF sub_choice = "1" THEN
                design_income = design_income + amount
                DISPLAY "Successfully added $", amount, " for Design."

            ELSE IF sub_choice = "2" THEN
                coding_income = coding_income + amount
                DISPLAY "Successfully added $", amount, " for Coding."

            ELSE
                documentation_income = documentation_income + amount
                DISPLAY "Successfully added $", amount, " for User Documentation."

            END IF


        ELSE IF main_choice = "2" THEN

            DISPLAY ""
            DISPLAY "--- EXPENSE MENU ---"
            DISPLAY "1. Software"
            DISPLAY "2. Equipment"
            DISPLAY "3. Workspace"
            DISPLAY "Enter expense category:"
            INPUT sub_choice

            WHILE sub_choice != "1" AND sub_choice != "2" AND
                  sub_choice != "3"

                DISPLAY "Invalid. Please enter 1, 2, or 3. Try Again!"
                INPUT sub_choice

            END WHILE

            DISPLAY "Enter expense amount ($):"
            INPUT amount

            WHILE amount < 0

                DISPLAY "Invalid. Please enter amount >= 0:"
                INPUT amount

            END WHILE

            IF sub_choice = "1" THEN
                software_expense = software_expense + amount
                DISPLAY "Successfully added $", amount, " for Software."

            ELSE IF sub_choice = "2" THEN
                equipment_expense = equipment_expense + amount
                DISPLAY "Successfully added $", amount, " for Equipment."

            ELSE
                workspace_expense = workspace_expense + amount
                DISPLAY "Successfully added $", amount, " for Workspace."

            END IF


        ELSE IF main_choice = "3" THEN

            total_income = design_income + coding_income + documentation_income

            total_expenses = software_expense + equipment_expense + workspace_expense

            net_balance = total_income - total_expenses

            DISPLAY ""
            DISPLAY "=========================================="
            DISPLAY "          FINANCIAL SUMMARY"
            DISPLAY "=========================================="
            DISPLAY "Total Income:   $", total_income
            DISPLAY "Total Expenses: $", total_expenses
            DISPLAY "Net Balance:    $", net_balance

            IF net_balance > 0 THEN

                DISPLAY "Status: You are profitable this month!"

            ELSE IF net_balance < 0 THEN

                DISPLAY "Status: You had a loss this month."

            ELSE

                DISPLAY "Status: You broke even this month."

            END IF

            DISPLAY "=========================================="


        ELSE IF main_choice = "4" THEN

            DISPLAY ""
            DISPLAY "Thank you for using Personal Budget Tracker. Goodbye!"

        END IF

    END WHILE

END MODULE
