# HealthCare Data Collection and Dataset Development With Python Web Scraping
## Overview
This project involved collecting, extracting, cleaning, and organizing healthcare information from the MedlinePlus Health Topics XML dataset using Python.

The goal was to transform XML data into organized, related datasets that can be easily accessed and explored using Microsoft Excel.

The project produced three datasets covering health conditions, related health topics, and associated healthcare resources.
## Project focus
Data Collection, Web Scraping, Data Cleaning, and Dataset Development.
## Objectives
- Retrieve healthcare information from the MedlinePlus XML source.
- Parse XML records and extract relevant healthcare information.
- Collect English health conditions and their associated information.
- Extract related health topics and healthcare resources.
- Clean and standardize extracted data.
- Create unique identifiers for related-topic and resource records.
- Organize the extracted information into related datasets.
- Perform data quality checks and validate dataset relationships.
  
**Data Source:** MedlinePlus Health Topics XML

**XML file:** mplus_topics_2026-11-21.xml

**Snapshot date:** November 21, 2026.

MedlinePlus is an online health information resource for patients and their families and friends. It is a service of the National Library of Medicine (NLM), the world's largest medical library, which is part of the National Institutes of Health (NIH).  

The original XML file contains both English and Spanish health-topic records. This project focused on English health-topic records.

## Language distribution check
**English:** 31,408

**Spanish:** 21,181

**Total:** 52,589

## Tools/Libraries
- **Python:** Data collection and processing
- **Visual Studio Code:** Development environment
- **Requests:** Retrieving the XML file
- **BeautifulSoup:** XML parsing and data extraction
- **Pandas:** Data manipulation and dataset creation
- **Regular Expressions:** Text cleaning and whitespace standardization
- **OpenPyXl:** Excel workbook export
- **Microsoft Excel:** Dataset storage and review

## Project Workflow
- **Data Collection:** Retrieved the MedlinePlus XML file using Python Requests and saved it locally.
- **XML Parsing:** Used BeautifulSoup with the XML parser to inspect and navigate the source data.
- **Data Extraction:** Selected English health-topic records and extracted relevant elements and attributes.
- **Data Transformation:** Cleaned embedded HTML markup, standardized whitespace and formatted dates.
- **Dataset Development:** Organized the extracted information into three related datasets using Pandas.
- **Data Validation:** Checked missing values, identifier uniqueness, and relationships between datasets.
- **Export:** Consolidated the final datasets into a multi-sheet Excel workbook.

## Final Datasets
The project produced three datasets, stored in Healthcare_Dataset.xlsx 


| Worksheet | Records | Columns |
| --- | --- | ---|
| Health Conditions | 1,017 | 10 |
| Related Topics | 3,316 | 8 |
| Total | 35,741 | 27|

## 1. Health Conditions

Key fields include:

- Condition_ID
- Condition_Name
- Date_Created
- Short_Description
- Full_Summary
- Alternative_Names
- Health_Category
- MeSH_Terms
- MeSH_IDs
- Condition_URL
  
## 2. Related Topics

Key fields include:

- Related_ID
- Condition_ID
- Condition_Name
- Related_Topic_ID
- Related_Topic_Name
- Related_Topic_URL
- Main_Topic_Language
- Source_Name
## 3. Healthcare Resources

Key fields include:

- Resource_ID
- Condition_ID
- Condition_Name
- Resource_Title
- Resource_URL
- Information_Category
- Organization
- Standard_Description
- Language_Mapped_URL
  
## Dataset Relationships
The three datasets are connected through the original Condition_ID field.

**Health Conditions → Related Topics:** One health condition can have multiple related-topic records.

**Health Conditions → Healthcare Resources:** One health condition can have multiple healthcare resource records.

Unique identifiers were also generated for the two related datasets:

**REL-0001** onwards for Related Topics.

**RES-0001** onwards for Healthcare Resources.

This structure preserves the relationships between the main health conditions and their associated records.

## Data Quality Assurance

The following checks were performed:

- Missing-value assessment.
- Unique identifier validation.
- Language distribution checks for healthcare resources.
- HTML markup removal from full summaries.
- Text whitespace standardization.
- Date formatting checks.
  
Missing values from the original source were retained rather than replaced with unsupported information.

The validation process confirmed that the generated identifiers were unique and that the main condition identifiers in the Related Topics and Healthcare Resources datasets matched records in the Health Conditions dataset.

## Repository Contents

| File | Description |
| --- | --- |
| README.md | Project Overview |
| healthcare_web_scraping.ipynb | Python script for data collection and extraction | 
| Healthcare_Dataset.xlsx  | Final Excel workbook containing three datasets |
| Healthcare_web_scraping_documentation.pdf | Detailed project methodology and documentation |
| requirements.txt | Python libraries required to run the project |

The original XML file is not included in the repository. It can be obtained from the MedlinePlus XML source.

## How to Run the Project

**Clone the repository:** git clone <your-repository-url>

**Navigate to the project folder:** cd Healthcare-Web-Scraping

**Install the required libraries:** pip install -r requirements.txt

**Run the Python script:** python healthcare_web_scraping.py

## Project Limitations
- The project focused on English health-topic records, although the original XML also contains Spanish records.
- Some healthcare resource fields contain missing values because the information was not available for every source record.
- The project used a dated XML snapshot, so subsequent changes to MedlinePlus are not reflected.
- The project focused on data collection, extraction, cleaning, structuring, and validation. Data visualization and statistical analysis were outside its scope.
  
## Project Outcome
The project successfully transformed the MedlinePlus XML source into three structured and related healthcare datasets containing **35,741 records across 27 columns**.

It demonstrates practical experience with **Python web scraping, XML parsing, data extraction, data cleaning, dataset development and data quality validation**.
