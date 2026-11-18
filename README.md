# Multi-Agent AI Research & Report Automation System

An AI-powered research and report generation system built using **n8n, Google Gemini, Tavily API, PDFBolt, and Google Drive**. The system automates the complete research process, from understanding a user's query and collecting information from the web to analyzing sources, generating a structured report, reviewing its quality, and delivering the final PDF.

## Project Overview

The Multi-Agent AI Research & Report Automation System is designed to simplify and automate time-consuming research and report-writing tasks.

Instead of manually searching multiple websites, organizing information, writing reports, and converting them into PDF documents, users can submit a research topic and let the automated workflow handle the process.

The system uses multiple AI agents, each responsible for a specific task, to produce structured and organized research reports.

## Objectives

- Automate web-based research using AI agents.
- Break user queries into smaller research tasks.
- Collect relevant information using the Tavily Search API.
- Analyze and classify collected sources.
- Generate structured research summaries using Google Gemini.
- Automatically write and review research reports.
- Convert generated reports into PDF documents.
- Upload the final PDF to Google Drive.
- Provide the generated report link to the user.

## System Architecture

The project follows a multi-stage workflow architecture in which different AI agents and automation nodes work together.

### Workflow Pipeline

1. **User Query:** Accepts the research topic from the user.
2. **Planner Agent:** Understands the query and generates a structured research plan.
3. **Track Loop:** Processes individual research tasks.
4. **Web Researcher:** Collects relevant web information using Tavily Search API.
5. **Source Analyzer:** Extracts source domains, classifies sources, and assigns confidence scores.
6. **Research Package Builder:** Organizes collected research information into a structured package.
7. **Gemini Research Analyst:** Analyzes each research section and extracts important findings.
8. **Writer Agent:** Generates a structured research report using the analyzed information.
9. **Review Agent:** Evaluates the generated report for completeness, consistency, readability, and unsupported claims.
10. **HTML Generation:** Converts the structured report into HTML format.
11. **PDF Generation:** Uses PDFBolt to convert the HTML report into a PDF document.
12. **Google Drive Integration:** Uploads the generated PDF to Google Drive.
13. **Final Response:** Returns the generated report link to the user.

## Technologies Used

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Google Gemini | AI-powered planning, research analysis, writing, and review |
| Tavily API | Web search and information collection |
| JavaScript | Custom logic using n8n Code nodes |
| Structured Output Parser | Generates structured AI responses |
| HTML | Research report formatting |
| PDFBolt API | HTML-to-PDF conversion |
| Google Drive | Storage and delivery of generated reports |

## AI Agents

### 1. Planner Agent
- Understands the user's research query.
- Identifies the main research goal and topic.
- Breaks the topic into multiple research tasks.
- Generates writing and review instructions.
- Produces structured JSON output.

### 2. Web Researcher
- Searches the web using the Tavily API.
- Retrieves relevant search results for each research task.
- Collects information and source URLs for further analysis.

### 3. Gemini Research Analyst
- Analyzes the collected research information.
- Extracts key findings, facts, statistics, and methodologies.
- Identifies challenges and future directions.
- Evaluates source quality and confidence.
- Organizes findings into structured research sections.

### 4. Writer Agent
- Converts analyzed research data into a professional report.
- Generates the title, introduction, main sections, conclusion, recommendations, and references.
- Uses the supplied research information rather than inventing unsupported facts.

### 5. Review Agent
- Reviews the generated report.
- Checks completeness, consistency, and readability.
- Identifies unsupported claims and other issues.
- Provides a review score and verdict.

## Key Features

- Automated research planning.
- Multi-agent AI workflow.
- Automated web information collection.
- Source classification and confidence scoring.
- Structured research analysis.
- AI-powered report generation.
- Automated report quality review.
- HTML-based report formatting.
- Automatic PDF generation.
- Google Drive integration.
- Automated report link delivery.


## Installation and Setup

### Prerequisites

- An n8n instance (local or cloud).
- Google Gemini API key.
- Tavily API key.
- PDFBolt API access.
- Google Drive account and configured credentials.

### Steps

1. Clone this repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/Multi-Agent-AI-Research-Automation.git
   ```

2. Open your n8n instance.

3. Import the workflow JSON file into n8n, if included in the repository.

4. Configure the required credentials:
   - Google Gemini
   - Tavily API
   - PDFBolt API
   - Google Drive

5. Verify the API connections and workflow node configurations.

6. Execute the workflow and provide a research topic.

7. Once execution is complete, access the generated PDF through the returned Google Drive link.

**Note:** API credentials are not included in this repository. Users must configure their own credentials before executing the workflow.

## Security

- API keys and credentials should be stored securely in n8n Credentials.
- Do not upload API keys, access tokens, passwords, or private credentials to GitHub.
- Use environment variables or secure credential management wherever applicable.

## Future Scope

- Add support for multiple research sources and search providers.
- Improve source reliability and verification.
- Introduce customizable report templates.
- Support additional document formats such as DOCX.
- Add multilingual research and report generation.
- Improve report evaluation and fact-checking.
- Implement advanced error handling and workflow monitoring.

## Learning Outcomes

Through this project, practical experience was gained in:

- Workflow automation using n8n.
- Building multi-agent AI systems.
- Integrating Large Language Models using APIs.
- Web research automation.
- Structured data processing using JavaScript.
- Automated document generation.
- Third-party API integration.
- Cloud storage and file delivery.

## Author

**Ketan Bansal**

B.Tech – Information Technology

Swami Keshvanand Institute of Technology, Management & Gramothan (SKIT), Jaipur

## Acknowledgement

This project was developed as part of industrial training to gain practical experience in AI automation, multi-agent systems, API integration, and automated report generation.

If you find this project useful, consider giving this repository a star!
