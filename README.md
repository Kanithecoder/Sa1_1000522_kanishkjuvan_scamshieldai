<div align="center">

# 🛡️ ScamShield AI
### Fraud & Scam Awareness Assistant

An IBCP project exploring conversational AI for online safety education.

**[🌐 Launch the Live Chatbot](https://kanishk-juvan-1000522-sa2-sub-scams.vercel.app/)**

Google Dialogflow ES · Dialogflow Messenger · Vercel · GitHub

</div>

---

## Project overview

ScamShield AI is an educational chatbot project designed to help users explore common scam warning signs and safer online practices. It applies conversational AI to a practical problem: making scam-awareness information easier to access through questions and answers.

The chatbot is built in Google Dialogflow ES and connected to a website through Dialogflow Messenger. The website is deployed on Vercel. Dialogflow handles the conversation, while the website provides a public entry point.

This README documents the project purpose, integration, deployment, and evaluation approach. The live link was supplied by the project author; this document does not certify its availability or the accuracy of every chatbot response.

## Student and assessment

| Detail | Information |
| --- | --- |
| Student | Kanishk Juvan V.A |
| Registration number | 1000522 |
| School | Viraj International School |
| Programme | International Baccalaureate Career-related Programme (IBCP) |
| Course | Artificial Intelligence: Real-World Applications and Implications |
| Assessment | Creating Intelligent Chatbots for Practical Applications |
| Project | ScamShield AI — Fraud & Scam Detection Assistant |

## Problem and purpose

Suspicious messages can use urgency, impersonation, and requests for sensitive information to influence users. People who are unfamiliar with these tactics may need clear explanations before deciding what to do.

ScamShield AI aims to provide an accessible conversational starting point for learning about these warning signs. Its intended audience includes students and other internet users seeking introductory scam-awareness guidance.

The project objectives are to:

- Organise scam-related enquiries into understandable conversation topics.
- Use Dialogflow to recognise user intent from different phrasings.
- Develop relevant responses and appropriate conversation recovery.
- Make the chatbot accessible through a shareable website.
- Evaluate usefulness, limitations, and responsible use through testing.

## Try the chatbot

1. Open **[ScamShield AI](https://kanishk-juvan-1000522-sa2-sub-scams.vercel.app/)**.
2. Click the chat button, normally in the bottom-right corner.
3. Send a greeting or ask a scam-related question.
4. Respond to any follow-up prompts.
5. Use fictional examples rather than private information.

Suggested evaluation prompts:

- “Hello.”
- “What is phishing?”
- “How can I recognise a suspicious email?”
- “Someone is asking for my OTP.”
- “Can you explain that another way?”

These are prompts to evaluate, rather than a guarantee that every topic is supported by the final agent.

## Technology and architecture

| Component | Role |
| --- | --- |
| Google Dialogflow ES | Stores the agent configuration and handles intent-based conversations. |
| Dialogflow Messenger | Embeds the chat interface in the webpage. |
| HTML and CSS | Provide the website structure and visual presentation. |
| Vercel | Hosts the website and provides the live URL. |
| GitHub | Stores website source, documentation, and any submitted agent export. |

A visitor opens the Vercel webpage and sends a message through Dialogflow Messenger. Messenger communicates with the Dialogflow agent and displays its response. The agent remains hosted by Google; deploying the webpage does not transfer the agent to Vercel.

## Dialogflow integration

The supplied integration uses this embed code inside the webpage's `<body>`:

```html
<script src="https://www.gstatic.com/dialogflow-console/fast/messenger/bootstrap.js?v=1"></script>
<df-messenger
  intent="WELCOME"
  chat-title="ScamShield-AI"
  agent-id="30bab607-dfa1-4a45-bf64-29d9fc558f45"
  language-code="en"
></df-messenger>
```

The embed identifies the agent, sets the chat title and language, and specifies the welcome event. The agent must have Dialogflow Messenger enabled for the integration to work.

The agent ID in the embed is a public integration identifier. No service-account private key is needed in this HTML integration. Never commit credentials, passwords, or private keys to the repository.

## Conversation design and assessment evidence

The assessment requires at least 15 intents and 10 custom entities, alongside conversation features and testing. These are requirements, not verified counts for the deployed agent.

The final submission should document:

- **Intents:** Actual intent names, purposes, and representative training phrases.
- **Entities:** Actual custom entity names, reference values, and synonyms.
- **Contexts:** How information or conversation state supports follow-up exchanges.
- **Slot filling:** Required parameters, prompts, and an example completed exchange.
- **Fallback:** How the chatbot responds when it cannot understand a message.
- **Suggestions:** Any implemented prompts or selectable suggestions.

The final Dialogflow agent export is the source for verifying implemented configuration. No intent inventory, entity inventory, or training-phrase total has been inferred from screenshots that were unavailable during README preparation.

## Setup and deployment

### Run the website

1. Download or clone the repository containing the website source.
2. Locate the main HTML file, normally `index.html`.
3. Confirm that the Dialogflow Messenger embed is inside `<body>`.
4. Open the page through a local web server or deploy it to a web host.
5. Check that the chat widget loads and responds.

### Deploy through Vercel

1. Sign in to Vercel and choose **Add New → Project**.
2. Import the GitHub repository containing the website.
3. For a plain HTML website, choose **Other** as the framework preset.
4. Use the directory containing `index.html` as the project root. No build command is needed for a plain static page.
5. Deploy and open the production URL.
6. Test access in an incognito window.

If the repository uses a framework rather than plain HTML, use that framework's deployment settings instead.

### Reuse the agent in a separate project

If a final Dialogflow agent export ZIP is included in the repository:

1. Create a separate Dialogflow ES agent.
2. Open its settings and use **Export and Import** to import the ZIP.
3. Review the imported configuration and any external dependencies.
4. Enable Dialogflow Messenger for the new agent.
5. Copy its generated embed code into your own webpage.
6. Deploy and test the new integration.

The existing embed continues to connect to the original agent. Importing an export into another agent does not update the webpage's agent ID automatically.

## Testing and evaluation

Testing should cover recognition, conversation continuity, and failure handling. Record actual chatbot replies and intent matches where available. Do not mark a test as passed solely because a reply appeared.

| Scenario | Example input or action | What to check | Recorded result |
| --- | --- | --- | --- |
| Welcome | Open the widget and send “Hi” | Appropriate introduction and purpose | Not recorded here |
| Relevant enquiry | “What is phishing?” | Relevant, understandable explanation | Not recorded here |
| Alternative phrasing | Rephrase a supported training example | Intended topic still recognised | Not recorded here |
| Follow-up exchange | Complete a configured multi-turn conversation | Context and parameters handled correctly | Not recorded here |
| Unsupported input | Ask an unrelated question | Suitable fallback without invented certainty | Not recorded here |
| Public access | Open the live URL in incognito mode | Website and widget accessible to a visitor | Not recorded here |

Attach actual outcomes, screenshots, corrections, and retest results as assessment evidence. No live interaction tests were performed as part of preparing this README.

## Limitations, privacy, and responsible use

- Responses depend on the topics, training phrases, and configuration implemented in the agent.
- Similar or ambiguous questions may be misunderstood.
- The chatbot cannot guarantee that a message, person, website, or transaction is safe.
- The supplied embed does not establish an independent URL scanner, fraud database, or real-time verification service.
- Users should not enter passwords, OTPs, bank information, or identifying details.
- Do not assume conversations are private or unlogged; review the agent's Google Cloud logging and data settings.
- The chatbot provides educational guidance and should communicate uncertainty clearly.

## Submission evidence

Alongside this README and the website source, include the following where available:

- The final Dialogflow agent export ZIP.
- An inventory of the implemented intents and custom entities.
- At least five completed test scenarios with actual results.
- Screenshots of the live interface and representative conversations.
- The project report, research sources, and personal reflection.

Screenshots were supplied during documentation preparation but could not be opened. They are not embedded or described here, avoiding broken image links and unsupported claims.

## Reflection and future improvements

Future development could focus on wider phrasing coverage, clearer fallback guidance, improved accessibility, and more systematic testing with unfamiliar users.

The student's final reflection should explain specific design decisions, difficulties encountered, feedback received, and changes made. Personal experiences and evaluation results should be written from the student's own evidence.

## References and acknowledgements

Technical documentation:

- [Dialogflow ES documentation](https://docs.cloud.google.com/dialogflow/es/docs)
- [Dialogflow Messenger integration](https://docs.cloud.google.com/dialogflow/es/docs/integrations/dialogflow-messenger)
- [Vercel documentation](https://vercel.com/docs)
- [GitHub documentation](https://docs.github.com/)

Add the actual sources used to develop scam-awareness responses and research. The technical references above do not establish the accuracy of the chatbot's safety content.

This README was drafted with assistance from OpenAI ChatGPT using project details provided by the student. The student should review it for accuracy and follow the school's academic integrity requirements when acknowledging assistance with the wider project.

---

**Created for Kanishk Juvan V.A's IBCP AI assessment.**
