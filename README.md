# PRO-FINANCE V14.0

A smart personal finance management system built to solve real-world budgeting needs.

## About This Project

I'm an Industrial Engineering and Management graduate who got tired of juggling between different banking apps and Excel sheets just to understand where my money goes each month. After trying a bunch of personal finance apps that either cost too much, had terrible UX, or didn't support Hebrew properly, I decided to build my own solution.

This project started as a simple expense tracker and evolved into a full financial management system over several months of daily use and iteration. It's designed specifically for the Israeli market with Hebrew interface, shekel currency, and direct import from local banks.

The core problem I wanted to solve was simple: I needed to know if I'm about to overspend BEFORE it happens, not after reviewing my credit card statement at the end of the month. I also wanted something that respects my privacy by keeping all data locally on my device.

---

## Main Features

The system includes several modules I built as I identified needs in my daily usage:

Dashboard gives you an immediate snapshot of your financial situation. Total income and expenses for the year, current balance, and monthly average. There's also a budget status table that shows which categories you're doing well in and which ones need attention.

Expense Tracking is where most of the work happens. You can add transactions manually or import them directly from your bank statement. The system has a built-in logic engine that automatically categorizes transactions based on keywords. For example, when it sees "Shufersal" or "Rami Levy" in the description, it knows that's groceries. This saves a lot of manual work.

Budget Alerts were probably the most important feature for me personally. The system tracks your spending in real-time and warns you when you're approaching your limits. It uses a two-tier system: weekly alerts when you hit 25% of your monthly budget for a category, and monthly alerts when you exceed 100%. This way you catch problems early.

Savings Goals lets you set financial targets like a wedding, vacation, or emergency fund. The system tracks your progress and calculates how much you need to save each month to reach your goal on time. It's motivating to see the progress bar fill up.

Analysis Tools include monthly breakdowns with daily spending charts, category trends over time, and spending forecasts based on your history. These help you understand patterns in your spending behavior.

---

## Technical Implementation

The entire application runs as a single HTML file with embedded CSS and JavaScript. No frameworks, no build process, no server needed. Just open the file in a browser and it works.

I chose this approach deliberately. Most modern web apps have become incredibly complex with countless dependencies that break every few months. I wanted something stable that would still work in five years without maintenance. Plus, it makes the code easier to understand and modify.

The tech stack is straightforward:

HTML5, CSS3, and vanilla JavaScript handle the core functionality. I use modern ES6+ features like arrow functions, destructuring, and async/await where they make the code cleaner.

Chart.js provides the visualizations. It's a mature, well-documented library that does exactly what I need without being bloated.

SheetJS handles the Excel file parsing for bank imports. This was critical because Israeli banks export data in various formats and I needed something robust enough to handle them all.

LocalStorage keeps all your data on your device. Nothing gets sent to any server, which means your financial information stays completely private.

The styling uses CSS Grid and Flexbox for layouts, with custom properties for theming. The entire interface supports right-to-left text direction properly, which is surprisingly tricky to get right.

---

## How This Project Was Built

I need to be transparent about something: I didn't write most of this code line by line. Instead, I used AI tools as my development accelerator while I focused on the architecture and business logic.

Here's how the process actually worked:

I started by mapping out exactly what features I needed based on my own pain points with existing solutions. Then I designed the data structures and logic flows on paper. What should happen when someone exceeds their budget? How should the category detection algorithm work? What's the best way to parse different bank file formats?

Once I had clear specifications, I used AI to generate the code implementations. I would describe what I needed in plain language and let the AI handle the syntax. Then I tested everything thoroughly, found edge cases, and iterated until each feature worked reliably.

My role was essentially that of a product manager and quality assurance engineer. I defined requirements, validated outputs, and made decisions about tradeoffs and priorities. The AI handled the tedious work of writing boilerplate code and wrestling with API documentation.

This approach let me build something in a few months that would have taken me a year or more to code manually, especially since I'm not a professional developer. But I understand every part of how this system works because I designed its logic and tested it extensively.

---

## What I Learned

This project taught me several valuable lessons:

Real products require constant refinement. The first version was pretty basic, but through daily use I kept finding small improvements that made a big difference. Version 14 is dramatically better than version 1, not because of big features but because of dozens of small fixes.

Data quality is harder than it looks. Getting bank imports to work reliably meant handling all kinds of edge cases. Different date formats, negative vs positive amounts, missing columns, extra header rows, transactions split across multiple rows. Real-world data is messy.

Good defaults matter more than customization. I initially planned to make everything configurable, but eventually realized that smart defaults that work for most people are better than endless settings. The category detection keywords, budget alert thresholds, and chart types are all based on what actually proved useful in practice.

User experience is about reducing friction. Every extra click or required field is a chance for users to give up. I spent a lot of time streamlining workflows so common tasks take minimal effort.

Privacy by design builds trust. Keeping everything local isn't just a technical choice, it's a feature. People are rightfully concerned about financial data security, and this architecture eliminates that worry entirely.

---

## Current Limitations

The system works well for my needs but has some obvious gaps:

All data is stored in browser localStorage, which means if you clear your browser data you lose everything. There's an export function but you need to remember to use it. A cloud backup option would be more robust.

You can't sync between devices since everything is local. If you use both a laptop and phone, you need to pick one as your primary device.

The category detection only knows keywords I've programmed in. If you shop somewhere the system hasn't seen before, it defaults to "Other" and you need to recategorize manually. It would be smarter if it could learn from your corrections.

While the interface works on mobile browsers, it's really designed for desktop use. A native mobile app would provide a better experience for on-the-go expense logging.

There's no way to split a single transaction between multiple categories, which sometimes happens in real life.

These limitations are all fixable with more development time, but the current version handles my day-to-day needs well enough that they haven't been priorities.

---

## Why I'm Sharing This

I built PRO-FINANCE primarily for myself, but I'm sharing it publicly for a few reasons:

It demonstrates my ability to identify a real problem and create a working solution. This isn't a tutorial project or a clone of something else. It's a tool that solves an actual need I had.

It shows I can work through complex challenges independently. Getting bank file imports working required figuring out parsing logic, handling edge cases, and testing against real messy data.

It proves I can manage a project from initial concept through multiple iterations to a polished product. The jump from V1 to V14 represents months of refinement based on actual usage.

For anyone evaluating me for a role that involves product thinking, systems design, or data analysis, this project gives concrete evidence of those skills. I can walk through every decision I made and explain the reasoning behind it.

Most importantly, it represents a modern approach to building software. Using AI as a coding assistant while focusing human effort on design and validation is going to become standard practice. I wanted to demonstrate that I'm already comfortable working this way.

---

## Usage Rights

This project is copyrighted and shared here for portfolio purposes only. You're welcome to look at the code for learning or evaluation, but please don't use it commercially or redistribute it without permission.

If you have a specific use case in mind, feel free to reach out and we can discuss it.

---

## Future Development Ideas

There are several features I've considered adding if I continue developing this:

Recurring transactions would save time for things like rent, subscriptions, and monthly bills. Set them up once and the system adds them automatically.

Better mobile support through a progressive web app approach or even a native mobile version would make it more convenient for logging expenses on the go.

PDF export functionality would be useful for tax purposes or sharing financial summaries with an accountant.

Multi-currency support would help people who travel frequently or deal with foreign transactions.

Shared accounts for couples or families who want to track household finances together.

Integration with open banking APIs would eliminate manual imports entirely, though this raises privacy concerns.

But honestly, the current version does what I need. These ideas are nice-to-haves rather than critical gaps.

---

## Contact

Shoval Naor
Industrial Engineering and Management Graduate

Email: shovaln1310@gmail.com
LinkedIn: https://www.linkedin.com/in/shoval-naor

If you have questions about the project, want to discuss the technical decisions I made, or are interested in my approach to building products, I'm happy to talk.


## Quick Technical Summary

Single HTML file, approximately 800 lines of code
11 expense categories with 50+ auto-detection keywords
Supports unlimited transactions with no performance issues
Full Hebrew interface with proper RTL support
Dark and light modes
Works completely offline
Zero external dependencies except Chart.js and SheetJS

Built because I needed it. Refined through months of daily use. Shared to demonstrate capabilities.

## ⚖️ License & Usage
**© 2025 Shoval Naor. All Rights Reserved.**

This project is shared publicly for **portfolio and evaluation purposes only**.
Please do not reproduce, distribute, or use this code for commercial or private projects without explicit permission.
