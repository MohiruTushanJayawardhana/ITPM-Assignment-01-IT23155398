# ITPM Assignment 1: Transliteration Accuracy Testing (Option 1)

This repository contains the automated test scripts and results for **Assignment 1 (Option 1)** of the **IT3040 - Information Technology Project Management (ITPM)** module at the Sri Lanka Institute of Information Technology (SLIIT).

## 📌 Project Overview

The objective of this assignment is to evaluate the transliteration accuracy of the Chat Sinhala function on the PixelSuite platform. The goal is to identify and automate **50 negative test cases** where the system fails to correctly convert informal, chat-style Singlish text into Standard Sinhala.

* **Target Application:** https://www.pixelssuite.com/chat-translator
* **Automation Framework:** Python with Playwright
* **Data Management:** OpenPyXL (Excel integration)

## 📁 Repository Structure

```
📦 ITPM-Assignment-01
 ┣ 📜 IT23155398_Assignment 1 - Test cases.xlsx   # Contains all 50 negative test cases and results
 ┣ 📜 IT23155398_test_automation.py               # Main Playwright automation script
 ┣ 📜 README.md                                   # Project documentation
 ┗ 📜 [Optional] Other project files              # Additional configurations if any
```

## 🛠️ Prerequisites

Before running the automated tests, ensure your system meets the following requirements:

1. **Python:** Version 3.11 or 3.12 recommended (3.13+ supported)
2. **Web Browser:** Google Chrome
3. **Operating System:** Windows / macOS / Linux

## 🚀 Installation & Setup Guide

Follow these steps to set up the environment and run the tests.

### Step 1: Clone the repository

```bash
git clone https://github.com/MohiruTushanJayawardhana/ITPM-Assignment-01-IT23155398.git
```
```bash
cd ITPM-Assignment-01-IT23155398
```

### Step 2: Install required dependencies

```bash
python -m pip install -U pip
```
```bash
pip install playwright openpyxl
```

### Step 3: Install Playwright browsers

```bash
playwright install
```

## ▶️ Running the Automated Tests

Before executing the script, **ensure that the `Assignment 1 - Test cases.xlsx` file is CLOSED** to prevent permission errors.

```bash
python "IT23155398_test_automation.py" --excel "IT23155398_Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Script Execution Details

* Reads Singlish inputs from the Excel file
* Launches a Chromium browser using Playwright
* Automates typing on the PixelSuite website
* Extracts transliterated output
* Writes results back into the Excel file (`Actual output` column)
* Updates the `Status` column automatically
* Continues execution until all valid rows are processed

## 📊 Test Case Design (Methodology)

The 50 negative test cases were designed to expose weaknesses in the transliteration system.

* **Coverage:** Includes at least two test cases for each of the 24 Singlish input types (e.g., questions, emojis, abbreviations, romanization variants)
* **Length Variation:** Categorized into Short (S), Medium (M), and Long (L) inputs
* **Goal:** All test cases are expected to produce a **FAIL** result (System Output ≠ Expected Output)

## 👤 Author

* **Name:** Jayawardhana D.V.M.T
* **Student ID:** IT23155398
* **Module:** IT3040 - Information Technology Project Management (ITPM)
* **Institution:** Sri Lanka Institute of Information Technology (SLIIT)
