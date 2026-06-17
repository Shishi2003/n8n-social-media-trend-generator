# n8n Social Media Trend Generator

Automated social media trend discovery and AI-powered content generation workflow built with n8n, NewsAPI, Gemini AI, Google Sheets, and Google Docs.

## Features

- Automated trend discovery
- Configurable niche selection
- AI-powered trend analysis
- AI-generated social media content drafts
- Google Sheets approval workflow
- Google Docs draft generation
- Email review and approval process
- Scheduled execution

## Tech Stack

- n8n
- Gemini AI
- NewsAPI
- Google Sheets
- Google Docs
- Gmail

## Workflow Overview

The workflow automatically:

1. Collects news articles from a configurable niche
2. Filters and scores trends
3. Selects the strongest trends
4. Generates social media content using Gemini
5. Stores drafts in Google Sheets
6. Sends drafts for approval
7. Creates Google Docs after approval

## Installation

1. Import the JSON workflow into n8n
2. Configure all credentials
3. Update the Configure Your Niche node
4. Execute the workflow

## Required Credentials

- NewsAPI
- Gemini API
- Google Sheets
- Google Docs
- Gmail

## Documentation

Detailed workflow documentation is available here:

- [Workflow Documentation](docs/WORKFLOW_DOCUMENTATION.md)

## Workflow File

Import the workflow into n8n using:

- `social-media-trend-generator-workflow.json`

## License

MIT License
