🧹 Company Information Data Cleaning and Validation Project

This project focuses on cleaning and validating a dataset containing company names and descriptions.
The goal was to ensure data quality, consistency, and usability for further analysis and dashboard creation.

📊 Project Overview

This dataset initially contained company names and details (descriptions) collected from online sources.
However, many entries included incomplete information, duplicated records, or irrelevant text.
To improve reliability, multiple validation and cleaning steps were applied using Excel formulas, conditional formatting, and manual verification.

🧩 Data Cleaning Methods
1. Company Name Validation

Checked for invalid or incomplete company names using length-based logic:

=IF(OR(LEN(A4)<3,LEN(A4)>50),"FALSE","TRUE")
<img width="898" height="691" alt="image" src="https://github.com/user-attachments/assets/f3d06bdf-8c09-42b2-b033-52891d701eba" />


Company names shorter than 3 or longer than 50 characters were marked invalid.

Additional checks were performed to detect numbers, symbols, and non-English characters.

Duplicates were identified and removed using:

Conditional Formatting → Highlight Duplicate Values

Data → Remove Duplicates

✅ Example: Multiple entries for Tasmanian Government and JPS Medical Recruitment were consolidated into single records.
<img width="530" height="659" alt="image" src="https://github.com/user-attachments/assets/4993f2be-095a-4d08-948e-b51bbf581b31" />

2. Company Detail Validation

Validated the company description (Detail) field to ensure completeness and relevance.

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

3. Duplicate Detection and Removal

Used Conditional Formatting and Remove Duplicates to identify duplicate company names.
Duplicates were highlighted (as shown in the screenshot below) and manually reviewed before deletion.

✅ Results
Metric	Before Cleaning	After Cleaning
Total Records	3,000+	2,500 (approx.)
Invalid Company Names	200+	0
Duplicate Entries	150+	0
Irrelevant Details	300+	0

Removed duplicates and irrelevant company descriptions.

Standardized text format (consistent casing and punctuation).

Ensured all company details included valid descriptions and geographic information.

🧠 Key Learnings

Effective use of Excel formulas for data validation and logical rule checks.

Combined conditional formatting and manual review for precision cleaning.

Reinforced understanding of data quality metrics and string manipulation techniques.

🧰 Tools & Skills Used

Microsoft Excel — Data cleaning, conditional formatting, formula-based validation

Text Analytics — Keyword filtering, pattern recognition

Data Quality Assurance — Duplicate removal, error flagging, manual review
