
# 📶 2G/3G Throttling Testing using JMeter (GUI-Based) and Chrome's Dev tool (Network tab Throttling)

This repository contains a pre-configured **JMeter test plan (.jmx)** designed to simulate **2G and 3G network conditions** using JMeter GUI. It helps you understand how your application performs under limited bandwidth and higher latency.

---

## 📁 Files

- `Console.jmx` – JMeter test plan configured with timers for throttling simulation
- `README.md` – Instructions to run and generate reports using the GUI
- Bednet_Facility Template.xlsx [1000 facilities]
- Bednet_Users Template.xlsx [1000 users]
- Bednet_Target Template.xlsx [75 Boundaries]

---

## 🎯 Objective

- Simulate 2G/3G mobile network conditions
- Control request rate using **Constant Throughput Timer**
- Simulate network latency using **Uniform Random Timer**
- Export and analyze test results using built-in HTML report generation

---

## 🧰 Requirements

- **Apache JMeter** (version 5.6.3)
- **Java 21 or higher**
- System with GUI capability (Linux)

---

## 🧪 How to Run the Test in JMeter GUI

### 1. **Launch JMeter**

Navigate to the JMeter `bin` folder and run:
- **macOS/Linux**: `./jmeter`

---

### 2. **Open the Test Plan**

- Go to `File > Open`
- Select `Console.jmx` from the project folder

---

### 3. **Review Timers for Throttling**

Inside the Thread Group:

#### ✅ Constant Throughput Timer
- Controls number of requests per minute
- Recommended values:
  - 2G: ~15 samples/min
  - 3G: ~60 samples/min

#### ✅ Uniform Random Timer
- Adds variable delay (network jitter)
- Example:
  - Constant Delay: 1000 ms
  - Random Delay Max: 2000 ms

You can tweak these values as needed for your simulation.

---

### 4. **Set up Result Saving**

#### Option A – Use a Listener:
1. Add a listener like `Summary Report` or `Aggregate Report`
2. Check the box: **"Write results to file / Read from file"**
3. Enter a file path, e.g., `results.jtl`

#### Option B – Add Simple Data Writer:
- Right-click Thread Group → `Add > Listener > Simple Data Writer`
- Set output file: `results.jtl`

---

### 5. **Run the Test**

- Click the **green Start button (▶️)** in the toolbar
- The test will run based on thread settings (number of users, loops, etc.)
- Results will be saved to the file you configured (e.g., `results.jtl`)

---

## 📊 Generate HTML Report from GUI Results

Once the test finishes and results are saved:

### 1. Open a terminal / command prompt

```bash
jmeter -g /path/to/results.jtl -o /path/to/html-report


**





Using Chrome Dev's tool,report is generated  for  3G report
you can check also in https://toolbox.googleapps.com/apps/har_analyzer/ by uploading  .har file.**\

https://drive.google.com/drive/folders/1Z0FRMaQMpIq4gDf_1g_Cqa_mReqcZwOf
