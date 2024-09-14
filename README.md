# Plus Code Geocoder with Google Maps API
======================================================

This Python script is designed to take a CSV file as input, extract the Plus Codes, and use the Google Maps API to obtain their corresponding latitude and longitude coordinates. The resulting DataFrame can be saved in either CSV or XLSX format.

## Requirements
---------------

*   **Python 3.x**: This script uses various libraries that are compatible with Python 3.x. (Suggesred : Python 3.10)
*   **pandas**: A library for data manipulation and analysis.
*   **requests**: A library for making HTTP requests to the Google Maps API.
*   **openpyxl**: A library for reading and writing Excel files.
*   **tqdm**: A library for displaying a progress bar during Plus Code geocoding.

```python
pip install pandas openpyxl requests tk tqdm
```

## Usage
------

### Step 1: Set Your Google Maps API Key

Replace `api_key` with your actual Google Maps API key:

```python
api_key = "YOUR_GOOGLE_MAPS_API_KEY"
```

### Step 2: Run the Script

Run the script, and it will guide you through the following steps:

#### Step 3: Select Your CSV File

Choose a CSV / XLSX file to process using the file dialog.

#### Step 4: Find the Plus Code Column

The script assumes that the Plus Code column contains the word "Plus" or "plus". If this is not the case, adjust the code accordingly.

#### Step 5: Geocode the Plus Codes with Progress Bar

A progress bar will display during the geocoding process, showing the number of processed Plus Codes.

#### Step 6: Choose Your Output Format

Select either CSV or XLSX format for the output file:

```python
while True:
    print("\nChoose output format:")
    print("1 - CSV")
    print("2 - XLSX")
    user_choice = input("Enter 1 or 2: ").strip()

    if user_choice == '1':
        output_format = 'csv'
        break
    elif user_choice == '2':
        output_format = 'xlsx'
        break
    else:
        print("Invalid choice. Please select 1 or 2.")
```

#### Step 7: Save the Output File

The script will save the resulting DataFrame in the chosen format.

### Example Use Case

Suppose you have a CSV/XLSX file `input.csv or input.xlsx` containing Plus Codes Coloumn, and you want to geocode them using the Google Maps API and save the result as an CSV / XLSX file:

```bash
python run.py
```

Follow the prompts, select `input.csv or input.xlsx`, and choose CSV/XLSX format for the output.

## Code Structure
----------------

The script is organized into the following functions:

### 1. `get_lat_lng_from_plus_code`: Geocode a single Plus Code using the Google Maps API

```python
def get_lat_lng_from_plus_code(plus_code, api_key):
    # ...
```

### 2. `adjust_column_width`: Adjust column widths for better readability in XLSX files

```python
def adjust_column_width(output_file_path):
    # ...
```

## Contributing
--------------

Feel free to contribute to this project by submitting bug fixes or feature requests.

### Issue Reporting

To report an issue, create a new GitHub issue using the following template:

*   Title: Briefly describe the issue.
*   Description: Provide more details about the issue and any relevant information (e.g., error messages).

### Pull Requests

If you'd like to contribute code, fork this repository, make your changes, and submit a pull request.

## License
----------

This script is released under the MIT license. See `LICENSE` for details.
```
Copyright (c) 2024 r7avi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
