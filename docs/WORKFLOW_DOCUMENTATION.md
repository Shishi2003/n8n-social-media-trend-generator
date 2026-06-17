Social media trend generation Workflow
Overview – What This Workflow Does
Creating social media content consistently is a time-consuming process. Teams often spend hours searching for trending topics, researching industry news, brainstorming content ideas, drafting posts, and coordinating approvals before anything can be published.
This workflow automates that entire process.
The workflow continuously monitors industry news sources, identifies relevant and trending topics based on a configurable niche, and uses AI to transform those topics into valuable content ideas. For each selected trend, the workflow generates insights, opinions, and discussion questions that can be used for social media engagement.
Instead of immediately publishing AI-generated content, the workflow introduces a human review process. Reviewers can approve or reject trends before content is generated, ensuring that only relevant and high-quality topics move forward.
When a trend is approved, the workflow automatically creates a Google Document containing the generated content draft. The draft then goes through a second approval stage where reviewers can approve or reject the final content before publication.
Throughout the process, Google Sheets acts as a centralized tracking system, maintaining the status of every trend and content draft. This allows teams to clearly see which trends are waiting for review, which drafts are being created, which posts have been approved, and which have been rejected.
The result is a complete content generation pipeline that combines automated trend discovery, AI-powered content creation, human quality control, and workflow tracking into a single system.
Who It's For :
This workflow is designed for individuals and teams that regularly create industry-focused content and want to reduce the manual effort involved in researching and drafting posts.
Typical users include:


Marketing Teams
Organizations that need a constant flow of content ideas based on current industry developments.
Social Media Managers
Professionals responsible for finding trending topics, creating content, and managing approval processes.
Content Creators
Individuals who want AI assistance in discovering content opportunities and generating draft material.
Agencies
Marketing and automation agencies that manage content generation for multiple clients and industries.
Business Owners
Companies that want to establish thought leadership by consistently posting about relevant industry trends.
Required Nodes :
The workflow uses the following nodes:
Node
Purpose
Schedule Trigger
Starts the workflow automatically at configured intervals
Configure Your Niche (Set Node)
Allows users to define niche, keywords, language, region, and number of articles to fetch
HTTP Request
Retrieves trending articles from NewsAPI
Code Nodes
Clean, format, and prepare article data for processing
Gemini AI
Generates insights, opinions, questions, and social media content drafts
Google Sheets
Stores trends, approvals, draft statuses, and document metadata
IF Nodes
Controls workflow decisions based on approval statuses
Google Docs
Creates and stores AI-generated content drafts
Gmail
Sends review and approval emails to reviewers
Update Sheet Nodes
Updates statuses and tracking information throughout the workflow


How to Use It :
Step 1: Configure Your Niche
Open the Configure Your Niche node and update:
niche
keywords
language
region
maxResults
Example:
Niche: AI Automation
Keywords:
("agentic AI" OR "AI agents" OR "workflow automation")
Step 2: Configure Credentials
Add the required credentials:
NewsAPI API Key
Gemini API Key
Google Sheets Credentials
Google Docs Credentials
Gmail Credentials
Step 3: Configure Google Assets
Update:
Spreadsheet ID
Sheet Name
Google Drive Folder
Step 4: Test the Workflow
Run the workflow manually once and verify:
Articles are fetched successfully
Trends are stored in Google Sheets
AI-generated content is produced correctly
Draft documents are created successfully
Step 5: Activate the Workflow
After successful testing, activate the workflow.
The workflow will automatically:
Discover trends
Generate AI insights
Store trends for review
Create drafts for approved trends
Send approval emails
Track the complete content lifecycle
No additional manual intervention is required except for content review and approval decisions.
How It Works :
The workflow follows a structured content creation lifecycle.
Step 1: Trend Discovery
The workflow begins automatically on a scheduled interval.
Using configurable keywords and search criteria, it searches industry news sources through NewsAPI to identify recent and relevant articles related to the selected niche.
For example:
AI Automation
Cybersecurity
FinTech
SaaS
Cloud Computing
The niche and keywords can be changed without modifying the workflow itself.
Step 2: Article Processing
The retrieved articles are cleaned and processed.
The workflow extracts useful information such as:
Article title
Source
Publication date
Article URL
Content summary
Duplicate or irrelevant information can be filtered out during this stage.
Step 3: AI-Powered Trend Analysis
Gemini AI analyzes the selected article and generates additional context.
The workflow creates:
Insight
A professional observation explaining why the trend matters.
Opinion
A thought-provoking perspective designed to encourage discussion.
Question
An engaging question that can be used to spark audience interaction.
This transforms a news article into a potential social media conversation.
Step 4: Trend Review Queue
The generated trend information is stored in Google Sheets.
Each trend enters the review queue with:
Status = Pending
Draft Status = NotCreated

At this stage, no content has been generated yet.
A reviewer manually evaluates whether the trend is relevant to the organization.
Step 5: Trend Approval
A reviewer updates the status of the trend.
Possible outcomes:
Approved
The workflow proceeds to content generation.
Rejected
The workflow stops processing that trend and records the rejection.
This ensures human oversight before any AI-generated content is created.
Step 6: Draft Creation
When a trend is approved, the workflow automatically generates a social media draft using Gemini AI.
The workflow then:
Creates a Google Document
Inserts the generated content
Saves the document link
Updates tracking information
The draft status becomes:
Draft Status = Pending

This indicates that a draft exists and is waiting for final review.
Step 7: Content Review
The generated draft is sent to reviewers through an approval process.
Reviewers evaluate:
Content quality
Accuracy
Brand alignment
Tone and messaging
Possible outcomes:
Approved
The draft is considered ready for publishing.
Rejected
The draft is marked for revision or removal.
Step 8: Lifecycle Tracking
Google Sheets acts as the workflow dashboard.
Every trend progresses through clearly defined stages:
Trend Found
    ↓
Pending Review
    ↓
Approved / Rejected
    ↓
Draft Generated
    ↓
Pending Draft Review
    ↓
Approved / Rejected

This allows anyone on the team to instantly understand the current state of every content idea.

Inputs & Outputs :
Inputs
The workflow requires:
Niche configuration
Search keywords
News articles from NewsAPI
Human approval decisions
Outputs
The workflow produces:
Trending topic database
AI-generated insights
AI-generated opinions
AI-generated discussion questions
Google Docs drafts
Approval records
Content lifecycle tracking information
By the end of the process, a raw news article has been transformed into a reviewed, approved, and trackable content asset ready for publication.
Configuration Guide :
Before running the workflow, update the following configurations:
Configure Your Niche Node
Update:
niche
keywords
language
region
maxResults
Example:
Niche: AI Automation
Keywords:
("agentic AI" OR "AI agents" OR "workflow automation")
NewsAPI
Add your NewsAPI API key in the HTTP Request node.
Google Sheets
Update:
Spreadsheet ID
Sheet Name
Google Docs
Update:
Google Drive Folder
Document Permissions
Gmail
Configure:
Gmail Credentials
Reviewer Email Address
Gemini AI
Configure:
Gemini API Key
Model Selection (if required)
Troubleshooting :
No Articles Returned
Possible Causes:
Invalid NewsAPI key
Keywords are too restrictive
NewsAPI quota exceeded
Solution:
Verify API key
Test broader keywords (e.g., "AI")
Check NewsAPI account limits
Google Sheet Not Updating
Possible Causes:
Incorrect Spreadsheet ID
Missing permissions
Column name mismatch
Solution:
Verify Sheet permissions
Refresh node mappings
Confirm column names
Draft Document Not Created
Possible Causes:
Google Docs credential issue
Missing Drive permissions
Solution:
Reconnect Google credentials
Verify folder access
Approval Email Not Sent
Possible Causes:
Gmail credential expired
Incorrect recipient email
Solution:
Reconnect Gmail account
Verify recipient address
Workflow Processes Incorrect Rows
Possible Causes:
Missing filters in Get Rows node
Solution:
Ensure filters are:
Status = Approved
AND
DraftStatus = Pending


