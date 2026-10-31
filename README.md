# n8n Automation Workflows

Ready-to-import n8n workflows for lead capture, AI lead scoring, document chat, customer support, and social media auto-posting. Each workflow is a single JSON file you can import straight into your own n8n instance.

## Workflows

| File | What it does |
| --- | --- |
| agency-leads-intake.json | A hosted form collects new leads, appends each one to a Google Sheet, and emails you a notification. |
| ai-lead-scoring-api.json | A webhook API that takes a lead (email and message), scores it with an OpenAI model, logs the result to Google Sheets, and returns structured JSON. Invalid requests are logged and get a 400 response. |
| rag-chat-with-your-documents.json | Upload a PDF, split it into chunks, embed it into a vector store, then chat with an AI agent that searches your documents and remembers the conversation. |
| telegram-ai-customer-support-bot.json | A Telegram bot powered by an OpenAI agent with per-chat memory. It replies to customers and can alert the owner when a human is needed. |
| instagram-daily-content-poster.json | Runs daily, picks the next unused topic from a Google Sheet, writes a caption with AI, publishes to Instagram, and marks the row as posted. |
| pinterest-auto-poster.json | Runs 3 times a day, takes the next unposted row from a Google Sheet queue, creates a Pinterest pin, and marks the row as posted. |

## Getting started

1. Open your n8n instance and create a new workflow.
2. Use the menu (top right) and choose Import from File, then pick one of the JSON files from this repo.
3. Open each node that needs credentials and connect your own accounts.
4. Point the Google Sheets nodes at your own spreadsheet.
5. Test the workflow manually, then activate it.

## Credentials you will need

Depending on the workflow, you will need some of the following:

- OpenAI API key (lead scoring, RAG chat, Telegram bot, caption writing)
- Google account for Google Sheets and Gmail
- Telegram bot token from BotFather
- Instagram Graph API access (Instagram business account)
- Pinterest API access

No credentials are included in these files. You must add your own.

## Requirements

- n8n (self-hosted or cloud) with the AI / LangChain nodes available
- Accounts for the services listed above

## Notes

- Sheet-driven posters expect a sheet with a column marking whether a row has been posted. Adjust the column names in the Google Sheets nodes to match your sheet.
- Review the Config and schedule nodes before activating so posting times and settings suit you.

## Contributing

Issues and pull requests are welcome.

## Author

Samruddh Borker - https://www.linkedin.com/in/samruddh-borker-8602293aa
