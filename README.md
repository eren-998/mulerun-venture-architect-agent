# 🚀 Venture Architect AI Agent

[![Platform](https://img.shields.io/badge/Platform-Mulerun-brightgreen?style=for-the-badge)](https://mulerun.com/)
[![n8n](https://img.shields.io/badge/Workflow-n8n-blueviolet?style=for-the-badge)](https://n8n.io/)
[![AI Model](https://img.shields.io/badge/Model-Google%20Gemini-blue?style=for-the-badge)](https://deepmind.google/technologies/gemini/)
[![Research](https://img.shields.io/badge/Data-Tavily%20AI-darkgreen?style=for-the-badge)](https://tavily.com/)
[![API](https://img.shields.io/badge/API-ConvertAPI-orange?style=for-the-badge)](https://www.convertapi.com/)
This repository contains the complete n8n workflow source for the **Venture Architect AI Agent**, an automated business strategy generator deployed on [Mulerun](https://mulerun.com/).

> **➡️ Interact with the live agent:** <https://mulerun.com/@rudntamug659yai/venture-architect-ai-agent>

---

## 🤖 Overview

The Venture Architect AI Agent is designed to bridge the gap between business ideation and strategic execution. It ingests user-defined parameters (idea, market, skills, team size, financial goals) and leverages a multi-step automated workflow to produce a comprehensive 5-section strategic business report.

The agent's core competency is its integration of **real-time web research** to ground its analysis in current market data, competitor landscapes, and realistic investment projections, rather than relying on static training data.

The final output is a dynamically generated, professionally styled HTML report, complete with a downloadable PDF version for offline use.

## ✨ Core Functionality

* **Comprehensive 5-Part Analysis:** Generates a detailed report covering:
    1.  Overview & Viability
    2.  Market & Competition Analysis
    3.  Investment & Earnings Projections
    4.  Actionable Phased Roadmap
    5.  Final Verdict & Strategic Suggestions
* **Real-Time Data Integration:** Utilizes the **Tavily AI** search tool to fetch current market sizes, growth projections (CAGR), competitor pricing models, and emerging industry trends.
* **Data-Driven Alignment Analysis:** Cross-references the user's skills and team size against market requirements and financial goals to identify structural weaknesses, gaps, and strategic opportunities.
* **Realistic Projections:** Delivers honest, data-backed assessments and investment breakdowns (e.g., software, marketing, operational costs) based on current industry standards pulled from live data.
* **Dynamic Report Generation:** Renders the final analysis as a clean, styled HTML page using a custom JavaScript node.
* **Automated PDF Conversion:** Includes a **bonus** feature that automatically processes the generated HTML through **ConvertAPI** to provide a downloadable PDF of the complete strategic roadmap.

## 🛠️ Tech Stack & Workflow Architecture

This agent is built entirely within **n8n** and orchestrates several services:

1.  **Input Handling (Form Trigger):** An n8n Form Trigger node captures the user's structured inputs.
2.  **Data Enrichment (Tavily AI Node):** The user's `Business/Idea` and `Target Market` are passed to the Tavily AI tool. This node performs real-time web research to gather mission-critical data.
3.  **Strategic Analysis Engine (Google Gemini):** The original user inputs *and* the enriched data from Tavily are synthesized into a complex system prompt. This is processed by the **Google Gemini** model to generate the structured 5-part analysis.
4.  **HTML Transformation (Custom JS Node):** The raw JSON/text output from Gemini is parsed and transformed by a custom JavaScript node, which dynamically builds a fully styled, professional HTML document.
5.  **PDF Generation (ConvertAPI HTTP Request):** The generated HTML is sent via an HTTP Request to the **ConvertAPI** endpoint to convert it into a distributable PDF file.
6.  **Response Aggregation (Gemini):** A final Gemini call embeds the PDF URL into the HTML report, creating a "Download PDF" button.
7.  **Final Output:** The complete, interactive HTML report is served to the user.

## 📋 Input Schema (Example Prompts)

**• Business/Idea:** (String) Describe your core business concept.
> *Examples: "Mobile car detailing service," "SaaS tool for freelancer invoicing," "E-commerce store for handmade jewelry"*

**• Target Market:** (String) Specify your target industry, sector, niche, audience, or customer segment.
> *Examples: "Luxury car owners in urban areas," "Small business owners & agencies," "Millennial fitness enthusiasts on Instagram"*

**• Your Current Skills:** (String) List relevant skills you already possess.
> *Examples: "Graphic design, video editing," "Python programming, API development," "No technical skills - beginner"*

**• Current Team Size:** (Integer) Enter the number of people on your team.
> *Examples: "1" (Solo founder), "3"*

**• Goal/Target:** (String) State your financial goal or monthly/yearly revenue target.
> *Examples: "$10,000/month," "$100,000 first year revenue"*

## 📂 Repository Structure

* `Venture Architect Ai Agent.json`: The complete, importable n8n workflow file.
* `README.md`: This documentation.

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
