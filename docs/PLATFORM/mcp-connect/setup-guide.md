---
title: Setup Guide Claude
excerpt: Connect Lifesight MCP to Claude in 2 minutes.
deprecated: false
hidden: false
metadata:
  robots: index
---
## **Before You Start**

Ensure you have the following before proceeding:

- An active Lifesight workspace. If you're evaluating Lifesight, <Anchor target="_blank" href="https://lifesight.io/demo/">book a demo</Anchor>.
- Claude Desktop (latest version)
- Lifesight MCP URL: [https://mcp.lifesight.io/mcp](https://mcp.lifesight.io/mcp)

***

## Steps to Connect Claude with Lifesight MCP

1. Fire up Claude Desktop and make sure you’re on the latest version.

2. Navigate to **Customize → Connectors&#x20;**


<Image src="https://files.readme.io/9545dc35b22fb0785f1317ffc84197aec5998bea78a6c9e31150fd776b1444fa-Screenshot_2026-06-01_at_10.29.30_PM.png" align="center" width="600px" border={true} />


3. Then click on **Add Custom connectors**


<Image src="https://files.readme.io/543b5aa7da9c168ebe4a8ff5f9a467ac6d6c91c76267eb04c90f7f78cc9d8420-Screenshot_2026-06-01_at_10.30.12_PM.png" align="center" width="600px" border={true} />


<br />

3. Give the connector a name you’ll recognise, e.g. Lifesight MIA MCP.
4. Add the URL and hit Add and Connect.
   > 📌 URL -&#x20;**&#x20;**[**https://mcp.lifesight.io/mcp**](https://mcp.lifesight.io/mcp)


<Image src="https://files.readme.io/6567c09b71cf8e84217ed23a8b38d47146470daf91cafe3834a7888eb3f4e092-Screenshot_2026-06-01_at_11.06.01_PM.png" align="center" width="600px" border={true} />


5. Claude will redirect you t&#x6F;**&#x20;**[**https://console.lifesight.io/mia-connect**](https://console.lifesight.io/mia-connect)**.**
6. Existing users: Log in with your Lifesight credentials. You're all set!


<Image src="https://files.readme.io/25913f8dfc06a3bb132a3b50796797a1c3decdd0b229742d82ae50fb9fb223cc-Screenshot_2026-06-01_at_10.32.16_PM.png" align="center" width="600px" border={true} />


5. **New users: Click Request for access to be redirected to the Lifesight demo page to get started.**

That’s it! Start asking questions in your language. Not sure where to begin?

| Try any of these                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **"What’s my \[Quarter] budget allocation by channel?”<br />“Which channel drove the highest iROAS last week?”<br />“I have \[ $200K] to reallocate, where should it go to maximize revenue?”<br />“Show me how \[Ad Channel 1]  has been performing compared to  \[Ad Channel 2] over the last \[N days].** |

***

## **Verify Your Setup**

These three prompts work in both Claude Desktop and ChatGPT. If you get structured output from your account, you’re good to go.

| Prompt                                                    | Expected Outcome                                              |
| --------------------------------------------------------- | ------------------------------------------------------------- |
| _List every causal model in my workspace._                | Markdown table: model names, last-run date, confidence range. |
| _What was my best-performing channel last week by iROAS?_ | Ranked answer with methodology footnote.                      |
| _Find the methodology document for geo-lift testing._     | Doc summary with link back to Lifesight.                      |

<br />
