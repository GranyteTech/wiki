# wiki
contains architecture/governance documents 


**Content**
```bash
├── Objective
├── Data sources
│   ├── Financial sources 
│   └── Social Sources
└── Architecture
    ├── Platform
    ├── Tech stack
    └── Structure
```


## Objective of GranyteTech

data analytics company which collects:
- financial data
- social media data

which will generate alpha based on the sentiment from social media data to understand the market's growth.

##  Data sources

This will be focused around using free api sources

### Financial Data 

Majority would consist of multiple sources of macro data + one soruce of mirco data

#### Yahoo Finance

- **Docs:** https://pypi.org/project/yfinance/
- **Format:** JSON
- **Notes:** Data delayed by a day, based on web scraping.

#### World Trade Organization

- **Docs:** https://apiportal.wto.org/docs/services
- **Format:** ?
- **Notes:** *work in progress* Require login/API key

#### World Bank

- **Docs:** https://datahelpdesk.worldbank.org/knowledgebase/- articles/889392-about-the-indicators-api-documentation
- **Format:** XML
- **Notes:** *work in progress* still need exploring 

#### Index Monetary Fund

- **Docs:** https://datahelp.imf.org/knowledgebase/articles/667681-using-json-restful-web-service
- **Format:** XML
- **Notes:** *work in progress* still need exploring 

#### US BUREAU OF LABOUR STATISTICS

- **Docs:** https://www.bls.gov/developers/api_python.htm
- **Format:** JSON
- **Notes:** *work in progress* Require login/API key

### Social media

#### YouTube

- **Docs:** https://developers.google.com/youtube/v3/docs
- **Format:** JSON
- **Notes:** Free* upto 10,000 calls per day.

#### Telegram

- **Docs:** https://docs.telethon.dev/en/latest/index.html
- **Format:** JSON
- **Notes:** Free* requires Phone number

#### Twitter

- **Docs:** https://developers.google.com/youtube/v3/docs
- **Format:** JSON
- **Notes:** Free* upto 500,000 calls per month.

#### Reddit

- **Docs:** https://www.reddit.com/r/TheoryOfReddit/wiki/collecting_data
- **Format:** JSON
- **Notes:** *work in progress* add '.json' suffix to url returns the json data of the page.

## Architecture

### Platform 

Google cloud platform (**GCP**) will be the main platform used to develop this service.

### Tech Stack

*work in progress*

### Diagram

*UML in progress*