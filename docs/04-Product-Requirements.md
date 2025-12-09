# Product Requirements

## Project Objective

This project aims to develop and explore the capabilities of automating simple household chores to provide greater convenience to customers and enhance the user experience when using an automatic trash can. The goal is to enter a niche in the market for customers seeking convenient solutions to everyday tasks, generate enough sales to turn a profit, and encourage consumers to move away from traditional trash cans toward more innovative, higher-end products. Suppose the product can be priced competitively with standard trash cans. In that case, it is estimated that at least 10% of the target customer group could become interested in this product over other competitors.

## Stakeholders

**Primary Users**
- Busy adults who want a convenient, hands-free trash can.
- Seniors or people with limited mobility who benefit from touch-free operation.
- Families who want a cleaner and safer kitchen environment.  
These groups influence requirements related to accessibility, sensor detection, lid operation, and fullness alerts.

**Household Purchasers**
- People who make buying decisions for their home.
- Focus on price, reliability, durability, and appearance.  
Their preferences affect product cost, size, and design considerations.

**Retailers**
- Stores, warehouses, and shipping partners.
- Need packaging that protects electronics and a form factor suitable for shelves and shipping standards.  
Their needs influence product durability and size.

**Customer Support and Repair**
- Handle troubleshooting and repairs after purchase.
- Prefer designs with clear labeling, accessible PCBs, and replaceable modules.  
Their input influences modularity and maintenance considerations.

## Use Cases

**User Story #1: Harriet**

Harriet is a healthy 56-year-old retired teacher who enjoys light activities such as puzzles and crafts. She moves comfortably around her home and performs daily chores, including taking out the trash. A touch-free trash can would allow her to throw away items without bending excessively. The detection system should remind her when the trash is nearly full, helping her manage household tasks with less effort.

**Implications for Requirements**
- Lid operation must be safe and predictable.
- Fullness detection should trigger before the bag becomes too heavy.
- Indicators must be clear and easy to understand.

**User Story #2: Peter**

Peter is a stay-at-home dad who cooks frequently and often has his hands full. A touch-free trash can allows him to dispose of scraps efficiently without interrupting his cooking workflow. Fullness detection should prevent overflow during busy kitchen use.

**Implications for Requirements**
- Lid must open quickly (0.8–1.5 seconds).
- Sensors must function even when hands are partially obstructed or messy.
- Fullness detection must prevent overflow.

## Aspects

The design is guided by the following prioritized requirements. P1–P10 represent the priority level, with P10 being the highest.

* **Product Design**
    * 1.1 External dimensions no larger than 40 cm × 30 cm × 60 cm while holding at least 13 gallons (50 liters). (P7)
    * 1.2 Maintain a smooth, modern appearance compatible with at least three common household color schemes. (P6)
    * 1.3 Retail price shall not exceed $80 to ensure affordability. (P9)
    * 1.4 Withstand a 0.5-meter drop without breaking or losing lid alignment, tested 10 times. (P10)
    * 1.5 Trash bag replaceable in no more than 2 steps and within 30 seconds. (P10)

* **Functionality**
    * 2.1 Motion sensor shall detect hand/object movement within 25 ± 5 cm and trigger lid opening within 1.0 ± 0.2 seconds. (P10)
    * 2.2 Fullness sensor shall detect when trash reaches 90–95% of maximum capacity. (P9)
    * 2.3 Notify the user within 1 second when fullness reaches 90–95%. (P8)
    * 2.4 Maintain battery operation for at least 7 days before recharge is required. (P4)
    * 2.5 Functionality shall be retained when plugged into an outlet. (P10)
    * 2.6 Lid shall limit odor exposure to no more than 10% of detectable smell outside the trash can. (P7)

## Requirement Criteria Specifications

* **Convenience / Automation**
   * Lid shall open within 0.8–1.5 seconds of detecting motion 20–30 cm above the sensor.
   * Sensor shall detect motion with a minimum accuracy of 95%.
   * Lid shall automatically close 2–4 seconds after motion is no longer detected.
   * Fullness sensor shall indicate 90–95% capacity.

* **User Experience**
   * Lid operations shall not exceed 45 decibels at 1 meter.
   * Indicators must remain visible/audible under typical indoor lighting/noise.
   * Trash bag replacement requires no more than 2 steps.
   * Optional manual open button shall be included.
   * Lid mechanism shall operate at 2–3 seconds per cycle to prevent accidents.

* **Market Competitiveness**
   * Production cost shall not exceed 50–60% of retail price.
   * Compatible with standard 13-gallon (50-liter) bags.

* **Durability / Reliability**
   * Exterior and lid shall withstand a 2 kg impact at 0.5 meters without misalignment.
   * Electronics compartment shall be water-resistant to IPX3.
   * Sensors shall operate for at least 12 months without manual cleaning.

## Open Questions

* Can the product fit standard-sized trash bags in most households?
* Can sensing and lid mechanisms scale for larger models while maintaining efficiency?
* How to ensure sensor accuracy under different lighting conditions?
* What is the optimal sensor distance to balance responsiveness and energy efficiency?
* How long should battery life last between charges? Should low-battery indicators be included?
* Can the trash can be easily cleaned, especially around sensors and lid?
* Should a manual override be included for sensor/power failure?
* Are there safety concerns like finger pinching or accidental lid closures?
* Can the sensor system be software-upgradable to improve detection or add features?
* Should recyclable or energy-efficient components be considered for sustainability?
* What is the expected lifespan, and how can the product be designed for easy repair or replacement?
