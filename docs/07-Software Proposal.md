# Software Proposal

This activity diagram illustrates the software workflow for the motion sensor, weight sensor, distance sensor, and motor/LED control logic.

```mermaid
flowchart TD
    %% Main flow
    A([Start]) --> B[Initialize Program]
    B --> C{Initialization Complete?}
    C -->|Yes| D[Run Main Loop]
    C -->|No| B
    D --> E[Begin Parallel Sensor Processes]

    %% Parallel starters
    E --- MOTION_TOP
    E --- LED_TOP

    %% Motion subgraph
    subgraph MOTION["Motion Sensor and Motor Control"]
    MOTION_TOP([ ]) --> F1[Read Motion Sensor]
style MOTION_TOP fill:none,stroke:none

        F1 --> G1{Motion Detected?}
        G1 -->|Yes| H1[Send Signal to Motor Controller]
        G1 -->|No| I1[Keep Motor Idle]
        I1 --> G1 
        H1 --> J1[Activate Motor - Open Lid]
        J1 --> K1[Start Timer]
        K1 --> L1{Timer Expired?}
        L1 -->|Yes| M1[Reverse Motor - Close Lid]
        L1 -->|No| WAIT[Wait]
        WAIT --> L1
        M1 --> N1([End Motion Process])
    end

    %% LED/weight/distance subgraph
    subgraph LED["Weight and Distance Sensor - LED Control"]
     LED_TOP([ ]) --> F2[Read Weight Sensor]
style LED_TOP fill:none,stroke:none
        F2 --> G2[Determine LED Color - Green to Red scale]
        G2 --> H2[Read Distance Sensor]
        H2 --> I2{Object Too Close?}
        I2 -->|Yes| J2[Override LED to RED]
        J2 --> Z2[Play Sound Indicating Full]
        I2 -->|No| K2[Maintain Weight-Based LED Color]
        Z2 --> L2[Output LED State]
        K2 --> L2
        L2 --> M2([End LED Process])
    end

    %% LED color logic subgraph
    subgraph COLORLOGIC["LED Color Decision Logic"]
        CL1([Start Color Decision]) --> CL2{Weight Capacity Level}
        CL2 -->|0% - 25%| CL3[Set LED to Green]
        CL2 -->|25% - 50%| CL4[Set LED to Yellow]
        CL2 -->|50% - 75%| CL5[Set LED to Orange]
        CL2 -->|75% - 100%| CL6[Set LED to Red]
        CL3 --> CL7([Color Selection Complete])
        CL4 --> CL7
        CL5 --> CL7
        CL6 --> CL7
    end

    %% Merge and loop
    M2 --> LOOP_MERGE[End of loop]
    N1 --> LOOP_MERGE
    LOOP_MERGE --> D 

    %% Initialization sub-diagram
    subgraph INIT["Initialization Details"]
        I1a([Start Initialization]) --> I2a[Set Hardware Registers]
        I2a --> I3a[Configure Sensor I/O Pins]
        I3a --> I4a[Configure Motor and LED Drivers]
        I4a --> I5a[Reset Internal Variables]
        I5a --> I6a[Load Default Parameters]
        I6a --> I7a([Initialization Complete])
    end

    %% Cross-links
    B -.-> I1a
    G2 -.-> CL1
