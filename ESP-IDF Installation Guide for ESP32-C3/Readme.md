


# ESP-IDF Installation Guide for ESP32-C3

## Prerequisites

Before installing ESP-IDF, ensure you have:

* A stable internet connection
* At least **10 GB free disk space**
* Python **3.8 or later**
* Git installed

---

## Step 1: Install Git

### Windows

Download and install Git from:

```
https://git-scm.com/downloads
```

Verify installation:

```bash
git --version
```

---

### Linux (Ubuntu / Debian)

```bash
sudo apt update
sudo apt install git -y
```

---

### macOS

```bash
brew install git
```

---

## Step 2: Install Python

### Windows

Download Python from:

```
https://www.python.org/downloads/
```

✔ During installation, **check “Add Python to PATH”**

Verify:

```bash
python --version
```

---

### Linux

```bash
sudo apt install python3 python3-pip -y
```

---

### macOS

```bash
brew install python
```

---

## Step 3: Download ESP-IDF

Clone the ESP-IDF repository:

```bash
git clone -b v5.1 --recursive https://github.com/espressif/esp-idf.git
```

> You can change the version (`v5.1`) if required, but this version is stable for ESP32-C3.

---

## Step 4: Install ESP-IDF Tools

Navigate to the ESP-IDF directory:

```bash
cd esp-idf
```

Run the install script:

### Windows

```bash
install.bat
```

### Linux / macOS

```bash
./install.sh
```

This installs:

* ESP32-C3 toolchain (RISC-V)
* Python virtual environment
* Required build tools

---

## Step 5: Set Up ESP-IDF Environment

This step must be done **every new terminal session**.

### Windows

```bash
export.bat
```

### Linux / macOS

```bash
source export.sh
```

Verify:

```bash
idf.py --version
```

---

## Step 6: Create a Test Project

Create a new project from the template:

```bash
idf.py create-project hello_world
cd hello_world
```

---

## Step 7: Set Target to ESP32-C3

This step is **mandatory**.

```bash
idf.py set-target esp32c3
```

---

## Step 8: Configure the Project (menuconfig)

```bash
idf.py menuconfig
```

Use this menu to:

* Configure Wi-Fi
* Set CPU frequency
* Enable logs
* Adjust flash size

Exit and save when done.

---

## Step 9: Connect ESP32-C3 and Find Port

### Windows

Check Device Manager → Ports (COM & LPT)

### Linux

```bash
ls /dev/ttyUSB*
```

### macOS

```bash
ls /dev/cu.*
```

---

## Step 10: Build, Flash, and Monitor

Replace `<PORT>` with your actual port.

```bash
idf.py -p <PORT> flash monitor
```

Example:

```bash
idf.py -p COM5 flash monitor
```

You should see:

```
Hello world!
This is esp32c3 chip with 1 CPU core(s)
```

Exit monitor:

```text
Ctrl + ]
```

---

## Common Issues & Fixes

### Problem: `idf.py not found`

✔ Run `export.bat` / `source export.sh`

---

### Problem: Permission denied (Linux)

```bash
sudo usermod -a -G dialout $USER
```

Log out and log back in.

---

### Problem: Wrong target

✔ Always run:

```bash
idf.py set-target esp32c3
```

---

## Recommended Folder Structure

```
esp-idf/
projects/
├── hello_world/
├── gpio_blink/
└── wifi_station/
```

---

## Learning Outcome

After completing this setup, you can:

* Develop ESP32-C3 firmware using ESP-IDF
* Use FreeRTOS-based multitasking
* Build secure Wi-Fi and BLE applications
* Create production-grade IoT firmware


