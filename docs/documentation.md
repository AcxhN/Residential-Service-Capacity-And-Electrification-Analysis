# Project Development Documentation

## Motivation

The initial goal of this project was to develop and demonstrate my skills in Revit and AutoCAD. I wanted to choose something that would genuinely motivate me. While designing an electrical system for a small commercial building would certainly be technical and valuable, I didn’t feel personally connected to that type of project.

Instead, I started thinking about everyday inconveniences in my own life. I considered designing a refrigerator egg dispenser that would make better use of vertical space and help save room. I also thought about creating a wall- or door-mounted hand wrap roller that could neatly roll and unroll wraps to allow them to air out. I even imagined incorporating electronic components such as a small motor to assist with rolling, or possibly a fan or heating element to help them dry. However, those ideas would be better suited to a 3D product design project. Since they strongly interest me, I decided to save them for a future project.

Then I remembered something interesting: In my hometown, Calgary, there was a solar panel rebate program. When I ran the numbers, the results showed that solar panels would lead to long-term cost savings. That realization inspired my current project idea. Initially, I wanted to model my parents’ house in Revit; however, I quickly realized that it would be too ambitious for a beginner, especially if I wanted to create an accurate model. Since I am currently in Vancouver for school, I would not be able to take detailed measurements to ensure precision. So I've settled to trace a floor plan I find online. 

Rather than designing arbitrary building diagrams, the idea evolved into solving a real-world problem:

- Residential electrification
- Solar feasibility
- Service capacity analysis

## Core Engineering Question

In consulting terms:

Can this existing gas-heated home transition toward electrification and net-zero without major electrical infrastructure upgrades?

Consulting engineers routinely evaluate:

- Does this building require a service upgrade?
- Can the panel handle additional loads?
- What are the grid implications?
- Is future capacity sufficient?

## Project Phases

### Phase 1 – Load Calculation (Excel)

- Estimate baseline residential load
- Apply simplified Canadian Electrical Code demand factors
- Compare calculated demand vs 100A service
- Evaluate electrification scenario (heat pump + HP water heater)

### Phase 2 – BIM Modeling (Revit)

- Trace simplified two-storey residential floor plan
- Create levels and walls
- Place main electrical panel
- Place major loads (heat pump, water heater, range, dryer)
- Generate panel schedule

### Phase 3 – Technical Documentation (AutoCAD)

- Create single-line diagram (existing configuration)
- Create electrified configuration diagram
- Show service upgrade alternative if required

## Assumptions

- 2400 sq ft dwelling
- 100A single-phase service
- Gas heating baseline
- Electrification via heat pump systems
- Simplified demand factor (first 10kW at 100%, remainder at 40%)


