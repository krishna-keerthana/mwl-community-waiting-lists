# mwl-community-waiting-lists
Analysis of MWL community health services waiting lists, Oct 2025 to Sep 2026.
# MWL Community Waiting Lists (Oct 2025 – Sep 2026)

## Why I did this
I wanted to understand community services data before applying for a Senior Information Analyst role in community services at Mersey and West Lancashire Teaching Hospitals (MWL). My earlier project used RTT data, which covers hospital care, so this was a chance to work with a different NHS dataset and see what MWL's community waiting lists look like.

## Data
- Source: NHS England, Community Health Services (CHS) SitRep, monthly publication
- Period: October 2025 to September 2026 (12 monthly files)
- Provider: Mersey and West Lancashire Teaching Hospitals NHS Trust (code RBN)
- Comparison: England totals for the same months and services

## What I did
I used Python (pandas and matplotlib) in Google Colab. Each monthly file has one tab for the total waiting list and eight tabs for wait bands, with a separate column for each service. I looped through every file and tab, kept only the MWL and England rows, and reshaped the data into one long table with a row per month, service and wait band. Then I worked out the percentage of people waiting over 18 and over 52 weeks, and compared MWL's community paediatrics with England for the same service.

Waiting lists are a monthly snapshot, so I never added months together.

## Findings
- MWL's community waiting list fell from 919 in October 2025 to 534 in September 2026, a drop of about 42%.
- Community paediatrics is the biggest list, with 301 of the 534 people waiting (56%) in September 2026.
- About half of the children waiting for community paediatrics (50.5%) had waited over 18 weeks, and 15.3% over 52 weeks.
- This is well below England for the same service, where 75% had waited over 18 weeks and 45.6% over 52 weeks.
- Adult services had almost no long waits. Only continence and colostomy support had people waiting over 18 weeks (4.9%).

## Data quality notes
- **August 2026:** MWL's submission showed 0 for every service, even though around 300 children were waiting for community paediatrics in the months before and after. The file also showed that no organisation in Cheshire and Merseyside failed to submit that month. I treated this as a reporting error and left August out of the trend.
- **Intermediate care and reablement:** a total is reported (23 in September 2026) but there is no wait band breakdown, so the bands don't always add up to the total.
- **Comparisons:** I compared the same service for MWL and England, because MWL reports a much smaller mix of services and an overall comparison would not be fair.
- **Status:** NHS England describes this data as unvalidated management information, so figures may be revised.

## Charts
![MWL community waiting list trend](mwl_trend.png)

![Community paediatrics: MWL vs England](paediatrics_vs_england.png)

## Files
- `mwl_community_waits.ipynb`: the notebook with all the code
- `mwl_vs_england_chs.csv`: the combined, cleaned data for MWL and England
- `mwl_trend.png` and `paediatrics_vs_england.png`: the charts

## Tools
Python (pandas, matplotlib), Google Colab, Excel
