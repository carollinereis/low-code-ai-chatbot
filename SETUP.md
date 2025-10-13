## Full Setup Guide: Building Your AI Café Assistant

This guide provides a detailed, step-by-step walkthrough for creating your low-code virtual café assistant using n8n and Google AI Studio.

---

### **Part 1: Set Up Your n8n Backend**

Our n8n workflow will act as the central "backend" for our chatbot.

1.  **Create a Free n8n Account:** Navigate to the [n8n website](https://n8n.io/) and sign up for a free cloud starter plan. This is the fastest way to get started without managing servers.
2.  **Start a New Workflow:** Once logged in, you'll be in your n8n dashboard. Create a new, blank workflow.

---

### **Part 2: Configure the AI Brain in Google AI Studio**

We need an API Key from Google, which acts like a secure password that allows n8n to communicate with the Gemini AI model.

1.  **Navigate to Google AI Studio:** Go to [aistudio.google.com](https://aistudio.google.com/).
2.  **Get API Key:** Look for the **`< > Get API key`** button on the top left and click it.
3.  **Create API Key:** Click **Create API key in new project**.
4.  **Copy Your Key:** Your new API key will be generated. **Copy this key immediately** and save it somewhere safe for the next step.

---

### **Part 3: Build the n8n Workflow**

Now we'll return to n8n to build the core logic.

1.  **Add the AI Agent Node:** In your n8n workflow, click the **`+`** button and add the **AI Agent** node.
2.  **Connect to Google Gemini:**
    - Click on the AI Agent node. Under 'Chat Model', click **`+`** and choose **Google Gemini**.
    - In the 'Credential' dropdown, select **Create New**.
    - Give your credential a name (e.g., `My Gemini Cafe Key`) and paste the **API Key** you copied from Google AI Studio.
    - Click **Save**.
3.  **Give Your Agent Instructions:**
    - In the AI Agent node settings, click **Add Option** -> **System Message**.
    - In the text box, define your assistant's personality and knowledge. Example:
      > You are BrewBot, the friendly virtual assistant for "The Daily Grind Café."
      > **Menu:** Latte: $4.50, Espresso: $3.00.
      > **Hours:** Weekdays 7 AM - 6 PM, Weekends 8 AM - 4 PM.
      > If you don't know the answer, say "Let me check with our human team!"
4.  **Give Your Agent Memory:**
    - Click the **Memory** dropdown and select **Simple Memory**.
    - Set the **Context Window Length** to `15` to remember the last 15 messages.

---

### **Part 4: Make Your Assistant Public and Test**

Finally, let's create a public URL (a Webhook) to receive user messages.

**Activate and Go Live**:

    - At the top right, toggle the workflow from "Inactive" to "Active".
    - Click the node and copy the Production URL. It should look like this: https://cafeproject.app.n8n.cloud/webhook/fbf80255-9246-486c-8434-58adc96a8e42/chat
    - To test, paste this URL into your browser.

### SUCCESS
You have successfully built and deployed a low-code AI assistant. You can now use this webhook URL to power a chatbot on any website or application.