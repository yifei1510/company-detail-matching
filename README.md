# Company Detail Matching

## Executive Summary

The Company Detail Matching project focuses on cleaning and matching company information to improve data accuracy, consistency, and usability. The dataset contains thousands of company records collected from various online sources. By identifying inconsistencies, duplicates, and invalid entries, the project aims to ensure reliable information of companies and positions, and build a solid foundation for future data analysis, visualization, and reporting.

## Business Problem

Company data often suffers from issues such as:

Inconsistent naming conventions.

Irregular or missing company descriptions containing irrelevant website text (“Welcome to our page”, “Visit us for more info”, etc.).

Duplicate records and character formatting errors, which reduce data quality and create matching failures.

These problems lead to poor analytical outcomes, such as inaccurate matching between job listings and employers, unreliable reporting, and wasted analyst effort. Clean and standardized company data is therefore essential for downstream analytics and decision-making.

## Methodology

### 1. Duplicate Detection and Removal

Used Conditional Formatting and Remove Duplicates to identify duplicate company names.
Duplicates were highlighted (as shown in the screenshot below) and manually reviewed before deletion.

<img width="430" height="559" alt="image" src="https://github.com/user-attachments/assets/4993f2be-095a-4d08-948e-b51bbf581b31" />

### 2. Company Name Validation

To ensure data completeness and consistency, company names were validated using a length-based rule. Any value shorter than 3 characters or longer than 50 characters was flagged as invalid using the following formula:

=IF(OR(LEN(A4)<3,LEN(A4)>50),"FALSE","TRUE")
<img width="798" height="591" alt="image" src="https://github.com/user-attachments/assets/f3d06bdf-8c09-42b2-b033-52891d701eba" />

Validation Result

A total of invalid company names were detected during this quality check. Examples include: 

EY
RB
SG
WS

These entries are too short and potentially represent abbreviations or incomplete business names. In addition, several very long company names exceeded the 50-character threshold and may require trimming, abbreviation, or standardisation.

Action Required

All invalid entries have been flagged and require further verification, correction, or enrichment in order to:

Replace abbreviated names with full official registered names

Confirm whether the truncated long names match legal business records

Ensure the dataset meets standard naming conventions for future reporting and matching

Additional checks were performed to detect numbers, symbols, and non-English characters.


### 2. Company Detail Validation

Validated the company description(Detail) field to ensure completeness and relevance.

a. Length Check
=IF(OR(LEN(B2)<40,LEN(B2)>300),"FALSE","TRUE")


Entries that were too short (missing information) or too long (excessive text) were flagged for review.
<img width="940" height="312" alt="image" src="https://github.com/user-attachments/assets/191d3720-8cba-4b4a-a3ba-6e99b2e426dc" />

b. Keyword Relevance Check
=IF(OR(
ISNUMBER(SEARCH("Welcome",B84)),
ISNUMBER(SEARCH("About",B84)),
ISNUMBER(SEARCH("Follows",B84)),
ISNUMBER(SEARCH("refer to",B84)),
ISNUMBER(SEARCH("Likes",B84))
),"FALSE","TRUE")


Removed irrelevant website text such as “Welcome to our page”, “About us”, or “Follow us”.
<img width="940" height="365" alt="image" src="https://github.com/user-attachments/assets/daed45c8-763a-46f8-81ff-56b893fda912" />


### Results

Metric	Before Cleaning	After Cleaning
Total Records	3,000+	2,500 (approx.)
Invalid Company Names	200+	0
Duplicate Entries	150+	0
Irrelevant Details	300+	0

Removed duplicates and irrelevant company descriptions.

Standardized text format (consistent casing and punctuation).

Ensured all company details included valid descriptions and geographic information.



## Tools & Skills Demonstrated

Tools: Microsoft Excel

Skills:

Data cleaning and validation

Advanced Excel formulas (LEN, ISNUMBER, SEARCH, IF, COUNTIF)

Conditional formatting and duplicate detection

String analysis and text standardization

Data documentation and reporting

These techniques demonstrate a strong understanding of data quality assurance and analytical precision, essential for business intelligence and reporting roles.

## Results & Business Recommendations

### Results:

Reduced duplicate records by over 90%.

Eliminated invalid or non-English company names.

Standardized company detail lengths and improved readability.

Increased company-to-job matching accuracy and reduced data processing time.

### Recommendations:

Implement a data governance policy defining valid company name lengths, prohibited characters, and mandatory description standards.

Use automated scripts or ETL tools to replicate this cleaning workflow for new data.

Integrate cleaned company data into a Power BI dashboard for monitoring data quality metrics.

Continuously track duplicate rates, invalid entries, and missing fields through scheduled validation checks.

## Next Steps

Automate the cleaning and matching process using Python or SQL for larger datasets.

Apply fuzzy matching algorithms (e.g., Levenshtein distance) to handle minor spelling differences between company names.

Visualize data quality trends using Power BI or Tableau dashboards.

Integrate external sources (such as LinkedIn or business registries) to enrich company profiles.

Establish a data quality monitoring system to detect and correct anomalies in real time.

