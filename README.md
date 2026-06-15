# AI Job Hunter

An AI-powered job discovery, analysis, and matching platform built with n8n, Gemini AI, Firecrawl, Notion, and Telegram.

The system automatically collects job opportunities, extracts structured information from job postings, evaluates them against a candidate profile, removes duplicates, and stores qualified opportunities for further review.

---

## Features

### Job Collection

- Submit job URLs through Telegram
- Submit LinkedIn job descriptions through a web form
- Store opportunities in a processing queue
- Prevent duplicate job entries

### Job Scraping

- Automatically scrape job posting content
- Extract clean job descriptions
- Remove navigation, tracking data, images, and irrelevant content
- Normalize data for AI processing

### AI-Powered Analysis

Extracts:

- Company
- Role
- Location
- Employment Type
- Salary Information
- Key Requirements
- Posting Date

Generates structured job metadata using Gemini AI.

### Resume Matching

Analyzes:

- Skills alignment
- Experience alignment
- Technology stack match
- Language requirements
- Location requirements

Generates a numerical match score for each opportunity.

### Opportunity Filtering

Only stores jobs that:

- Meet a minimum match threshold
- Were posted recently
- Pass quality checks

### Data Management

- Store qualified jobs in Notion
- Track application status
- Maintain a database of opportunities
- Prevent duplicate processing

### Notifications

- Telegram notifications
- Success and rejection alerts
- Processing updates

---

## Architecture

```text
Job URL
    ↓
Queue
    ↓
Firecrawl Scraper
    ↓
Content Cleanup
    ↓
Gemini AI Extraction
    ↓
Resume Matching
    ↓
Scoring Engine
    ↓
Notion Database
    ↓
Telegram Notification
```

---

## Tech Stack

### Automation

- n8n

### Artificial Intelligence

- Google Gemini

### Web Scraping

- Firecrawl

### Data Storage

- Notion
- n8n Data Tables

### Notifications

- Telegram Bot API

---

## Key Challenges Solved

### Duplicate Detection

Job URLs are normalized before storage to prevent duplicate entries.

### Concurrency Control

A workflow locking mechanism prevents multiple executions from processing the same queue simultaneously.

### Content Cleaning

Large amounts of noise such as navigation menus, SVG data, tracking information, and image payloads are removed before AI processing.

### Resume Scoring

The system evaluates job postings against a real-world software engineering profile and generates a quantitative match score.

---

## Example Output

```json
{
  "company": "Example Company",
  "role": "Full Stack Engineer",
  "location": "Berlin",
  "type": "Remote",
  "resume_matching": 82,
  "key_requirements": [
    "TypeScript",
    "Node.js",
    "PostgreSQL",
    "Docker"
  ]
}
```

---

## Workflow Highlights

- Automated job collection
- AI-based information extraction
- Resume-to-job matching
- Duplicate prevention
- Queue management
- Workflow locking
- Telegram notifications
- Notion integration

---

## Screenshots

### Workflow

![Workflow](screenshots/workflow.png)

### Notion Database

![Notion Database](screenshots/notion-database.png)

### Match Results

![Match Results](screenshots/match-results.png)

---

## Future Improvements

- Next.js dashboard
- Multi-user support
- Resume upload and management
- AI-generated cover letters
- Interview preparation assistant
- Job recommendation engine
- Analytics and reporting

---

## Motivation

Searching and applying for jobs manually is repetitive and time-consuming.

This project was built to automate the process of collecting, evaluating, and organizing job opportunities using modern AI and automation tools while maintaining full visibility and control over the decision-making process.

---

## Author

**Hussain Hedayati**

- Portfolio: https://hedayat.me
- LinkedIn: https://linkedin.com/in/hedayati1488
- GitHub: https://github.com/hussain1488
