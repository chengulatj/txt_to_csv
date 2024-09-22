# MCMIS Catalog: TXT to CSV conversion

This script converts a tab-delimited text file into a CSV file format.  The script reads the input text file line by line, using the tab character as a delimiter to split each line into a list of values. It then writes these values as rows into a new CSV file using the csv module in Python.

This code provides a solution to convert tab-delimited text files from the MCMIS (Motor Carrier Management Information System) Catalog: Crash File into a CSV format. The catalog contains essential data about crashes involving motor carriers, and converting these files from text format to CSV makes the data more accessible for analysiis and manipulation using various tools and software.

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Requirements](#requirements)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Data Structure Overview](#data-structure-overview)
  - [Crash Carrier](#crash-carrier)
  - [Crash Event](#crash-event)
  - [Crash Master](#crash-master)
7. [Examples](#examples)
8. [License](#license)
9. [Conclusion](#conclusion)

## Introduction
The **MCMIS** catalog: Crash File - TCT to CSV COnverter is a Python-based tool designed to convert text files containing detailed crash information into CSV format. The crash data files are available in tab-delimited text format which can be cumbersome to work with in data analysis tools. This converter ensures the data is in more versatile and widely used format (CSV). 

## Features
Converts MCMIS Crash text files (tab-delimited) into CSV format.
Supports multiple categories of crash data: Crash Carrier, Crash Event, and Crash Master.
Uses UTF-8 encoding for compatibility with most data processing tools.
Efficiently handles large datasets.
Provides flexibility in specifying input and output file paths.

## Requirements
**Python 3.x**
Libraries:
csv (python standard library)

## Installation

To use this tool, follow these steps below:
1. **Clone the repository**:
   ```bash
   git clone https://github.com/chengulatj/txt_to_csv.git

2. **Install any necessary dependencies**:
   
 This project only uses Python's standard library, so no additional installation is needed.

## Usage
1. Open the notebook or Python script in Google Colab, Jupyter Notebook, or any Python IDE.
2. Make sure the input text files for **Crash Carrier**, **Crash Event**, and **Crash Master** are located in your specified directory.
3. Set the input variable to the path of the text file you want to convert for each category.
4. Set the output variable to the desired output path for the CSV file for each category.
5. Run the provided code cells or script to perform the conversion for all three categories.
   
## Code Example

Below is a snippet of the main code that reads a text file and writes it to a CSV file:

```python
import csv

# Define input and output paths
input = '/content/drive/MyDrive/CrashCarrier_01012021_12312021HDR.txt'
output = '/content/drive/MyDrive/CrashCarrier_21.csv'

# Specify the delimiter used in the text file
delimiter = '\t'

# Read the text file and write to CSV
with open(input, 'r', encoding='latin-1') as txt_file, open(output, 'w', newline='', encoding='utf-8') as csv_file:
    # Create a CSV writer object
    csv_writer = csv.writer(csv_file)

    # Iterate through each line in the text file
    for line in txt_file:
        # Split the line into a list of values based on the delimiter
        row = line.strip().split(delimiter)
        # Write the row to the CSV file
        csv_writer.writerow(row)

print(f'Text file "{input}" has been successfully converted to CSV file "{output}".')

```

## Data Structure Overview

The text files contain various fields across different categories. Here is an overview of the key fields for each category:

### Crash Carrier

- **CRASH_CARRIER_ID**: Crash Carrier ID
- **CARRIER_SOURCE_CODE**: Carrier Name Source
- **CRASH_CARRIER_NAME**: Carrier Name
- **CRASH_CARRIER_CITY**: Carrier Address/City Name
- **NO_ID_FLAG**: No Census Number Flag ("Y" or "N")
- **DOCKET_NUMBER**: Docket Number

### Crash Event

- **CRASH_EVENT_ID**: Crash Event ID
- **EVENT_ID**: Event ID
- **SEQ_NO**: Sequence Number
- **EVENT_OTHER_DESC**: Other Description

### Crash Master

- **CRASH_ID**: Crash ID
- **REPORT_STATE**: Report State
- **REPORT_NUMBER**: Report Number
- **REPORT_DATE**: Report Date
- **VEHICLE_CONFIGURATION_ID**: Vehicle Configuration
- **WEATHER_CONDITION_ID**: Weather Condition

## Examples

The notebook includes examples for converting different text files for the **Crash Carrier**, **Crash Event**, and **Crash Master** categories over multiple years. Each example demonstrates how to specify the input and output paths and perform the conversion.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Conclusion

By converting **MCMIS Crash** data files from **TXT to CSV** format, this tool makes the data much more accessible for analysis and visualization. Whether you are a data analyst, a researcher, or a traffic safety professional, this converter will save you time and effort when working with crash data.

