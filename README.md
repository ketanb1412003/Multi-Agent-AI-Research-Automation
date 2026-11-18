# Multi-Agent AI Research & Report Automation System

An AI-powered research and report generation system built using **n8n, Google Gemini, Tavily API, PDFBolt, and Google Drive**. The system automates the complete research process, from understanding a user's query and collecting information from the web to analyzing sources, generating a structured report, reviewing its quality, and delivering the final PDF.

---

## Project Overview

The **Multi-Agent AI Research & Report Automation System** is designed to simplify and automate time-consuming research and report-writing tasks.

Instead of manually searching multiple websites, organizing information, writing reports, and converting them into PDF documents, users can submit a research topic and let the automated workflow handle the process.

The system uses multiple AI agents, each responsible for a specific task, to produce structured, organized, and research-based reports.

The entire process is orchestrated through n8n, with external APIs providing web search, AI processing, PDF generation, and cloud storage capabilities.

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

---

## System Architecture

The project follows a multi-stage workflow architecture in which different AI agents and automation nodes work together.

### Workflow Pipeline

1. **User Query:** Accepts the research topic through the n8n chat interface.
2. **Planner Agent:** Understands the query and generates a structured research plan.
3. **Tasks Loop:** Processes individual research tasks.
4. **Web Researcher:** Collects relevant web information using the Tavily Search API.
5. **Edit Fields:** Maps and prepares research data for further processing.
6. **Source Analyzer:** Extracts source domains, classifies sources, and assigns confidence scores.
7. **Aggregate 1:** Combines collected research results.
8. **Research Package Builder:** Organizes collected information into a structured research package.
9. **Split Out:** Separates research sections for individual analysis.
10. **Gemini Research Analyst:** Analyzes each research section and extracts important findings.
11. **Aggregate 2:** Combines the analyzed research sections.
12. **Writer Agent:** Generates a structured research report.
13. **Review Agent:** Evaluates the generated report for completeness, consistency, readability, and unsupported claims.
14. **Merge:** Combines the generated report with its review results.
15. **HTML Generation:** Converts the structured report into HTML format.
16. **PDF Generation:** Uses PDFBolt to convert the HTML report into a PDF document.
17. **Google Drive Integration:** Uploads the generated PDF to Google Drive.
18. **Final Response:** Returns the generated report link to the user.

### Architecture Diagram

The system consists of five major stages:

- Workflow Orchestration
- Web Research and Source Collection
- Research Processing and Analysis
- Report Generation and Quality Review
- Document Generation and Delivery

---

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

---

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
- Provides research material for the source analysis stage.

### 3. Gemini Research Analyst

- Analyzes the collected research information.
- Extracts key findings, facts, statistics, and methodologies.
- Identifies challenges and future directions.
- Examines conflicting evidence where available.
- Evaluates source quality and confidence.
- Organizes findings into structured research sections.

### 4. Writer Agent

- Converts analyzed research data into a professional report.
- Generates the title, introduction, main sections, conclusion, recommendations, and references.
- Follows the instructions generated during the planning stage.
- Uses the supplied research information rather than inventing unsupported facts.

### 5. Review Agent

- Reviews the generated report.
- Checks completeness, consistency, and readability.
- Identifies unsupported claims and other issues.
- Provides a review score and verdict.
- Evaluates whether the report is ready for document generation.

---

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

---

## Repository Structure

The repository is organized into the following directories:

```text
Multi-Agent-AI-Research-Automation/
│
├── workflow/
│   └── research-agent-workflow.json
│
├── screenshots/
│   ├── Complete Agent.png
│   ├── Web  Researcher Node.png
│   └── Other screenshots...
│
├── documentation/
│   └── project-report.pdf
│
├── Codes/
│   └── All node's codes.txt
│
├── .gitignore
└── README.md
```

**Note:** The filenames above are examples. Refer to the actual files available in the repository.

---

## Screenshots

Screenshots of the workflow and its important components are included below.

### Complete n8n Workflow

![Complete Workflow](screenshots/Complete%20Agent.png)

### Web Researcher Node

![Web Researcher Node](screenshots/Web%20%20Researcher%20Node.png)

### Other Workflow Components

Add additional screenshots here to demonstrate the Planner Agent, Source Analyzer, Research Analyst, Writer Agent, Review Agent, and final PDF output.

---

## Installation and Setup

Follow these steps to configure and run the project on your own n8n instance.

### 1. Prerequisites

Before starting, make sure you have:

- An n8n instance (local installation or n8n Cloud).
- A Google account.
- A Google Gemini API key.
- A Tavily API key.
- PDFBolt API access and an API key.
- Access to Google Drive.

Some services may require separate account registration, usage limits, or paid API access.

### 2. Clone the Repository

Open your terminal and execute:

```bash
git clone https://github.com/YOUR_USERNAME/Multi-Agent-AI-Research-Automation.git

cd Multi-Agent-AI-Research-Automation
```

Replace `YOUR_USERNAME` with your GitHub username.

### 3. Open n8n

You can use either:

- **n8n Cloud:** Sign in to your n8n Cloud account.
- **Local n8n:** Start your locally installed n8n instance.

If you need to install n8n locally using npm:

```bash
npm install -g n8n
n8n
```

Open the local n8n interface at:

```text
http://localhost:5678
```

### 4. Import the Workflow

1. Open your n8n instance.
2. Navigate to the Workflows section.
3. Select the option to import a workflow from a file.
4. Select `research-agent-workflow.json` from the `workflow/` directory.
5. Open the imported workflow.
6. Review the nodes and their configurations.

### 5. Configure API Credentials

The workflow requires credentials for the following services.

#### Google Gemini

1. Obtain an API key from Google AI Studio.
2. Open the Credentials section in n8n.
3. Create the required Google Gemini credentials.
4. Select the configured credentials in the Gemini AI nodes.
5. Verify that the selected model is available to your account.

#### Tavily API

1. Create an account on Tavily.
2. Generate an API key.
3. Configure the API key for the Web Researcher HTTP Request node using a secure n8n credential or another supported secure configuration.
4. Verify that the request is correctly authenticated.

#### PDFBolt

1. Create an account on PDFBolt.
2. Obtain your API key.
3. Configure the required authentication in the PDFBolt HTTP Request nodes.
4. Verify that the HTML-to-PDF conversion request is configured correctly.

#### Google Drive

1. Open the Credentials section in n8n.
2. Create and connect your Google Drive credentials.
3. Authenticate your Google account.
4. Ensure that the connected account has permission to upload files.
5. Configure the destination Google Drive folder in the workflow.

### 6. Verify Workflow Configuration

Before executing the workflow:

- Check that all required credentials are connected.
- Verify the Tavily API request configuration.
- Check the Gemini model connections.
- Verify the PDFBolt request and response configuration.
- Confirm Google Drive authentication and destination folder settings.
- Ensure that the Chat Trigger and response nodes are correctly configured.

### 7. Execute the Workflow

1. Save the imported workflow.
2. Open the n8n chat interface associated with the Chat Trigger node.
3. Submit a research topic or question.
4. Allow the workflow to execute the research and analysis stages.
5. Wait for report generation, review, and PDF conversion.
6. Once execution completes successfully, access the generated PDF using the Google Drive link returned by the workflow.

---

## Example Usage

A user can submit a research query such as:

```text
Research the applications, advantages, challenges,
and future scope of Artificial Intelligence in healthcare.
```

The workflow then:

1. Creates a structured research plan.
2. Searches the web for relevant information.
3. Collects and classifies sources.
4. Analyzes the collected research material.
5. Generates a structured report.
6. Reviews the report for quality and completeness.
7. Converts the report into a PDF.
8. Uploads the PDF to Google Drive.
9. Returns the generated report link.

---

## Troubleshooting

| Problem | Possible Solution |
|---|---|
| Gemini authentication error | Verify the API key and Gemini credentials in n8n. |
| Tavily request fails | Check the API key, request configuration, and available API credits. |
| PDF generation fails | Verify PDFBolt credentials and the HTML input. |
| Google Drive upload fails | Check Google authentication, folder permissions, and destination configuration. |
| Workflow execution stops | Inspect the failed node and its execution details in n8n. |
| Missing credential error | Reconnect the required service credentials in n8n. |

---

## Security

- API keys and credentials are not included in this repository.
- Store API keys securely using n8n Credentials.
- Never upload API keys, access tokens, passwords, or private credentials to GitHub.
- Do not share private credential files or authentication details.
- Configure your own API credentials before running the workflow.
- Review exported workflow JSON files before publishing them to ensure they do not contain sensitive information.

---

## Future Scope

- Add support for multiple research sources and search providers.
- Improve source reliability and verification.
- Introduce customizable report templates.
- Support additional document formats such as DOCX.
- Add multilingual research and report generation.
- Improve report evaluation and fact-checking.
- Implement advanced error handling and workflow monitoring.
- Introduce user-specific report customization.

---

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
- Designing and managing multi-stage automation workflows.

---

## Author

**Ketan Bansal**

B.Tech – Information Technology

Swami Keshvanand Institute of Technology, Management & Gramothan (SKIT), Jaipur

---

## Acknowledgement

This project was developed as part of industrial training to gain practical experience in AI automation, multi-agent systems, API integration, workflow orchestration, and automated report generation.

If you find this project useful, consider giving this repository a star!
