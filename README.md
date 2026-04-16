# Borscht

![License](https://img.shields.io/badge/license-GPLv3-blue.svg)
![Go](https://img.shields.io/badge/go-1.26+-00ADD8.svg)
![Flutter](https://img.shields.io/badge/flutter-frontend-02569B.svg)

Welcome to the Borscht project! 

## What is Borscht?

Borscht is a complete, self-hosted recipe manager, universal scraper, and meal planner. Its ecosystem revolves around saving recipes from across the web, parsing ingredients automatically, and managing them seamlessly via a cross-platform client app.

You can think of Borscht like an **RSS feed for recipes**, where your feed is automatically populated with fresh, seasonal recipes (or whatever you prefer) every couple of days. 

Beyond scraping, it includes core functionalities similar to other recipe apps:
- **Collections:** Store and organize recipes into cookbooks.
- **Meal Planning:** Create meal plans effortlessly.
- **Shopping Lists:** Generate shopping lists automatically based on what you want to cook.
- **Cooking Mode:** Follow step-by-step guides with an always-on screen.
- **Household Sharing:** Share your loved recipes, meal plans, and shopping lists with household members.
- *...and more features will come over time.*

**Why use it?**
- **Universal Scraping:** Unlike popular recipe scrapers that require manual, hardcoded configurations for each website, Borscht inherently understands `schema.org` and Open Graph markup. This allows it to reliably extract complete recipe structures from nearly any modern recipe blog out-of-the-box.
- **Flexible Storage:** Out-of-the-box support for SQLite, PostgreSQL, MySQL for the database, and local or S3-compatible self-hosted image storage for attachments.
- **Fast & Efficient:** The scraping and backend infrastructure is built in Go, resulting in lightning-fast response times and extremely low resource footprints.
- **Your Data:** It's self-hosted, removing any reliance on proprietary platforms. No logs, no traces, just your recipes.

## History

- **2022:** I was annoyed that the popular Python package everyone uses for scraping couldn't handle all the websites I needed. It required manual addition of each website, even when those sites had standard `schema.org` markup for the recipe. It was also super slow and didn't return half of the fields (and still doesn't!). At the same time, I wanted to play around with a new language and try something new. I tried Rust and Go, found Go easier and faster to adopt, and enjoyed looking for workarounds that broke my OOP mindset.
- **2023:** I considered React Native and Flutter for the client app. I tried both, hated both, and abandoned the project for a year.
- **2024:** Returned, tried both again, still hated both.
- **2025:** I decided to finally finish the app. Thanks to Claude, it became way easier to push through the Flutter part. I can genuinely thank AI for this release; without it, the client would have never been finished. I acknowledge the use of Claude and other models for the client code generation, but I take responsibility for reviewing and maintaining the code (doing the boring part). The other parts of the project consist mostly of my own shitcode, so you can blame me for that.

## Disclaimer & Ethical Note

Publishing this project poses some questions, as the app processes other people's work and requires copying them to function.
**However, as long as you use it on your own hardware for private use, it is fine.** This is why you can't find it on the Play Store or App Store, and why the code is open-source. It is not meant for commercial use or distribution.

If you end up using Borscht regularly to fetch recipes from your favorite providers, I highly advise you to return to their websites and support them (through donations, buying their books, or subscribing). If you enjoy their recipes, they did a great job and deserve the credit for it.

**If you are a recipe website owner and want to prevent your website from being scraped, please raise an issue in this repository.**

---

## Modules

1. **[Smetana (Backend)](./backend/):** The core API services.
2. **[Buryak (Frontend)](./frontend/):** The main client application.
3. **[Krip (Scraper)](./scraper/):** Responsible for web scraping recipe data.
4. **[Kapusta (Parser)](./parser/):** Parses ingredient and recipe data structures.

> **Note:** **Krip** and **Kapusta** are built as fully-fledged Go libraries and have their own CLI tools! You can import them into any Go project, or use them directly via CLI, if you just need a fast parser or scraper without the rest of the Borscht ecosystem.


## Getting Started

### 1. Deploying the Backend (Smetana)

To run the project, you first need to deploy the backend services. The easiest and recommended way to do this is via Docker.
You will find [`compose.yaml`](./backend/compose.yaml) and also more detailed instructions in the [`backend/README.md`](./backend/README.md) file.

### 2. Getting the Client App (Buryak)

You don't need to build the frontend application from source to start using it (if you want, read the README.md in the module).
The simplest way to get the Android or Web app is to download the latest available release. 

**Download the latest releases here:** [https://github.com/borschtapp/buryak/releases](https://github.com/borschtapp/buryak/releases)

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page if you want to contribute, or start a discussion.

## License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](./LICENSE) file for details.
