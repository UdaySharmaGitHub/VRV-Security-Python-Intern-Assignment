# Log File Analyzer
- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Output Examples](#output-examples)
- [CSV File Structure](#csv-file-structure)
- [Customization](#customization)


## **Overview**
This Python script analyzes a server log file to extract key insights, including:
- Request counts per IP address.
- Identification of the most frequently accessed endpoint.
- Detection of suspicious activity, such as brute force login attempts.

The results are displayed in the terminal and saved to a CSV file for further analysis.

---

## **Features**
1. **Count Requests per IP Address**:
   - Calculates and displays the number of requests made by each IP address.
   - Results are sorted in descending order of request counts.

2. **Identify the Most Frequently Accessed Endpoint**:
   - Determines the endpoint (URL or resource path) accessed the most and displays the count.

3. **Detect Suspicious Activity**:
   - Flags IP addresses with excessive failed login attempts (default threshold: 10).
   - Failed login attempts are identified by HTTP status code `401` or specific messages like "Invalid credentials."

4. **Save Results to CSV**:
   - Results are saved in a structured format to `log_analysis_results.csv`.

---

## **Requirements**
- Python 3.7 or higher
- No external dependencies (uses Python's standard library)

---

## **Setup Instructions**
1. Clone this repository or download the script files.
2. Ensure the sample log file (`sample.log`) is present in the same directory as the script.
3. Adjust the configuration if needed:
   - Update the log file path: `LOG_FILE`
   - Modify the suspicious activity threshold: `THRESHOLD`

---

## **Usage**
1. Python Script:
   ```bash
   VRV Assignment v1.ipynb
   ```

2. The output will be displayed in the terminal, including:
    - Request counts per IP
    - The most accessed endpoint
    - Suspicious activity detected

3. A CSV file named log_analysis_results.csv will be created in the same directory with the analysis results.

## **Output Examples**
***`Terminal Output:`***
```bash
IP Address           Request Count
192.168.1.1          234
203.0.113.5          187
10.0.0.2             92

Most Frequently Accessed Endpoint:
/home (Accessed 403 times)

Suspicious Activity Detected:
IP Address           Failed Login Attempts
192.168.1.100        56
203.0.113.34         12
```
---

## **CSV File Structure**

The `log_analysis_results.csv` file contains the following sections:

1. **Requests per IP**:
    - Columns: `IP Address`, `Request Count`

    **Example:**
    ```csv
    IP Address,Request Count
    192.168.1.1,234
    203.0.113.5,187
    10.0.0.2,92
    ```

2. **Most Accessed Endpoint**:
    - Columns: `Endpoint`, `Access Count`

    **Example:**
    ```csv
    Endpoint,Access Count
    /home,403
    ```

3. **Suspicious Activity**:
    - Columns: `IP Address`, `Failed Login Count`

    **Example:**
    ```csv
    IP Address,Failed Login Count
    192.168.1.100,56
    203.0.113.34,12
    ```
---
## **Customization**
- ***Log File Path:*** Change the LOG_FILE variable in the script to point to your desired log file.

- ***Suspicious Activity Threshold:*** Modify the THRESHOLD variable to set a custom limit for failed login attempts.
