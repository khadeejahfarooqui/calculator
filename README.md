# calculator
# Task 8 – Simple Calculator using SpecKitPlus

## Phase 1: /constitution (Setup & Installation)

```bash
# Create virtual environment
python -m venv speckit_env

# Activate virtual environment
# Windows
speckit_env\Scripts\activate
# macOS/Linux
# source speckit_env/bin/activate

# Upgrade pip
pip install --upgrade pip

# Install required packages
pip install specifyplus streamlit pandas
```

**Notes:**

* Virtual environment created
* Packages installed: specifyplus, streamlit, pandas

---

## Phase 2: /specify (Basic Import & Test)

```python
import specifyplus
print("SpecKitPlus version:", specifyplus.__version__)

# Simple connection test
result = specifyplus.test_connection()
print("Connection Test Result:", result)
```

**Notes:**

* Successfully imported specifyplus
* Connection test passed

---

## Phase 3: /plan (Loading Data)

```python
import specifyplus as sp
import pandas as pd

# Load sample dataset
data = sp.load_sample_data("example_dataset.csv")

# Display first 5 rows
print(data.head())
```

**Notes:**

* Loaded example dataset using SpecKitPlus
* Verified first 5 rows

---

## Phase 4: /tasks (Data Processing / Analysis)

```python
# Preprocess the loaded data
processed = sp.preprocess_data(data)

# Run basic analysis
summary = sp.analyze(processed)
print(summary)
```

**Notes:**

* Preprocessed data successfully
* Generated summary statistics

---

## Phase 5: /implement (Streamlit Calculator)

```python
import streamlit as st

st.title("Simple Calculator")

num1 = st.number_input("Enter first number:", step=1.0)
op = st.selectbox("Select operation", ["+", "-", "*", "/"])
num2 = st.number_input("Enter second number:", step=1.0)

if st.button("Calculate"):
    if op == "+":
        st.success(f"Result: {num1 + num2}")
    elif op == "-":
        st.success(f"Result: {num1 - num2}")
    elif op == "*":
        st.success(f"Result: {num1 * num2}")
    elif op == "/":
        if num2 == 0:
            st.error("Error: Cannot divide by zero.")
        else:
            st.success(f"Result: {num1 / num2}")
```

**Notes:**

* Streamlit calculator is working
* Test calculator by performing different operations


