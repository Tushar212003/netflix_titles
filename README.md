# Netflix Titles Dataset - Data Cleaning README

## Overview
This dataset contains information about Netflix titles, including Movies and TV Shows. The original file was cleaned and transformed to ensure consistency and usability for analysis.

---

## Original Columns and Cleaning Performed:

1. **Show_Id**:
   - No changes needed. Unique identifier for each title.

2. **Type**:
   - Categories like "Movie" or "TV Show" are consistent.

3. **Title**:
   - Trimmed extra spaces.
   - Standardized to Proper Case (e.g., "The Crown" instead of "the crown").

4. **Director**:
   - Missing values replaced with `"Unknown"` (if originally missing).
   - Trimmed and standardized.

5. **Cast**:
   - Cleaned to remove leading/trailing spaces.

6. **Country**:
   - Missing entries filled with `"Not Available"`.
   - Trimmed and standardized to Proper Case.

7. **Date_Added**:
   - Converted from text to real Excel Date using `DATEVALUE()`.
   - Use: `=IFERROR(DATEVALUE(H2), "")`

8. **Release_year**:
   - Already clean; no action needed.

9. **Rating**:
   - Standardized to uppercase using `UPPER()` function.

10. **Duration**:
    - Originally mixed strings (e.g., "104 min", "3 Seasons").
    - Split into two columns:
      - `Duration_Value`: Numeric part (e.g., `104`, `3`)
      - `Extract Duration Type`: Time unit (e.g., `min`, `Seasons`)
    - Formula used:
      - `=IFERROR(VALUE(LEFT(J2, FIND(" ", J2)-1)), "")`
      - `=IFERROR(TRIM(MID(J2, FIND(" ", J2)+1, LEN(J2))), "")`

11. **listed_in**:
    - Trimmed spaces.
    - Standardized capitalization (e.g., "Dramas, Romantic Movies").

12. **Description**:
    - No critical issues found; trimmed spaces.

---

## Notes
- No null values remain in the dataset.
- No duplicates found.
- Dataset is analysis-ready and structured for pivoting, filtering, and visual reporting in tools like Excel, Power BI, or Python.

