# PDF-Data-Extraction-Automation
Extract PDF data via Regex match patterns
To automate data extraction from large number of PDF files and consolidate all extracted data into a spreadsheet in a most speedy manner.
The challenge for this project is to accurately extract at least 18 items from 1000 e-Invoices within one minute.
3 programs of different extraction approaches are developed and evaluated:

Extract_PDF_data_via_screen_scraping.xaml:
- Launch each file to scrap data in foreground.  Speed is extremely slow for processing large number of files.

1.Modern Design experience:   (set IsClassicMode to False in Main.xaml)
      Speed - complete 1.5 files in 45sec.  (lowest speed)
      
2.Classic Design experience:  (set IsClassicMode to True in Main.xaml)
      Speed - complete 3 files in 45sec.     (very slow speed)
      
Extract_PDF_data_via_Taxonomy_Manager.xaml
- Use Taxonomy Manager to build data fields and use Document Understanding tools to digitize (via OmniPage OCR), classify file contents and extract data via various build-in extraction scopes in background.
2 types of Extractor Scopes were tried:

 1.Form Extractor:     (set IsFormExtractor to True in Manin.xaml)
Note: Need Developer Api Key to access EndPoint site to enable the form template editor which is used to mark the data position via an existing PDF file as template.
Limitation: Community licensed only allow to run 50 pdf files within an hour.
      Speed – complete 25 files in 40sec.  (far from expectation)
      
 2.RegexBasedExtractor:  (set IsFormExtractor to False in Main.xaml)
     No need Api key but Developer needs to program specific Regex patterns to match each field.
      Speed – complete 150 files in 40sec.  (fail to beat the challenge)

Extract_PDF_data_via_Regex_match.xaml
- Convert all texts of each PDF file in background and use one Regex match   pattern to extract all the required data in one go and apply strings manipulation to fine-tuning each extracted data.
- 2 Options are available.
 1.Direct Append extracted data to text file in CSV format without data table. (set IsDirecAppendToCSV to True in Main.xaml)
     Speed – complete 1000 files in 40sec.  (Meet the Challenge’s Goal)
 2.Export extracted data to excel file via data table.   (set IsDirecAppendToCSV to False in Main.xaml)
     Speed – complete 1000 files in 40sec.  (Meet the Challenge’s Goal
