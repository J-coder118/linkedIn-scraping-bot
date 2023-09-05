# LinkedIn-Job-Scraping-bot

In 2022, while looking for my first Data Analyst job after graduation, I have to painfully perform a daily mediocre task of scrolling through every single Data Analyst posting on LinkedIn, Glassdoor, Indeed, etc. It was  that moment that I stumbled upon the idea of creating a Web Scraping bot to do all the manual work.

## Tools

I used Python particularly the following tidyverse packages: *pandas, numpy, selenium, gspread, gspread-dataframe, google, pydrive*. I also install the latest Chromedriver to use Selenium: https://chromedriver.chromium.org/downloads

In addition, I need to create an API on **Google Cloud Service** to allow the bots to access the Google Sheet page: https://console.cloud.google.com/apis . In case you don't want to write the data to google sheet component, this part is unneccesasry. Instead

The environment is Jupyter Lab.

## Procedure

The overall process should be something like this:

1. Using Selenium package, the bot would access this link: 
https://ca.linkedin.com/jobs/search?keywords=Data%20Analyst&location=Canada&locationId=&geoId=101174742&f_TPR=r86400&position=1&pageNum=0 
(this link shows all the Data Analyst postings in Canada on LinkedIn within the latest 24 hour (for those looking for other position you can use different links!)

2. The bot would loop through every single record, find relevant elements, and retrieve these data into table format.

![WebP image with fallback](illustration/WebsiteUI-ScrapingElements.webp "WebP Image")

3. The data will be written on to a google sheet file, which is live connected to Tableau Public dashboard that automatically update on any change of the data. https://public.tableau.com/app/profile/hoang.pham3135/viz/LinkedInDataAnalystJobScraping/DATAANALYSTJOBPOSTINGSINCANADA

4. Finally, with Window Task Scheduler, the Python bot will automatically run daily (as a batch file) at a specific time. This will automate the whole process (almost).

## Side Note:

To replicate the boss you will need to lookup and install the most update ChromeDriver version and other python packages, as they keep releasing newer versions.

## Directory


- `README.MD`: Overview and Summary of the project
- `LinkedinScraping.ipynb`: Python bot
- 'R_Script_files`
- `illustration`: snapshot that show example
  - `WebsiteUI-ScrapingElements.webp`
  - `ScrollingLogic.webp`
- `Sample_Output_data.csv`: Sample data that shows the bots output. To see full version please visit: https://docs.google.com/spreadsheets/d/1b06QOCAlYdmRKyW2sp1wGI-I_nU1iilteJPS5lR094c/edit#gid=1100797668
