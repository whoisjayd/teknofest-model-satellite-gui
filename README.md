# Ground Station UI & Raspberry Pi Setup Guide  

## ⚠️ Repository Notice  
This repository contains a simplified, public-facing version(which is just readme).**The *full repository is kept private* to maintain authenticity**. For access inquiries, contact [Jaydeep Solanki](mailto:contactjaydeepsolanki@gmail.com).  

## Key Features  
- **Real-time telemetry monitoring** via PySide6 GUI.  
- **CSV data simulation** for testing.  
- **Raspberry Pi integration** for payload communication.  
- Automated RTC timezone setup (`Europe/Istanbul`).  


## Quick Setup  

### 📲 Ground Station UI  
1. **Install Python 3.10+**  
2. **Set up virtual environment**:  
   ```bash
   python -m venv venv && source venv/bin/activate  # Linux/macOS
   venv\Scripts\activate  # Windows
   ```  
3. **Install dependencies**:  
   ```bash
   pip install -r UI/requirements.txt
   ```  
4. **Launch UI**:  
   ```bash
   python UI/mainwindow.py
   ```  

### 🍓 Raspberry Pi  
1. **Run setup script**:  
   ```bash
   chmod +x RPI/install_setup_libraries.sh && ./RPI/install_setup_libraries.sh
   ```  
2. **Set RTC timezone**:  
   ```bash
   sudo python RPI/rtc_set_time.py
   ```  
3. **Start telemetry**:  
   ```bash
   sudo python RPI/maincode.py
   ```  

---

## Simulate Data  
1. Run `python UI/csv_file_simulation_gui.py`  
2. Load a CSV with columns:  
   ```csv
   Packet_count,Satellite_Status,Error_Code,Mission_Time,Pressure1,Pressure2,Altitude1,Altitude2,Altitude_Difference,Descent_rate,Temperature,Battery_Voltage,Gps_Latitude,Gps_Longitude,Gps_Altitude,Pitch,Roll,Yaw,LNLN,Iot_Data,Team_Number
   ```  

---

## 🔧 Troubleshooting  
| Issue | Solution |  
|-------|----------|  
| **UI fails to launch** | Reinstall dependencies with `pip install -r UI/requirements.txt` |  
| **Pi RTC time incorrect** | Verify internet connection and rerun `rtc_set_time.py` |  
| **No telemetry data** | Check IP address in `mainwindow.py` (Ctrl+F to find/replace) |  

---

## Key Code Modifications  
- **IP Address Change**:  
  1. Open `UI/mainwindow.py` and `UI/csv_file_simulation_gui.py`.  
  2. Search (`Ctrl+F`) for current IP.  
  3. Replace (`Ctrl+H`) with new IP.  

- **Map Tiles**:  
  Edit `tile_layer` URLs in both files to use alternative providers (e.g., OpenStreetMap).  

---

## Visual Reference  
![UI Workflow](https://i.ibb.co/rG0DSnkC/image-2025-03-20-225725582.png)  
*Data flow in the Ground Station UI. Full visuals available in the private repo.*  

---

## 📬 Contact  
**Developer**: **Jaydeep Solanki**  
- Email: [contactjaydeepsolanki@gmail.com](mailto:contactjaydeepsolanki@gmail.com)  
- LinkedIn: [linkedin.com/in/solanki-jaydeep](https://www.linkedin.com/in/solanki-jaydeep)  

**Team Dyaus** (Nirma University)  
- Instagram: [@teamdyaus](https://www.instagram.com/teamdyaus/)  
- Email: [teamdyaus.itnu@gmail.com](mailto:teamdyaus.itnu@gmail.com)  

---

*Note: Payload design files and competition-sensitive code are excluded from this public version. Code may require adjustments for full functionality.* 🛠️
