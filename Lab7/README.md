# LAB 7 – Fuzz Testing with Hypothesis

**Course:** Software Testing / Software Engineering Lab  
**Lab:** 7  
**Project:** Bookstore Trade-In  
**Student:** Shweta  
**SRN:** PES1UG24AM404

## 1. Objective

The objective of this lab is to perform fuzz testing using the Hypothesis library in Python.

Fuzz testing generates random inputs and checks whether program functions handle unexpected inputs without crashing.

## 2. Project Description

This project tests three functions from `processor.py`:

1. `verify_isbn10_format()` – Processes ISBN-10 input and extracts its format details.
2. `calculate_depreciation_factor()` – Calculates the depreciation factor based on book age and lifespan.
3. `lookup_condition_multiplier()` – Returns a multiplier based on the book's physical condition.

## 3. Files Included

| File | Description |
|---|---|
| `processor.py` | Module containing the functions under test. |
| `test_processor.py` | Hypothesis-based fuzz testing functions. |
| `README.md` | Project documentation. |
| `screenshots/` | Screenshots of implementation and execution results. |

## 4. Technologies Used

- Python 3
- Hypothesis
- Pytest
- Visual Studio Code

## 5. Installation

Install the required Python libraries:

```bash
python -m pip install hypothesis pytest
```

## 6. Test Implementation

The `test_processor.py` file contains three fuzz testing functions.

### Test 1: ISBN-10 Format

Generates random strings and None values to test how the ISBN processing function handles unexpected inputs.

### Test 2: Depreciation Factor

Generates random inputs to test whether the depreciation calculation handles invalid values safely.

### Test 3: Condition Multiplier

Generates random inputs to test whether the condition lookup function handles unsupported condition codes safely.

### Hypothesis Strategies

- `st.text()` generates random text inputs.
- `st.none()` generates None values.
- `@given()` supplies generated inputs to the test functions.
- `try-except` handles expected exceptions.
- `assert` checks the returned output.

## 7. Execution Instructions

Run the tests using:

```bash
python -m pytest -v
```

Run the original processor program manually:

```bash
python processor.py
```

Example inputs:

```text
ISBN-10: 0-306-40615-2
Age/Lifespan: 3/10
Condition: GOOD
```

Expected sample output:

```text
Group 306: Starts 0, Checksum 2
Depreciation Factor: 0.7
Multiplier: 0.6
```

## 8. Screenshots

The `screenshots` folder contains evidence of:

1. Project folder structure.
2. Test implementation.
3. Hypothesis test execution.
4. Manual program execution.

## 9. Conclusion

Fuzz testing was performed using Hypothesis to generate random inputs for the three Bookstore Trade-In functions.

The tests help identify unexpected input handling problems, including type errors, invalid values, and missing condition codes.

This demonstrates how property-based testing can be used to examine program behaviour with a wide range of inputs.
