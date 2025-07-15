# OPTIMIZATION-MODEL

# 🧃 Juice Factory Product Mix Optimization using PuLP

This project solves a real-world product mix optimization problem for a juice factory using **Linear Programming (LP)** with Python's **PuLP** library.

---

## 🎯 Objective

Maximize total profit by deciding how many units of each juice to produce (Apple, Orange, Mixed Fruit), subject to constraints on:

- Machine time
- Labor time
- Maximum producible units

---

## 📁 Input Data

Input is read from an Excel file: `juice_data.xlsx`

| Product            | Profit (₹/unit) | Machine Time (hrs) | Labor Time (hrs) | Max Units |
|--------------------|------------------|----------------------|-------------------|-----------|
| Apple Juice         | 25               | 3                    | 2                 | 60        |
| Orange Juice        | 30               | 2                    | 3                 | 60        |
| Mixed Fruit Juice   | 40               | 4                    | 4                 | 60        |

---

## 🧠 What This Project Does

1. **Loads Data**  
   - Reads the Excel file into a pandas DataFrame.

2. **Defines LP Model**  
   - Creates a `LpProblem` with `LpMaximize` objective.

3. **Defines Decision Variables**  
   - One variable per juice product (e.g., `Apple_Juice`, `Orange_Juice`).

4. **Objective Function**  
   - Maximize profit:  
     `Z = 25 * A + 30 * O + 40 * M`

5. **Constraints**
   - `3A + 2O + 4M <= 240` (Machine time constraint)
   - `2A + 3O + 4M <= 220` (Labor time constraint)
   - `A, O, M <= 60` (Production limits)

6. **Solves the Model**  
   - Finds the optimal values using PuLP's solver.

7. **Displays the Output**
   - Shows optimal units of each juice and total profit.

8. **Visualization**
   - Bar chart using `matplotlib` for optimal juice mix.

9. **Sensitivity Analysis**
   - Re-runs model with increased machine time (+20 hours) and compares profit change.

---

## ✅ Sample Output

```python
{'Apple Juice': 56.0,
 'Orange Juice': 36.0,
 'Mixed Fruit Juice': 0.0,
 'Total Profit': 2480.0}
