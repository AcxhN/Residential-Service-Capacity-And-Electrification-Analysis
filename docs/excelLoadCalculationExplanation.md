# Excel_Load_Calculation_Explanation.md

## Project Purpose

This `.xlsx` file represents the engineering logic that answers:

“What is the electrical demand (in amps) of a typical house before and after electrification?”

We are converting the electrical demand of loads (in Watts) into an equivalent current (in amps), and comparing that to a 100 A electrical service

According to the Canadian Electrical Code, we are not supposed to simply add up all connected load. We must apply demand factors to reflect realistic usage

---

# How the Calculations Work

---

## Part 1 – Determine the Connected Load

| Category                 | Example              | Basis                        |
|--------------------------|----------------------|------------------------------|
| Lighting                 | 2400 sq ft × 3 W/ft² | Home Depot                   |
| Small appliance circuits | 2 × 1500 W           | Home Depot                   |
| Laundry circuit          | 1500 W               | Home Depot                   |
| Electric range           | 12 000 W             | EcoFlow website              |
| Dryer                    | 5000 W               | Inspire Clean Energy website |
| Air conditioner          | 3500 W               | Lennox website               |
| Heat pump (later)        | 5000 W               | Jackery website              |
| Heat pump water heater   | 3000 W               | Typical residential rating   |

The sum of these gives the total connected power in Watts  
It represents the maximum possible draw if everything runs at once

---

## Sources

https://www.homedepot.com/c/ah/how-to-calculate-electrical-load-step-by-step/9ba683603be9fa5395fab9019a159b03  
https://www.ecoflow.com/us/blog/ultimate-guide-electric-stove-wattage  
https://www.inspirecleanenergy.com/blog/sustainable-living/  
https://www.lennox.com/residential/lennox-life/consumer/air-conditioner-wattage  
https://www.jackery.com/blogs/knowledge/how-many-watts-does-a-heat-pump-use  

---

### Lighting
Home Depot states:  
“Assume 3 watts per square foot of living space for the home's lighting and general purpose circuits.”

### Small Appliance Circuits
“Assume 1,500 watts for each 20-amp small appliance circuit.”

### Laundry Circuit
“If the house has two small appliance circuits and a laundry circuit, that makes 4,500 watts.”

### Electric Range
Used upper-bound value for larger electric stove wattage (12,000 W)

### Dryer
“Dryers use around 1,800 – 5,000 watts, with 3,000 being the average.”  
Upper bound (5000 W) selected

### Air Conditioner
“A full-sized central system could draw over 3,500 watts depending on efficiency ratings.”

### Heat Pump
5-ton heat pump ≈ 5000 W input assumption

---

## Part 2 – Demand Factor (Reduction Factor)

Realistically, not all circuits run simultaneously at full power

We apply code-required adjustments (demand factors).  
This produces the calculated load, which engineers use to size:

- Service conductors  
- Main breaker  
- Electrical panel  

Simplified residential method used:

- First 10 kW at 100%
- Remainder at 40%

Reference:  
https://vancouver.ca/files/cov/electric-load-calculation-residential.pdf

Note:
The City of Vancouver form uses a more structured approach:

- 5000 W base load for first 90 m²
- +1000 W per additional 90 m²
- Separate heating rules
- Specific range treatment
- Specific EVSE treatment

This simplified approach was chosen for brevity

---

## Part 3 – Convert to Amps

After calculating adjusted demand load in watts:

Amps = Demand (W) / System Voltage (V)

calculated demand current = 78.7 A, this is less than the 100A service rating 

### Engineering Conclusion

Under the simplified residential demand method:

- A **100 A service is technically adequate** for the modeled electrified house  
- However, the margin is limited  

Given future electrification trends such as:

- Electric vehicle charging  
- Additional electric heating  
- Simultaneous high-load appliance use  

A **200 A service upgrade is recommended for long-term electrification readiness**

This Excel analysis forms the baseline engineering justification that is later cross-checked in the Revit model