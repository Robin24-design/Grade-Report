# Grade-Report

A Python-based student grade management system that calculates individual student performance metrics and generates comprehensive class statistics reports.

## Overview

Grade-Report is a command-line application designed to process student academic records, calculate grade averages, assign letter grades, and provide detailed class analytics. The system processes exam scores in three subjects (Mathematics, English, and Science) for multiple students and generates both a class-wide report and supports individual student lookups.

## Features

### Core Functionality

- **Grade Calculation**: Automatically computes average scores across three subjects (Maths, English, Science)
- **Grade Assignment**: Assigns letter grades based on standardized grading scale:
  - **A**: 80-100
  - **B**: 70-79
  - **C**: 60-69
  - **D**: 50-59
  - **F**: Below 50
- **Pass/Fail Status**: Automatically determines pass (≥50) or fail (<50) status for each student
- **Class Statistics**: Generates aggregate statistics including:
  - Class average
  - Highest student average
  - Lowest student average
- **Student Search**: Interactive search functionality to look up individual student records by name

### Output

The system generates a formatted class report displaying:
- Student names
- Individual averages (2 decimal precision)
- Assigned letter grades
- Pass/Fail status
- Class-wide statistics

## Data Structure

### Student Records

Students are stored as dictionaries with the following structure:

```python
{
  "name": "Student Name",
  "maths": <score>,
  "english": <score>,
  "science": <score>
}
```

### Sample Data

The system comes with 5 pre-loaded students:

| Name | Maths | English | Science |
|------|-------|---------|---------|
| Robin | 70 | 40 | 50 |
| Tintswalo | 35 | 69 | 38 |
| Peggy | 54 | 87 | 92 |
| James | 42 | 30 | 56 |
| Kulani | 65 | 76 | 71 |

## How It Works

### Step 1: Process Student Scores
- Iterates through each student record
- Calculates the average of three subject scores
- Applies grading logic based on average
- Determines pass/fail status

### Step 2: Generate Class Report
- Displays all students with their calculated metrics
- Computes class-wide statistics:
  - Average of all student averages
  - Highest performing student average
  - Lowest performing student average
- Presents data in a formatted table

### Step 3: Interactive Student Search
- Prompts user to search for a specific student by name
- Displays detailed information for the found student
- Continues until user types 'exit'

## Usage

### Running the Program

```bash
python grade_report.py
```

### Program Flow

1. **Automatic Class Report Generation**: Upon execution, the program displays:
   ```
   ==================================================
                      CLASS REPORT
   ==================================================
   Name         Average    Grade    Status    
   --------------------------------------------------
   Robin        53.33      D        Pass      
   Tintswalo    47.33      F        Fail      
   Peggy        77.67      B        Pass      
   James        42.67      F        Fail      
   Kulani       70.67      B        Pass      
   --------------------------------------------------
   CLASS AVERAGE: 58.33
   HIGHEST AVERAGE: 77.67
   LOWEST AVERAGE: 42.67
   ==================================================
   ```

2. **Student Search**: After the report, the program enters search mode:
   ```
   Search for a student by name (or type 'exit' to quit): robin
   
   --- Student Found ---
   Name : Robin
   Average : 53.33
   Grade : D
   Status : Pass
   ```

3. **Exit**: Type 'exit' to terminate the search function and end the program.

## Code Structure

### Main Components

- **Student Data List**: `students` - Contains all student records
- **Results List**: `results` - Stores calculated metrics for each student
- **Grade Calculation Loop**: Processes each student and assigns grades
- **Class Statistics Calculation**: Computes aggregate metrics
- **Display Functions**: Formats and outputs the class report
- **Search Loop**: Enables interactive student lookups

## Requirements

- Python 3.x
- No external dependencies required (uses only Python standard library)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Robin24-design/Grade-Report.git
   ```

2. Navigate to the directory:
   ```bash
   cd Grade-Report
   ```

3. Run the program:
   ```bash
   python grade_report.py
   ```

## Customization

### Adding New Students

Edit the `students` list to add more student records:

```python
students = [
  {"name": "New Student", "maths": 75, "english": 82, "science": 88},
  # ... existing students ...
]
```

### Modifying Grading Scale

Adjust the grade assignment conditions in the grade logic section:

```python
if average >= 80:
    grade = 'A'
elif average >= 70:
    grade = 'B'
# ... modify thresholds as needed ...
```

### Changing Pass/Fail Threshold

Modify the status assignment line:

```python
status = "Pass" if average >= 50 else "Fail"  # Change 50 to your desired threshold
```

## Example Output

```
==================================================
                   CLASS REPORT
==================================================
Name         Average    Grade    Status    
--------------------------------------------------
Robin        53.33      D        Pass      
Tintswalo    47.33      F        Fail      
Peggy        77.67      B        Pass      
James        42.67      F        Fail      
Kulani       70.67      B        Pass      
--------------------------------------------------
CLASS AVERAGE: 58.33
HIGHEST AVERAGE: 77.67
LOWEST AVERAGE: 42.67
==================================================

Search for a student by name (or type 'exit' to quit): peggy

--- Student Found ---
Name : Peggy
Average : 77.67
Grade : B
Status : Pass

Search for a student by name (or type 'exit' to quit): exit
Exiting search. Goodbye!
```

## Future Enhancements

- **File I/O**: Load student data from CSV/JSON files
- **Web Interface**: Create a web-based dashboard for grade management
- **Export Reports**: Generate PDF or Excel reports
- **Subject Weighting**: Apply different weights to different subjects
- **Percentile Ranking**: Calculate student percentiles within the class
- **Grade Distribution**: Display grade distribution statistics
- **Database Integration**: Store records in a database for persistence

## Author

Robin24-design

## License

Open source - feel free to use and modify as needed.

---

**Last Updated**: August 24, 2026
