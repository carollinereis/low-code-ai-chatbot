# Low-Code Virtual Café Assistant with Google AI & n8n

[Leia em Português do Brasil](./README.pt-br.md)

This project demonstrates how to build a fully functional, intelligent chatbot for a café using a completely low-code approach. The assistant can answer questions about the men and provide store hours.

It leverages the power of Google's Gemini models for conversational AI and n8n for visual workflow automation, allowing you to go from idea to deployment without writing complex code.

**[View the Project Architecture Diagram](./img/architecture-diagram.png)**

## Features
- **Conversational Support:** Engage customers in natural, human-like conversation.
- **Menu & Business Knowledge:** Instantly answer questions about menu items, prices, and store hours.
- **24/7 Availability:** Serve customers online anytime.
- **Easily Extensible:** The n8n workflow can be expanded to log conversations, send notifications, and more.

## Tech Stack
- **AI Brain:** **Google AI Studio** (Gemini Pro model)
- **Automation Engine / Backend:** **n8n**

## Prerequisites
- A Google Account to access [Google AI Studio](https://aistudio.google.com/).
- An active [n8n](https://n8n.io/) instance (the free cloud plan is perfect for starting).

## Getting Started

Ready to build your own assistant? We've created a detailed, step-by-step guide to walk you through the entire process, from setting up your tools to testing your live chatbot.

#### **[Click Here for the Full Setup Guide](SETUP.md)**

### Usage Example
Once deployed, you interact with your assistant by sending a message as a query parameter in a URL.

**Your URL will look like this:**
[`https://cafeproject.app.n8n.cloud/webhook/fbf80255-9246-486c-8434-58adc96a8e42/chat`]



