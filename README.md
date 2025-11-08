# 🧱 3D Printer — Hardware Components

> 🧠 This repository provides everything you need to **plan, build, and operate a custom 3D printer from scratch**.

---

## ⚙️ Mechanical Parts
- 🧩 **Frame Structure**  
- 🛞 **Linear Motion Components**  
- 🪵 **Print Bed Assembly**  
- 🔥 **Extruder & Hotend Specifications**

---

## ⚡ Electronics
- 🧠 **Main Controllers:** Arduino Mega boards  
- 🎛️ **Stepper Motors & Drivers**  
- 🔋 **Power Supply Requirements**  
- 🧭 **Sensors**  
- 💡 **Displays:** *(not for now)*  
- 🔌 **Wiring Specifications**

---

## 🧰 Assembly Tools
- 🧱 Complete list of tools required for printer assembly  

---

## 🖊️ 3D Modeling Software
- 🧒 **Beginner-Friendly:** [Tinkercad] 
- 👨‍💻 **Professional:** [Fusion 360]

---

## 🧠 Slicing Software
- ✂️ **Popular Option:** [Cura]
---

## 💻 Development Tools
- 🪶 **Arduino IDE**  
- 🧩 **PlatformIO**

---

## 📂 File Formats
- 🧱 **STL**, **G-code**, and other essential file formats explained  

---

## 📖 Additional Documentation
- 💽 **Operating System Compatibility Matrix**  
- ✨ **Optional Enhancements:** LED lighting, enclosures  
- 🚀 **Step-by-Step Getting Started Guide**  
- 🌐 **Curated List of Resources & Community Links**

---

⭐ **Build. Create. Innovate.**  
Your open-source journey to a custom 3D printer starts here! 🖨️


---

### **1. Understanding the CNC Shield**
The **CNC Shield (v3)** is a popular open-source hardware add-on for the Arduino **Uno** that supports stepper motor drivers like **A4988** or **DRV8825**. It is designed for CNC machines but can be repurposed for 3D printing with the right firmware and setup.

---

### **2. Components Required**
#### **Electronics:**
- **Arduino Uno** (as the main controller)
- **CNC Shield v3** (stepper driver interface)
- **A4988/DRV8825** stepper drivers (for motor control)
- **NEMA 17 stepper motors** (for X, Y, Z, and extruder)
- **Hotend** (compatible with filament type, e.g., E3D V6)
- **Heatbed** (optional but recommended for better adhesion)
- **Power Supply** (12V or 24V, depending on the components)
- **Limit switches** (for homing X, Y, and Z axes)
- **Thermistors** (for temperature sensing)
- **MOSFET or relay** (to control the heated bed)
---

### **3. Wiring the CNC Shield**
The CNC Shield has four stepper motor slots:
- **X, Y, and Z** for movement.
- **Extruder (E0 or E1)** for filament feeding.

#### **Connecting Stepper Motors:**
1. Insert **A4988/DRV8825 drivers** into the CNC shield.
2. Connect each **stepper motor** to its respective port.
3. Adjust **VREF voltage** on drivers to match motor current requirements.

#### **Connecting Endstops:**
- Connect **X, Y, and Z endstops** to the shield’s **limit switch pins**.
- Use **normally open (NO) configuration** for safety.

#### **Connecting the Hotend & Heatbed:**
- Use **MOSFET or relay** to handle the high power demand.
- The **hotend and bed thermistors** connect to the **analog input pins**.

---

### **4. Installing and Configuring Firmware**
Since the CNC Shield does not natively support 3D printing, you need firmware that can drive a 3D printer:

#### **Option 1: GRBL-Based Firmware (Hacked)**
- GRBL is designed for CNC milling, but it can be modified for 3D printing.
- Requires additional **G-code preprocessing**.

#### **Option 2: Marlin (Preferred)**
- Use **Marlin Firmware** with an **Arduino Mega 2560 + RAMPS 1.4** for full compatibility.
- The **Arduino Uno + CNC Shield** combination has limited flash memory, making Marlin difficult to use.

#### **Flashing Firmware:**
1. Install **Arduino IDE**.
2. Download and modify **GRBL for CNC Shield** or **Marlin for RAMPS**.
3. Upload the firmware to the **Arduino Uno**.
4. Configure **steps/mm**, acceleration, and temperature settings in firmware.

---

### **5. Assembling the 3D Printer**
1. **Frame Assembly**: Build a rigid structure with aluminum extrusions.
2. **Linear Motion**: Attach **smooth rods, linear bearings, and lead screws** for movement.
3. **Hotend Mounting**: Secure the hotend to the **X-carriage**.
4. **Bed Leveling**: Ensure a flat and adjustable print bed.
5. **Electronics Mounting**: Secure the **Arduino, CNC shield, and power supply**.
6. **Cable Management**: Use zip ties and drag chains to keep wiring neat.

---

### **6. Testing and Calibration**
- **Check stepper motor movement** using software like **Pronterface**.
- **Home all axes** to verify endstop functionality.
- **PID Tune the hotend and heatbed** for temperature stability.
- **Calibrate steps/mm** for accurate motion.
- **Test extrusion** by manually extruding filament.

---

### **7. Running the Printer**
- Load slicing software like **Cura**
- Export G-code and send it via **Pronterface** or **OctoPrint**.
- Start printing and fine-tune the settings.

---

### **Challenges & Limitations**
- **Limited stepper driver control**: The CNC Shield lacks advanced features like microstepping tuning.
- **No native 3D printing support**: Workarounds are needed for proper extrusion control.
- **Weak power handling**: The shield isn’t designed for high-power heated beds.

