
# 🛠️ Setup Instructions – Accident Detection System (Raspberry Pi)

This guide explains how to set up and run the Accident Detection System using a Raspberry Pi, sensors, and a GSM module.

---

## 🔧 Required Hardware

- Raspberry Pi (any model with GPIO pins)
- MPU6050 (accelerometer + gyroscope)
- SIM800L GSM module
- Breadboard and jumper wires
- Power supply (5V, 2A or more)

---

## 🖥️ Software Requirements

Make sure your Raspberry Pi is running **Raspberry Pi OS** and connected to the internet.

Install Python dependencies:

```bash
pip install smbus pyserial
````

---

## ⚙️ Raspberry Pi Setup

### Enable I2C and Serial:

1. Open the Raspberry Pi configuration tool:

   ```bash
   sudo raspi-config
   ```

2. Go to:

   * `Interfacing Options` > **I2C** → Enable
   * `Interfacing Options` > **Serial**

     * Disable login shell over serial
     * Enable hardware serial port

3. Reboot the Raspberry Pi:

   ```bash
   sudo reboot
   ```

---

## 🔌 Connecting the Components

### MPU6050 (I2C Sensor)

| MPU6050 Pin | Raspberry Pi Pin |
| ----------- | ---------------- |
| VCC         | 3.3V             |
| GND         | GND              |
| SDA         | GPIO2 (SDA)      |
| SCL         | GPIO3 (SCL)      |

### SIM800L (GSM Module)

| SIM800L Pin | Raspberry Pi Pin     |
| ----------- | -------------------- |
| VCC         | 4V external (not 5V) |
| GND         | GND                  |
| TX          | GPIO15 (RXD)         |
| RX          | GPIO14 (TXD)         |

> ⚠️ **Note:** SIM800L needs 4V, not 5V. Use a buck converter or Li-ion battery.

---

## 🚀 Running the Code

1. Rename the code files from `.txt` to `.py` (if needed):

   ```bash
   mv code/main_code.txt code/main_code.py
   ```

2. Edit the phone number in the code:

   ```python
   phone_number = "+91XXXXXXXXXX"
   ```

3. Run the script:

   ```bash
   python3 code/main_code.py
   ```

---

## ✅ How It Works

* The MPU6050 detects sudden acceleration or impact.
* If an accident is detected, an SMS is sent to the specified phone number using the GSM module.

---

## 🧪 Troubleshooting

| Problem              | Solution                                    |
| -------------------- | ------------------------------------------- |
| MPU6050 not detected | Check wiring and run `i2cdetect -y 1`       |
| SMS not sending      | Ensure SIM800L has network (LED blinks)     |
| Serial error         | Make sure login shell is disabled on serial |

