# **Elevator Control System using VHDL**

## **Project Overview**
This project implements a **three-floor elevator control system** using **VHDL** and an **FPGA board**. The elevator operates with three call buttons (one per floor) and includes safety mechanisms such as **position detection switches** and **motor control logic**. The system ensures that the elevator moves only when conditions are met, preventing invalid transitions.

## **Table of Contents**
- [Project Overview](#project-overview)
- [Features](#features)
- [State Diagram](#state-diagram)
- [Implementation Details](#implementation-details)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation & Setup](#installation--setup)
- [Code Structure](#code-structure)
- [Working Mechanism](#working-mechanism)
- [Testing & Debugging](#testing--debugging)
- [Future Enhancements](#future-enhancements)
- [License](#license)

## **Features**
✅ Three-floor elevator simulation  
✅ Button-based floor calling mechanism  
✅ Rack-and-pinion gear system  
✅ Position detection using four switches  
✅ State Machine for movement logic  
✅ FPGA-based hardware implementation  
✅ Safe movement with state validation  
✅ Emergency stop functionality  

## **State Diagram**
The project uses a **7-state FSM (Finite State Machine)**:
1. **F1 (Floor 1)**
2. **F2 (Floor 2)**
3. **F3 (Floor 3)**
4. **MU2 (Moving Up to Floor 2)**
5. **MU3 (Moving Up to Floor 3)**
6. **MD2 (Moving Down to Floor 2)**
7. **MD1 (Moving Down to Floor 1)**


## **Implementation Details**
The elevator system is implemented using **VHDL** and follows a structured approach:
- **Sensors:** Detect the elevator’s position at different floors.
- **Buttons:** Control the movement of the elevator.
- **Motor Control:** Ensures the elevator moves up or down as required.
- **FSM Logic:** Handles transitions based on inputs from buttons and sensors.
- **LED Indicators:** Show the current state and floor.
- **Error Handling:** Prevents illegal movements.

### **Basic Operation:**
- If a floor button is pressed, the elevator moves accordingly.
- The platform is considered aligned only when both **middle switches** are closed.
- The system prevents **invalid movements** (e.g., moving up while already at the top floor).

## **Hardware Requirements**
- FPGA board (e.g., Xilinx Spartan-6)
- Push buttons for floor selection
- Sensors for platform detection
- Rack-and-pinion gear system
- Power supply

## **Software Requirements**
- **Xilinx Vivado / Quartus Prime** (for VHDL simulation & synthesis)
- **ModelSim** (for functional verification)
- **Git** (for version control)
- **Waveform Analyzer** (for FSM debugging)

## **Installation & Setup**
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/elevator-control-system.git
   cd elevator-control-system
   ```
2. Open the project in **Vivado/Quartus**.
3. Load the VHDL source files.
4. Synthesize and generate the bitstream.
5. Upload the bitstream to your FPGA board.
6. Connect the push buttons and sensors.
7. Run the simulation and validate the FSM.

## **Code Structure**
```
📂 Elevator-Control-System
 ├── 📂 src                # VHDL source files
 │   ├── lift_project.vhd  # Main elevator control module
 │   ├── fsm_controller.vhd # State machine logic
 │   ├── motor_control.vhd # Motor handling logic
 │   └── sensors.vhd       # Sensor handling logic
 ├── 📂 testbench          # Simulation testbenches
 ├── 📂 docs               # Documentation & diagrams
 ├── README.md             # Project documentation
 ├── LICENSE               # License file
 ├── elevator_fsm.pdf      # FSM state diagram
 ├── .gitignore            # Git ignored files
 └── 📂 scripts            # Automation scripts
```

## **Working Mechanism**
1. **Idle State:** The elevator remains idle until a floor button is pressed.
2. **Button Pressed:** The FSM determines the direction of movement.
3. **Movement State:** The elevator moves up or down based on the requested floor.
4. **Position Detection:** The sensors confirm when the elevator reaches the desired floor.
5. **Stopping State:** The motor stops when the correct floor is reached.

## **Testing & Debugging**
- **Unit Testing:** Each module is tested separately.
- **Simulation:** ModelSim is used for waveform analysis.
- **Hardware Debugging:** FPGA debugging tools validate movement logic.
- **Edge Cases:** Button spamming, emergency stops, and invalid states are tested.

## **Future Enhancements**
- Add a **4th floor** to increase functionality.
- Implement a **Display Panel** showing the current floor.
- Introduce **Voice Alerts** for better user interaction.
- Optimize power consumption by refining motor logic.

## **License**
This project is licensed under the **MIT License** - see the (LICENSE) file for details.
