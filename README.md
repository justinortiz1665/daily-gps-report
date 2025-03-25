# GPS Dashboard Excel Format Guide

This document explains the expected Excel file format for the GPS Dashboard application.

## Overview

The GPS Dashboard application requires a specific Excel file structure to properly import and analyze GPS tracking data for athletes. The file should contain detailed session information including player metrics like distance, speed, and acceleration/deceleration data.

## Required Excel Structure

The application expects an Excel file (*.xlsx or *.xls) with at least the following:

### Required Sheet

- **Sessions**: A sheet named exactly "Sessions" containing the raw GPS data for all player sessions

### Column Requirements for "Sessions" Sheet

The "Sessions" sheet must contain the following columns (column headers must match exactly):

| Column Name | Data Type | Description |
| --- | --- | --- |
| Week # | Text/Number | Week identifier (e.g., "Week 1") |
| MD | Text | Match Day type (e.g., "General", "MD-1", "MD-2", "MD", etc.) |
| Player  Position | Text | Player's position (e.g., "Central Midfielder", "Center Back") |
| Session Date | Date | Date of the training session |
| Total Time | Time | Duration of the session |
| Player Display Name | Text | Player's name or identifier |
| Total Distance | Number | Total distance covered in meters |
| Distance Per Min | Number | Distance covered per minute |
| Distance Zone 4 (Absolute) | Number | Distance in Zone 4 in meters |
| Distance Zone 5 (Absolute) | Number | Distance in Zone 5 in meters |
| Distance Zone 6 (Absolute) | Number | Distance in Zone 6 in meters |
| High Speed Running (Absolute) | Number | High-speed running distance in meters |
| Accelerations  (Relative) | Number | Number of accelerations |
| Decelerations (Relative) | Number | Number of decelerations |
| Sum Acc + Dec | Number | Sum of accelerations and decelerations |
| Quality Ratio | Number | Quality ratio metric |
| HML Distance | Number | High/Medium/Low intensity distance |
| Max Speed | Number | Maximum speed reached in m/s |
| Percent of Max Speed | Number | Percentage of max speed achieved |
| Sprint Distance | Number | Sprint distance in meters |

### Optional Sheets

Your Excel file may also contain additional sheets, such as:

- **Sessions - Dashboard**: For predefined dashboard visualizations
- **Sessions - Pivot Tables**: For summarized pivot table data

However, only the "Sessions" sheet is required for the application to function properly.

## Example Data Format

Here's an example of how the data should be structured in the "Sessions" sheet:

| Week # | MD | Player  Position | Session Date | Total Time | Player Display Name | Total Distance | ... |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Week 1 | General | Central Midfielder | 2024-08-12 | 09:27:00 | Player 7 | 4835 | ... |
| Week 1 | General | Center Back | 2024-08-12 | 09:27:00 | Player 14 | 4235 | ... |
| Week 1 | General | Full Back | 2024-08-12 | 09:27:00 | Player 33 | 3998 | ... |
| Week 1 | MD-3 | Wingers | 2024-08-15 | 10:15:00 | Player 26 | 5620 | ... |

## Data Requirements and Validation

- Dates should be in a standard date format recognized by Excel
- Times should be in a standard time format (HH:MM:SS)
- Numeric values should not contain text (except for column headers)
- Missing values are allowed but may affect certain calculations
- Player names and positions should be consistent across sessions
- Week numbers should follow a consistent format

## Additional Notes

1. **Data Volume**: The application is optimized to handle a large number of sessions (1000+)
2. **Data Consistency**: Ensure consistent naming conventions for:
    - Player names
    - Positions
    - Week identifiers
    - MD types
3. **Data Validation**: It's recommended to validate your Excel data before import:
    - No duplicate sessions
    - Proper date/time formats
    - Valid numeric values (no negative distances, etc.)
4. **Data Organization**: Sessions are typically organized by:
    - Weekly training blocks
    - Match day relation (MD, MD-1, etc.)
    - Session types

## Common Issues and Solutions

| Issue | Solution |
| --- | --- |
| Import fails | Check that sheet is named exactly "Sessions" |
| Missing player data | Ensure player names are consistent across sessions |
| Charts show incorrect data | Verify numeric columns contain only numbers |
| Dates display incorrectly | Ensure date format is standard and recognized |
| Data not showing in analysis | Check for missing values in key columns |

## Sample File

For reference, the dashboard was built based on the "GPS Dashboard Project Demo.xlsx" file structure. Use this as a template when preparing your GPS data for import.
