# PRO-FINANCE DIAMOND V3.3 + AI

A smart, privacy-first personal finance management system built to solve real-world budgeting needs. 

[Live Demo Link Here - https://shovalnaor.github.io/Pro-Finance-AI-Budget-Tool/] 

---

### About This Project

I'm an Industrial Engineering and Management graduate who got tired of juggling between different banking apps and Excel sheets just to understand where my money goes each month. After trying a bunch of personal finance apps that either cost too much, had terrible UX, or didn't support Hebrew properly, I decided to build my own solution.

This project started as a simple expense tracker and evolved into a full financial management system over several months of daily use and iteration. Now in its "Diamond V3.3" release, it is designed perfectly for the Israeli market (Hebrew/Shekels/local bank imports) while also offering full English translation and dark/light modes.

The core problem I wanted to solve was simple: I needed to know if I'm about to overspend BEFORE it happens, not after reviewing my credit card statement at the end of the month. I also wanted something that respects my privacy by keeping all data locally on my device.

### Main Features

The system includes several modules I built as I identified needs in my daily usage:

* **The Dashboard & Financial Health:** Gives you an immediate snapshot of your financial situation. Total income and expenses, current balance, and real-time budget tracking bars. I recently built a dynamic "Financial Health Score" that grades your current month's performance based on your savings rate and budget discipline.
* **AI Financial Advisor (NEW):** I integrated the Google Gemini API to act as an objective, strict financial advisor. It analyzes your spending patterns, calls out unnecessary expenses, and calculates long-term saving potentials. I specifically programmed it to tell you what you *need* to hear, not what you *want* to hear.
* **Expense Tracking & Auto-Categorization:** This is where most of the work happens. You can add transactions manually or import them from Excel. The system has a built-in logic engine that automatically categorizes transactions based on keywords (e.g., if it sees "Shufersal", it knows it's groceries).
* **Strict Monthly Budgets:** The system lets you set specific financial limits for different categories. Every time you exceed a category's budget, your overall financial health score drops, helping you catch problems early.
* **Recurring Transactions:** Automates your monthly bills. Set them up once, and the engine smartly injects them into your journal on the designated day without creating duplicates.
* **Savings Goals:** Lets you set targets like a wedding, vacation, or emergency fund. The system tracks your progress visually.
* **Analysis & Forecasting Tools:** Includes monthly breakdowns with daily spending charts, category trends over time, and smart spending forecasts based on your 3-month history to help you understand patterns.

### Technical Implementation

The entire application runs as a single HTML file with embedded CSS and JavaScript. No frameworks, no build process, no server needed. Just open the file in a browser and it works.

I chose this approach deliberately. Most modern web apps have become incredibly complex with countless dependencies that break every few months. I wanted something stable, lightning-fast, and entirely private. 

The tech stack is straightforward:
* **HTML5, CSS3, and Vanilla JavaScript** handle the core functionality and dynamic UI rendering.
* **Chart.js** provides the visualizations. It's mature and does exactly what I need without being bloated.
* **SheetJS** handles the Excel file parsing for bank imports, which is critical since Israeli banks export data in various messy formats.
* **Google Generative AI API** handles the backend calls for the AI advisor module.
* **LocalStorage** keeps all your data strictly on your device. Nothing gets sent to any server (except the AI prompts you choose to send to Gemini).

### How This Project Was Built

I need to be transparent about something: I didn't write most of this code line by line. Instead, I used AI tools as my development accelerator while I focused on the architecture and business logic.

I started by mapping out exactly what features I needed based on my own pain points. Then I designed the data structures and logic flows. What should happen when someone exceeds their budget? How should the category detection algorithm work? How do we dynamically re-render the entire UI when switching between Hebrew (RTL) and English (LTR)?

Once I had clear specifications, I used AI to generate the code implementations. I tested everything thoroughly, found edge cases, and iterated. My role was essentially that of a **Product Manager and Systems Architect**. I defined requirements, validated outputs, and made decisions about tradeoffs. The AI handled the syntax. 

This approach let me build a production-ready system in a fraction of the time, demonstrating how modern software development is shifting toward human-led design paired with AI execution.

### What I Learned

This project taught me several valuable lessons:
1. **Real products require constant refinement.** Version 3.3 is dramatically better than version 1 because of dozens of small fixes discovered through daily use.
2. **Data quality is harder than it looks.** Getting bank imports to work reliably meant handling all kinds of edge cases and messy real-world data.
3. **Dynamic DOM manipulation is tricky.** Building a system that seamlessly translates text and graphs on-the-fly without refreshing the page required rethinking how the UI renders data.
4. **Privacy by design builds trust.** Keeping everything local isn't just a technical choice, it's a feature. 

### Current Limitations
* All data is stored in browser localStorage. If you clear your browser data, you lose everything. There's a JSON export/import function, but you need to remember to use it.
* You can't natively sync between devices since everything is local. 
* The AI Advisor requires the user to input their own personal Gemini API key to function.
* The interface is fully responsive, but the dense data tables are best experienced on a desktop or tablet.

### Why I'm Sharing This

I built PRO-FINANCE primarily for myself, but I'm sharing it publicly because:
* It demonstrates my ability to identify a real problem and create a working, structured solution.
* For anyone evaluating me for a role involving **Product Management, PMO, or Data Analysis**, this project provides concrete evidence of my systems-thinking and logical design skills.
* It represents a modern approach to building software: utilizing AI to maximize output while maintaining strict control over the product's vision and architecture.

### Contact

**Shoval Naor** - Industrial Engineering and Management Graduate  
*Actively seeking roles in Data Analysis or PMO* * Email: shovaln1310@gmail.com  
* LinkedIn: [linkedin.com/in/shoval-naor](https://www.linkedin.com/in/shoval-naor)

---

### ⚖️ License & Usage
© 2026 Shoval Naor. All Rights Reserved.  
This project is shared publicly for **portfolio and evaluation purposes only**. Please do not reproduce, distribute, or use this code for commercial or private projects without explicit permission.
