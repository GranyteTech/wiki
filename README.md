# wiki
contains architecture/governance documents on how this project will be built.

**Content**
```bash
├── Objective
├── Architecture
│   ├── Platform
│   ├── Structure
│   └── Tech Stack
└── Data sources
    ├── Financial sources 
    └── Social Sources
```

## Objective of GranyteTech

data analytics company which collects:
- financial data
- Nominal data

which will generate alpha based on the sentiment from Nominal data to understand the market's growth
while minimising cost on GCP. 

The inference will try to predict short term(roughly 3-6 months ahead) investments on how well the security will do.

### Costs

- Nominal data will be quantified by it's sentiment and aggregated to reduce training cost.
- All Data will be accessed from GCS buckets (collecting data from Big Query is too costly).
- All GCS bucket data will be partitioned into months (to reduce querying cost: Operation A costs).
- All APIs will use pagination to limit usage.
- Data collection will be batched by weekly or monthly ingestions. (cheaper than day/streaming).

### Failsafes & Products

If the project is unsuccessful, it can still be slavaged with 2 failsafes, which will deliver well structured, organised data to clients.

#### Failsafe 1: Strucuted finanical data

Low risk, low/none reward

Fast to implement, however multiple companies provide services such as this.

#### Failsafe 2: Strucuted nominal data

**extremely high risk**, med reward

A few services will collect data from multiple sources in a structured manner under one topic.

## Architecture

### Platform 

Google cloud platform (**GCP**) will be the main platform used to develop this service.

### Diagram

![UML diagram of general architecture](/diagrams/general_diagram.png)

### Tech Stack

#### DevOps

Infrastructure handler (any one):
- Terraform
- Pulumi
- Deployment manager (not recommended)

Python3 (Basic, able to complete easy leetcode questions):
- pytest
- unittest
- pulumi

General:
- Docker/Containerd
- GCP: Cloud Build
- GCP: Secret Manager 
- GCP: IAM, roles, policies & Service accounts
- Good understanding of Scalable architecture

#### DE, DS, MLE

Python3 (Basic, able to complete easy leetcode questions):
- jupyter notebook
- numpy
- pandas
- pytorch/keras (not chosen as of yet)

General:
- Docker/Containerd
- GCP: Cloud Build
- GCP: Cloud Run/GCP: Cloud Function
- GCP: Big Query
- SQL (Basic, able to complete easy leecode questions)
- Understand how transformers work (but do not need to know how to program them)
- Know how to setup GPU acceleration

#### SWE, BED (in late stages)

JavaScript (Basic, able to complete easy leetcode questions):
- typescript
- node js 
- express

Python3 (Basic, able to complete easy leetcode questions):
- Django
- Flask 

General:
- Docker/Containerd
- GCP: Cloud Build
- GCP: App Engine
- Good understanding how to build 

##  Data sources

This will be focused around using free api sources

### Financial Data 

Majority would consist of multiple sources of macro data + one source of mirco data

#### Yahoo Finance

- **Docs:** https://pypi.org/project/yfinance/
- **Format:** JSON
- **Notes:** Data delayed by a day, based on web scraping.

#### World Trade Organization

- **Docs:** https://apiportal.wto.org/docs/services
- **Format:** ?
- **Notes:** *work in progress* Require login/API key

#### World Bank

- **Docs:** https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation
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

