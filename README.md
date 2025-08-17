# Profit-Driven-Fleet-Optimization

This repository contains an end-to-end operations research project focused on optimizing the fleet management strategy for a car rental company. The primary goal is to move beyond simple forecasting and use prescriptive analytics to determine the optimal fleet size and daily vehicle distribution that maximizes weekly profit while adhering to complex operational constraints.
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **📋 Problem Statement**
A car rental company's profitability is directly tied to its ability to manage a complex, dynamic logistics network. The key challenge is to balance vehicle supply with fluctuating demand across multiple depots, accounting for multi-day rentals, vehicle transfers, and a damage-and-repair cycle. This project aims to create a "steady-state" solution that provides a precise, actionable weekly plan, answering two fundamental business questions: How many cars should the company own? and Where should those cars be located each day to maximize profit?

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **📊 Data Summary**
The analysis is based on a set of business parameters for a car rental company with four depots (Glasgow, Manchester, Birmingham, Plymouth) operating six days a week. The key data points include:

Demand Forecasts: Estimated daily rental demand for each depot.

Operational Probabilities: Historical percentages for rental durations (1, 2, or 3 days) and return locations.

Financial Data: A detailed cost and revenue structure, including rental prices, marginal costs, transfer costs, weekly ownership costs, and damaged car fees.

Capacity Constraints: Daily repair capacity limits for the two designated repair depots (Manchester and Birmingham).

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **🛠️ Methodology & Techniques**
To find the provably optimal solution, a Linear Programming (LP) model was formulated and solved. This mathematical optimization approach is ideal for complex resource allocation problems.

Model Formulation: The business problem was translated into a formal mathematical model with three core components:

Decision Variables: Representing key operational quantities like total cars owned (xOwned), cars rented per day (xRented), and vehicles transferred between depots.

Objective Function: A linear equation designed to maximize total weekly profit, calculated as (Total Revenues) - (Total Costs).

Constraints: A series of linear equations that encode the complex business rules, including car flow balancing, demand fulfillment, and repair capacity limits.

Steady-State Logic: A crucial aspect of the model is the "steady-state" assumption, which links the end of one week to the start of the next using modulo arithmetic in the constraints. This ensures the solution is a sustainable, repeatable weekly plan.

Solving: The model was implemented in Python using the Gurobi solver, a high-performance, industry-standard tool for mathematical optimization.

Strategic Analysis: Beyond finding the optimal solution, the project report includes advanced analysis of the model's output:

Bottleneck Analysis: Using shadow prices to identify which constraints (like repair capacity) are the most significant limiting factors on profit.

Sensitivity Analysis: Discussing how the model can be used for "what-if" scenarios to test the impact of changing business parameters like fuel costs or demand forecasts.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **🚀 Tools and Libraries**
This project was built using Python and the following core libraries:

Gurobi (gurobipy): A powerful, commercial-grade solver for building and solving the linear programming model.

Pandas: For organizing and displaying the final solution in a clear, tabular format.

itertools: To assist in creating the combinations of depots and days needed for the model's variables and constraints.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **💡 Inference and Conclusion**
The optimization model produced a clear and actionable operational plan, prescribing an optimal fleet size of 617 cars, which yields a maximum achievable weekly profit of \$121,160.

The key insight is that the model provides a direct, data-driven playbook that replaces guesswork with a provably optimal strategy. The detailed daily inventory schedules for both undamaged and damaged cars ensure that vehicles are proactively positioned to meet demand and generate revenue. Furthermore, the analysis of shadow prices revealed that the repair capacity at the Manchester and Birmingham depots is a significant bottleneck, providing a quantitative justification for potential future investment in expanding those facilities.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

# **Final Conclusion:**
This project successfully demonstrates the power of mathematical optimization to solve a complex, real-world business problem. The model's output is not just an analysis but a direct operational plan that maximizes profit by balancing all revenue drivers and cost constraints simultaneously. By defining the exact fleet size and distribution, it optimizes asset utilization and improves logistical efficiency. The framework is a powerful decision-support tool, enabling management to perform sensitivity analysis and develop robust strategies that can adapt to changing market conditions.
