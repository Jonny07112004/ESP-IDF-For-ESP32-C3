


# Setting Up VS Code with ESP-IDF Extension (ESP32-C3)

## Prerequisites

Ensure the following are already installed:

* **ESP-IDF** (installed and working via terminal)
* **Python 3.8+**
* **Git**
* **Visual Studio Code**

> If ESP-IDF is not installed yet, complete the ESP-IDF installation first.

---

## Step 1: Install Visual Studio Code

Download and install VS Code from:

```
https://code.visualstudio.com/
```

During installation (Windows):

* ✔ Add to PATH
* ✔ Register Code as an editor

---

## Step 2: Install ESP-IDF Extension in VS Code

1. Open **VS Code**
2. Go to **Extensions** (`Ctrl + Shift + X`)
3. Search for:

   ```
   ESP-IDF
   ```
4. Install **“Espressif IDF”** (official extension)

---

## Step 3: Launch ESP-IDF Setup Wizard

1. Press:

   ```
   Ctrl + Shift + P
   ```
2. Select:

   ```
   ESP-IDF: Configure ESP-IDF extension
   ```

---

## Step 4: Choose Setup Type

Select:

```
EXPRESS
```

✔ Recommended for beginners
✔ Uses existing ESP-IDF installation

---

## Step 5: Configure ESP-IDF Paths

The extension will ask for paths:

### ESP-IDF Path

Select your ESP-IDF installation folder:

```
<your-path>/esp-idf
```

---

### Python Path

Example:

* Windows:

  ```
  <your-path>/esp-idf/python_env/idf5.x_py3.x_env/Scripts/python.exe
  ```
* Linux/macOS:

  ```
  <your-path>/esp-idf/python_env/idf5.x_py3.x_env/bin/python
  ```

---

### Git Path

Automatically detected in most cases.

---

### ESP-IDF Tools Path

Accept default:

```
~/.espressif
```

---

## Step 6: Complete Setup

* Click **Install**
* Wait for tool verification
* Restart VS Code when prompted

---

## Step 7: Open an ESP-IDF Project

### Option 1: Open Existing Project

```
File → Open Folder → Select ESP-IDF Project
```

---

### Option 2: Create New Project

1. Press:

   ```
   Ctrl + Shift + P
   ```
2. Select:

   ```
   ESP-IDF: New Project
   ```
3. Choose:

   * Template: `hello_world`
   * Target: `esp32c3`
   * Project location

---

## Step 8: Set Target to ESP32-C3

If not set automatically:

```
Ctrl + Shift + P → ESP-IDF: Set Target → esp32c3
```

---

## Step 9: Build, Flash, and Monitor

### Build

```
Ctrl + Shift + P → ESP-IDF: Build Project
```

### Flash

```
Ctrl + Shift + P → ESP-IDF: Flash Device
```

### Monitor

```
Ctrl + Shift + P → ESP-IDF: Monitor Device
```

Or use the **ESP-IDF toolbar buttons** at the bottom.

---

## Step 10: Verify Output

Expected serial output:

```
Hello world!
This is esp32c3 chip with 1 CPU core(s)
```

Exit monitor:

```
Ctrl + ]
```

---

## Useful ESP-IDF Commands in VS Code

| Action      | Command                           |
| ----------- | --------------------------------- |
| menuconfig  | ESP-IDF: SDK Configuration Editor |
| Clean build | ESP-IDF: Full Clean               |
| Select port | ESP-IDF: Select Port              |
| Doctor      | ESP-IDF: Doctor Command           |

---

## Common Issues & Fixes

### Extension not detecting ESP-IDF

✔ Re-run:

```
ESP-IDF: Configure ESP-IDF extension
```

---

### COM port not visible

* Install USB-UART driver
* Check Device Manager / `/dev/ttyUSB*`

---

### Permission denied (Linux)

```bash
sudo usermod -aG dialout $USER
```

Log out and log back in.

---

## Recommended VS Code Settings

* Enable **C/C++ IntelliSense**
* Use **ESP-IDF Terminal** instead of system terminal
* Enable **Error Lens** (optional)

---

## Learning Outcome

After this setup, you can:

* Develop ESP32-C3 firmware fully inside VS Code
* Use menuconfig visually
* Debug and monitor serial output
* Build production-grade ESP-IDF projects


