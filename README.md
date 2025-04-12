
---

# 🔍 Port Scanner

**Port Scanner** is a Python tool designed to monitor and scan USB devices connected to your system. Using libraries such as `pyudev` and `pyusb`, it listens for USB events (like device insertion or removal) and logs detailed device information. This tool can be used for real-time tracking and device-specific actions on USB ports.

---

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Customization](#customization)
- [Disclaimer & Legal Notice](#disclaimer--legal-notice)

---

## Features ✨

- **Real-Time USB Monitoring:**  
  Detects and logs USB device connections and removals as they occur.

- **Device Information Logging:**  
  Captures device-related data such as device paths, interface numbers, and more.

- **USB Device Management:**  
  Utilizes `pyusb` to detach kernel drivers when necessary and access device configurations for further operations.

- **Custom Actions:**  
  Easily extendable to perform device-specific tasks (e.g., reading barcodes or other USB interactions).

---

## Requirements 🛠

- **Python 3.x:**  
  Ensure you have Python 3 installed on your system.

- **Required Python Libraries:**
  - `pyusb`
  - `pyudev`
  - `logging` (Python Standard Library)

  *Tip:* Consider using a virtual environment to manage dependencies.

---

## Installation 💾

1. **Clone or Download the Repository:**

   ```bash
   git clone https://github.com/yourusername/port-scanner.git
   cd port-scanner
   ```

2. **Set Up a Virtual Environment (Recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. **Install the Required Dependencies:**

   ```bash
   pip install pyusb pyudev
   ```

---

## Usage 🚀

1. **Run the Port Scanner:**

   Execute the Python script:

   ```bash
   python port_scanner.py
   ```

2. **Monitoring USB Devices:**

   - The tool will automatically begin monitoring USB device events.
   - When a new USB device is added, it logs the device information after detaching the kernel driver (if needed) to allow further access.
   - Similarly, on device removal, it updates the internal tracking.

3. **Scanning USB Ports:**

   - After monitoring events, the tool can also iterate through stored USB devices and log detailed information for further processing or actions.

---

## How It Works 🔍

- **USB Event Monitoring:**  
  The script utilizes `pyudev.Monitor` to watch for events originating from the system's udev controller. It filters events related to USB devices and processes them in real time.

- **Device Configuration:**  
  When a device is added, the code attempts to access it via `pyusb` by detaching the kernel driver if it's active and retrieving the device’s configuration details.

- **Logging:**  
  All detected events (insertion or removal) along with device-specific information are logged using Python's `logging` module, providing clear visibility into the USB activity.

- **Device Dictionary:**  
  The device information is stored in an internal dictionary (`usb_devices`) which can be later iterated over to perform additional operations or scans on the connected USB ports.

---

## Customization 🎨

- **Extend Functionality:**  
  Enhance the project by adding more actions when specific devices are connected (e.g., read barcodes, perform diagnostics, trigger alerts, etc.).

- **Logging Enhancements:**  
  Customize logging formats or direct logs to different outputs (files, consoles, or remote servers).

- **Interface Integration:**  
  Integrate with a GUI or web dashboard to create a user-friendly interface for real-time monitoring and management.

---

## Disclaimer⚠️

> **Important:**  
> This project is intended for educational and testing purposes only.  
> Use this tool only on systems and devices for which you have explicit permission to monitor. Unauthorized use may be illegal and unethical.  
> **Use responsibly and at your own risk.**

---

Enjoy using Port Scanner, and feel free to customize and extend its functionality as needed. Happy scanning!  

---
