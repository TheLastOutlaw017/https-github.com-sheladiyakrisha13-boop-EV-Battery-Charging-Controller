# EV-Battery-Charging-Controller
A MATLAB-based EV Battery Charging Controller using a Mamdani Fuzzy Inference System. It considers SOC, battery temperature, temperature rise rate, cell voltage difference, and ambient temperature to recommend adaptive charging current. It enables smoother, smarter, and more context-aware charging decisions than traditional threshold-based control.
EV Battery Charging Controller Using Fuzzy Logic

Adaptive Charging Current Control Using a Mamdani Fuzzy Inference System

📌 Project Overview

Electric vehicles (EVs) are becoming an important part of sustainable transportation, making efficient and reliable battery charging an essential area of research. Charging current should be adjusted according to the battery's condition rather than relying only on a single parameter.

This project presents a MATLAB-based EV Battery Charging Controller using a Mamdani Type-1 Fuzzy Inference System. It considers five battery and environmental parameters to recommend an appropriate charging current under different operating conditions.

The main idea is to replace rigid, threshold-based decisions with a more flexible approach that considers multiple conditions simultaneously.

🎯 Objectives

- Develop a fuzzy logic-based EV battery charging controller in MATLAB.
- Consider multiple battery and environmental parameters when recommending charging current.
- Design membership functions for input and output variables.
- Implement fuzzy IF–THEN rules using Mamdani inference.
- Apply centroid defuzzification to obtain a crisp charging-current value.
- Compare fuzzy control with conventional threshold-based control.

⚙️ System Architecture

The controller accepts five inputs and produces one output.

Input Parameters

Parameter| Range| Purpose
State of Charge (SOC)| 0–100%| Represents the battery's charge level
Battery Temperature| 15–60°C| Indicates the battery's thermal condition
Temperature Rise Rate| 0–2°C/min| Represents how quickly the battery temperature increases
Cell Voltage Difference| 0–100 mV| Indicates voltage imbalance between cells
Ambient Temperature| 10–45°C| Represents surrounding temperature conditions

Output Parameter

Recommended Charging Current: 0–20 A

The controller recommends higher current under suitable conditions and progressively reduces it when battery or environmental stress increases.

🧠 Why Fuzzy Logic?

Traditional threshold-based controllers make decisions using predefined limits. They may not adequately account for several battery stress conditions occurring simultaneously.

Fuzzy logic provides a flexible alternative by representing input values through degrees of membership rather than treating every condition as simply ON or OFF.

This allows the controller to consider overlapping conditions and produce gradual charging-current recommendations.

🔬 Membership Functions

Membership functions convert numerical input values into fuzzy membership degrees between 0 and 1.

The project uses the following fuzzy sets:

Variable| Fuzzy Sets
SOC| Low, Medium, High
Battery Temperature| Low, Normal, High
Temperature Rise Rate| Slow, Moderate, Fast
Cell Voltage Difference| Small, Medium, Large
Ambient Temperature| Low, Normal, High
Charging Current| Very Low, Low, Medium, High, Very High

Overlapping membership functions help represent gradual transitions between operating conditions.

🔄 Working Principle

The controller follows these steps:

1. Input Collection

Five numerical values representing battery and environmental conditions are supplied to the system.

2. Fuzzification

Each input is converted into membership degrees using its corresponding membership functions.

3. Rule Evaluation

The controller evaluates a set of 12 fuzzy IF–THEN rules to determine the appropriate charging-current level.

4. Mamdani Inference

The fuzzy rules are processed using MIN and MAX operations to determine their contributions to the output.

5. Aggregation

The outputs of the activated rules are combined using the MAX aggregation method.

6. Defuzzification

The centroid method converts the aggregated fuzzy output into a single numerical charging-current recommendation.

📋 Fuzzy Rule Base

The controller uses 12 fuzzy IF–THEN rules to evaluate different operating conditions.

Examples include:

- Rule 1: IF SOC is Low AND Battery Temperature is Normal AND Temperature Rise Rate is Slow AND Cell Voltage Difference is Small, THEN Charging Current is Very High.
- Rule 2: IF SOC is Low AND Battery Temperature is High, THEN Charging Current is Low.
- Rule 3: IF SOC is Low AND Temperature Rise Rate is Fast, THEN Charging Current is Low.
- Rule 4: IF SOC is Medium AND Battery Temperature is Normal AND Temperature Rise Rate is Slow AND Cell Voltage Difference is Small, THEN Charging Current is High.
- Rule 7: IF SOC is High AND Battery Temperature is High, THEN Charging Current is Very Low.
- Rule 8: IF Cell Voltage Difference is Large, THEN Charging Current is Very Low.

The remaining rules address additional conditions, including high ambient temperature, rapid temperature rise, and combinations of battery stress factors.

These rules allow the controller to respond to different operating conditions rather than depending on SOC alone.

💻 MATLAB Implementation

The controller is implemented using a Mamdani Type-1 Fuzzy Inference System.

Configuration

Setting| Value
FIS Type| Mamdani Type-1
Number of Inputs| 5
Number of Outputs| 1
Number of Rules| 12
AND Method| MIN
OR Method| MAX
Implication| MIN
Aggregation| MAX
Defuzzification| Centroid

The MATLAB implementation demonstrates the complete fuzzy-logic decision-making process, from numerical inputs to the final charging-current recommendation.

📊 Sample Simulation

The project presentation includes the following test case:

Input Parameter| Value
SOC| 30%
Battery Temperature| 32°C
Temperature Rise Rate| 0.3°C/min
Cell Voltage Difference| 15 mV
Ambient Temperature| 28°C
Recommended Charging Current| 16.67 A

This example demonstrates how the fuzzy inference system processes multiple input parameters to generate a charging-current recommendation.

The result depends on the defined membership functions and fuzzy rule base.

📈 Results and Observations

The MATLAB simulation demonstrates that the recommended charging current changes according to battery and environmental conditions.

Key observations include:

- Charging current is reduced as SOC increases.
- High battery temperature can lead to a lower recommended current.
- Rapid temperature rise can trigger a reduction in charging current.
- Significant cell voltage differences result in more conservative charging recommendations.
- Multiple input parameters can be considered simultaneously.

The results illustrate how fuzzy logic can provide smoother and more context-aware control decisions than a rigid threshold-based approach.

⚖️ Fuzzy Control vs Threshold Control

Fuzzy Controller| Threshold Controller
Considers multiple inputs simultaneously| Relies on fixed decision boundaries
Provides gradual charging-current changes| May produce abrupt changes
Considers thermal and electrical stress| May overlook simultaneous stress factors
Handles overlapping operating conditions| Offers less flexibility for intermediate conditions
Produces adaptive current recommendations| May be overly aggressive or conservative near thresholds

🛠️ Technologies Used

- MATLAB
- Fuzzy Logic Toolbox
- Mamdani Fuzzy Inference System
- Fuzzy Membership Functions
- Centroid Defuzzification

📚 Learning Outcomes

Through this project, we explored the practical application of fuzzy logic in electrical engineering and intelligent control systems.

The project helped us understand:

- The difference between crisp and fuzzy sets.
- Membership-function design and fuzzification.
- Fuzzy IF–THEN rule development.
- Mamdani inference and MIN/MAX operations.
- Rule aggregation and centroid defuzzification.
- MATLAB-based simulation and evaluation of control systems.

🚀 Future Scope

The project can be extended through:

- Testing with more comprehensive battery operating scenarios.
- Refining membership functions and fuzzy rules.
- Comparing performance against additional control strategies.
- Integrating real-time battery sensor measurements.
- Exploring hardware implementation and experimental validation.
- Incorporating battery-specific charging limits and protection mechanisms.

These extensions would require further development and validation before practical deployment.

⚠️ Limitations

This is an academic, simulation-based project. The controller generates recommended charging-current values; it does not directly control a physical EV battery.

The simulation results do not establish battery safety, improved battery life, or real-world charging performance. Practical implementation would require battery-specific limits, validated control logic, appropriate protection mechanisms, and experimental testing.

👥 Project Team

Developed as part of the Fuzzy Logic and Genetic Programming course.

Department: Electrical Engineering
Institute: L. D. College of Engineering, Ahmedabad

- Dev Chauhan
- Sanjana Patel
- Manan Vaiwala
- Krisa Sheladiya

🏁 Conclusion

This project demonstrates how fuzzy logic can be applied to EV battery charging-current recommendations by considering multiple battery and environmental parameters simultaneously.

Using a Mamdani Type-1 Fuzzy Inference System, 12 fuzzy rules, and centroid defuzzification, the MATLAB implementation produces adaptive charging-current recommendations for different operating conditions.

The project provides practical experience in intelligent control, fuzzy-system design, and MATLAB simulation while offering a foundation for further research into adaptive EV battery charging.
