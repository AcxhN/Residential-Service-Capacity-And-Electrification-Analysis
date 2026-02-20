# Revit Documentation 

## Project Purpose 

The goal of the Revit file is not to build architecture, instead it's to place major electrical equipment in a architecture file and generate a panel schedule 
https://libraryrevit.com/rvt/single-story-house-plan/ 
---

## Documentation of workflow

## 1. Define Rooms and Electrical Space

- Select architectural link → Edit Type
- Ensure Room Bounding is checked
- Analyze tab → Space
- Select kitchen / living / dining area
- Rename to kitchen-living-dining-room

This allows panel location and load organization to be structured logically

---

## 2. Place Main Panel

- Go to Lighting Plan L1
- Systems → Electrical Equipment
- Select 100A panel
- Place on living room wall
- Rename panel to Panel1

### Mental Model Before Continuing

- A panel is only a container until circuits are connected
- Major loads must have electrical connectors to allow circuit creation
- MEP libraries contain smart families with connectors
- Circuits must match panel distribution system

---

## 3. Represent Major Loads

Initial attempt:
- Load Architectural range outlet family
- Could not host or circuit properly

Solution:
- Use MEP family: motor with disconnect
- Duplicate type
- Rename and configure per load

Load types created:

- Lighting load
- Small appliance circuits
- Laundry circuit
- Electric range – 12kVA – 240V – 2P
- Dryer – 5kVA – 240V – 2P
- Air conditioner – 3.5kVA
- Heat pump – 5kVA
- Heat pump water heater – 3kVA

Each type configured with:

- Voltage
- Number of poles
- Apparent load (VA)

- When connecting to panel it said the motors were not compabtabile with panel, so I repeated the process but with receptacles.
- When trying to create a circuit between receptacles and the panel, the panels more accurate to residential panels in real life could not be assigned a distrubution system, so I had to alternate between panels until one came with a distribution system

## 4. Panel Schedule Results

From Revit Panel Schedule:

- Total connected load = 40,200 VA  
- Estimated demand = 25,100 VA  
- Connected current = 112 A  
- Estimated demand current = 70 A  
- Demand factor ≈ 62%

Observation:

- Schedule shows 120/208V 3-phase system
- Typical house should be 120/240V single-phase
- Despite voltage mismatch, numerical feasibility comparison remains valid

---

# Engineering Evaluation

## Connected Load Check

I = S / (√3 × V_LL)

- S = 40,200 VA
- V_LL = 208 V

I ≈ 112 A

- Exceeds 100A rating

---

## Demand Load Check

- S_demand = 25,100 VA

I ≈ 70 A

- Below 100A rating

---

# Cross-Check With Excel Analysis

Excel Phase 1 Results:

- Connected load = 32,200 W  
- Adjusted demand load = 18,880 W  
- Calculated current = 78 A  

Comparison:

- Excel demand current = 78 A  
- Revit estimated demand current = 70 A  

Difference explanation:

- Revit applied internal load classifications and demand factors
- Excel used simplified residential demand rule
- Both approaches show demand under 100 A
- Both indicate limited headroom

Conclusion:

- Revit model validates Excel engineering logic
- Minor differences due to demand factor methodology
- Both confirm electrified house is near capacity of 100A service

---

# Final Feasibility Conclusion

- Connected loads exceed 100A rating
- Demand-adjusted loads remain under 100A
- Electrification significantly reduces safety margin

Recommendation:

- Upgrade to 200A service for electrification readiness

If remaining at 100A:

- Load management required
- EV charging likely constrained
- Future expansion limited

---

# Helpful References

- https://www.youtube.com/watch?v=qV-uAH9qS00  
- https://www.youtube.com/watch?v=6cpyglx_rXQ  