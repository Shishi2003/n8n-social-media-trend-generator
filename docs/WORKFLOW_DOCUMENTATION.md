# Social Media Trend Generation Workflow

## Overview – What This Workflow Does

Creating social media content consistently is a time-consuming process. Teams often spend hours searching for trending topics, researching industry news, brainstorming content ideas, drafting posts, and coordinating approvals before anything can be published.

This workflow automates that entire process.

The workflow continuously monitors industry news sources, identifies relevant and trending topics based on a configurable niche, and uses AI to transform those topics into valuable content ideas. For each selected trend, the workflow generates insights, opinions, and discussion questions that can be used for social media engagement.

Instead of immediately publishing AI-generated content, the workflow introduces a human review process. Reviewers can approve or reject trends before content is generated, ensuring that only relevant and high-quality topics move forward.

When a trend is approved, the workflow automatically creates a Google Document containing the generated content draft. The draft then goes through a second approval stage where reviewers can approve or reject the final content before publication.

Throughout the process, Google Sheets acts as a centralized tracking system, maintaining the status of every trend and content draft. This allows teams to clearly see which trends are waiting for review, which drafts are being created, which posts have been approved, and which have been rejected.

The result is a complete content generation pipeline that combines:

- Automated trend discovery
- AI-powered content creation
- Human quality control
- Workflow tracking

into a single system.

---

## Who It's For

This workflow is designed for individuals and teams that regularly create industry-focused content and want to reduce the manual effort involved in researching and drafting posts.

### Marketing Teams
Organizations that need a constant flow of content ideas based on current industry developments.

### Social Media Managers
Professionals responsible for finding trending topics, creating content, and managing approval processes.

### Content Creators
Individuals who want AI assistance in discovering content opportunities and generating draft material.

### Agencies
Marketing and automation agencies that manage content generation for multiple clients and industries.

### Business Owners
Companies that want to establish thought leadership by consistently posting about relevant industry trends.

---

## Requirements

Before using this workflow, ensure you have:

- NewsAPI account and API key
- Gemini API access
- Google Sheets access
- Google Docs access
- Gmail account for approvals
- n8n instance

---

## Required Nodes

| Node | Purpose |
|--------|---------|
| Schedule Trigger | Starts the workflow automatically at configured intervals |
| Configure Your Niche (Set Node) | Allows users to define niche, keywords, language, region, and number of articles to fetch |
| HTTP Request | Retrieves trending articles from NewsAPI |
| Code Nodes | Clean, format, and prepare article data for processing |
| Gemini AI | Generates insights, opinions, questions, and social media content drafts |
| Google Sheets | Stores trends, approvals, draft statuses, and document metadata |
| IF Nodes | Controls workflow decisions based on approval statuses |
| Google Docs | Creates and stores AI-generated content drafts |
| Gmail | Sends review and approval emails to reviewers |
| Update Sheet Nodes | Updates statuses and tracking information throughout the workflow |

---

## How to Use It

### Step 1: Configure Your Niche

Open the **Configure Your Niche** node and update:

- niche
- keywords
- language
- region
- maxResults

**Example**

```text
Niche: AI Automation

Keywords:
("agentic AI" OR "AI agents" OR "workflow automation")
```

### Step 2: Configure Credentials

Add the required credentials:

- NewsAPI API Key
- Gemini API Key
- Google Sheets Credentials
- Google Docs Credentials
- Gmail Credentials

### Step 3: Configure Google Assets

Update:

- Spreadsheet ID
- Sheet Name
- Google Drive Folder

### Step 4: Test the Workflow

Run the workflow manually once and verify:

- Articles are fetched successfully
- Trends are stored in Google Sheets
- AI-generated content is produced correctly
- Draft documents are created successfully

### Step 5: Activate the Workflow

After successful testing, activate the workflow.

The workflow will automatically:

1. Discover trends
2. Generate AI insights
3. Store trends for review
4. Create drafts for approved trends
5. Send approval emails
6. Track the complete content lifecycle

No additional manual intervention is required except for content review and approval decisions.

---

## How It Works

### Step 1: Trend Discovery

The workflow begins automatically on a scheduled interval.

Using configurable keywords and search criteria, it searches industry news sources through NewsAPI to identify recent and relevant articles related to the selected niche.

Example niches:

- AI Automation
- Cybersecurity
- FinTech
- SaaS
- Cloud Computing

The niche and keywords can be changed without modifying the workflow itself.

### Step 2: Article Processing

The retrieved articles are cleaned and processed.

The workflow extracts useful information such as:

- Article title
- Source
- Publication date
- Article URL
- Content summary

Duplicate or irrelevant information can be filtered out during this stage.

### Step 3: AI-Powered Trend Analysis

Gemini AI analyzes the selected article and generates:

#### Insight
A professional observation explaining why the trend matters.

#### Opinion
A thought-provoking perspective designed to encourage discussion.

#### Question
An engaging question that can be used to spark audience interaction.

This transforms a news article into a potential social media conversation.
