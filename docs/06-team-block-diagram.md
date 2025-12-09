---
title: Team Block Diagram
---

The block diagram was designed with ease of connectivity in mind. Our product consists of two subsystems: the motor and the LED scale. Each of these outputs is connected to its associated sensor: the motion sensor and the force and distance sensors, respectively. Each block diagram is connected to the others to ensure a common ground voltage. Each diagram indicates the power level used by the components, as well as the specific component used for each part of the diagram, and to which pins the components are connected. 


<img width="1198" height="390" alt="Screenshot 2025-12-08 at 9 27 11 PM" src="https://github.com/user-attachments/assets/0362a100-f2e1-40be-845e-d8854993058c" />


PDF available [here](https://github.com/user-attachments/files/24046176/Team207_Block_Diagram_FR.drawio.pdf)

## Team Design and Decision-Making Process: Message Structure

Our team approached the design of the message structure by first analyzing example block diagrams for similar systems. We aimed to maintain consistency across all components in our system, ensuring that signals between sensors, microcontrollers, and actuators were clearly defined and easy to follow. Each message was structured to include only the necessary information for triggering actions, such as lid opening or fullness notifications, to reduce the chance of errors or miscommunication. During the design process, we iteratively refined the block diagram as a team, discussing how each sensor’s data would flow through the system and how messages would be formatted to maintain reliability and clarity. This approach enabled us to establish a consistent and easy-to-understand communication structure that could be implemented directly in our code and hardware.

## Top 5 Biggest Changes to Software Design

1. **Added a second sensor**  
   Originally, the system used only one sensor for detecting both motion and fullness. We realized that separating the sensors would better fit the project requirements. By introducing a second sensor, each microcontroller now handles two inputs, making the software more complex to write and debug. 

2. **Reassigned Sensors**  
   To improve subsystem organization, the sensors were moved to Hattie’s board. This required reassigning pins and updating the software to match the new hardware connections. The change ensures cleaner separation of hardware responsibilities and reduces wiring complexity, which in turn simplifies code maintenance.

3. **Changed pin types (digital ↔ analog)**  
   During the reorganization, some pins originally configured as digital needed to be analog, and vice versa, depending on the sensor requirements. Updating the pin types in the code ensured that the microcontrollers read correct values from each sensor. This adjustment reduced misreadings and simplified the software logic for handling inputs.

4. **Simplified channel switching**  
   With multiple sensors on separate channels, the previous complex switching routines were no longer necessary. The code was simplified to read each sensor independently, avoiding timing conflicts or interference. This improves overall responsiveness and reliability, as documented in [Hattie’s website](https://jhlee59.github.io/07-Microcontroller%20Code/Microcontroller%20Code/) with the sensor channel switching implementation.

5. **Improved subsystem connection mapping**  
   Updating the software to match the reorganized block diagram clarified the relationships between sensors, microcontrollers, and actuators. This ensures that data flows correctly between subsystems and that signals trigger actions accurately. The UML diagrams were revised to reflect these changes, making it easier to maintain and extend the code in future iterations.


