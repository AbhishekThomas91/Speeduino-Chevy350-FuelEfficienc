# Speeduino Fuel Efficiency Patch – Chevy 350 V8

Custom C module for Speeduino firmware to improve **fuel efficiency at higher RPMs** on a **Chevy 350 V8** by adjusting AFR targets under light-load cruise conditions.

## 🚗 What It Does
- Detects high RPM + light engine load
- Blends a leaner AFR target (e.g., 16.0:1) to reduce fuel usage
- Maintains performance under throttle
- Designed to be safe with wideband O2 and proper tuning

## 🔧 Setup

### 1. Prerequisites
- Speeduino-compatible hardware (Arduino Mega + shield)
- Wideband O2 sensor installed
- TunerStudio (for tuning maps)

### 2. Installation
- Clone this repo into your Speeduino firmware project
- Include `src/speeduino_fuel_efficiency.c` in your build
- Add call to `updateAFRTarget()` inside the main fuel calculation loop

### 3. Config Files
- `ve_table_sample.csv`: Sample VE map for high-RPM cruising
- `speeduino_chevy350.ini`: Optional TunerStudio config entries

## ⚠️ Safety Tips
- Use only with **wideband O2**
- Monitor AFR, EGT, knock
- Never run lean under high load or boost
- Test on a dyno or closed environment before daily driving

## 📁 Project Structure

src/ └── speeduino_fuel_efficiency.c # Main logic

config/ └── speeduino_chevy350.ini # Optional TunerStudio INI additions

ve_table_sample.csv # VE table for tuning reference

## 🙌 Credits
Developed for educational use with Speeduino open-source ECU. Inspired by lean cruise strategies in OEM ECUs.

---

### 📜 License
MIT License – open-source, use at your own risk.
