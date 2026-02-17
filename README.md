## 1️⃣ Problem Statement

Sales teams, founders, and agencies often need:
- Local business leads
- Niche-specific company lists
- Contact details from public sources

Manually collecting this information from Google search results, directories, and company websites is:
- Repetitive
- Slow
- Hard to scale
- Prone to copy-paste errors

💡 Solution

The Lead Scraper Agent automates:
- Searching businesses by niche + location
- Extracting website URLs
- Scraping contact details (email, phone, address if available)
- Returning clean structured JSON or CSV

This allows teams to:
- Generate lead lists quickly
- Save hours of manual research
- Build outbound pipelines faster

## 2️⃣ Architecture Diagram

![Alt text](https://github.com/amunim12/Lead_Scraper_Agent/blob/main/Lead%20Scraper%20Agent.png)


## 3️⃣ Agent Loop Explanation

1️⃣ Plan
The workflow prepares:

- Search query format
Example:
"Plumbing companies in Chicago with website"
- Number of results to fetch
- Pagination logic

2️⃣ Act
n8n executes:
- Search API request
- Extracts business URLs
- Sends HTTP requests to each website
- Scrapes HTML content

3️⃣ Observe
The workflow parses:
- Email addresses (regex)
- Phone numbers
- Address if present

It checks:
- Empty responses
- Invalid websites
- Duplicate entries

4️⃣ Reflect
- Basic workflow checks:
- Did we reach desired lead count?
- Did scraping fail for some URLs?
- Should we retry failed nodes?

If errors occur → retry logic triggers.

