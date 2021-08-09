# Mapping Sentiments to Emojis


Symbl's APIs empower developers to enable: 
- **Real-time** analysis of free-flowing discussions to automatically surface highly relevant summary discussion topics, contextual insights, suggestive action items, follow-ups, decisions, and questions.
- **Voice APIs** that makes it easy to add AI-powered conversation intelligence to either [telephony][telephony] or [WebSocket][websocket] interfaces.
- **Conversation APIs** that provide a REST interface for managing and processing your conversation data.
- **Summary UI** with a fully customizable and editable reference experience that indexes a searchable transcript and shows generated actionable insights, topics, timecodes, and speaker information.

<hr />

## Pre-requisites

* HTML
* JavaScript
* Python3


## Feature:
Enable a WebSocket's live streaming sentiment polarity scores to be interpreted by emojis. 

## Setup and Deploy
The first step to getting setup is to [sign up][signup]. 

Gather your Symbl credentials:
1. Your App Id that you can get from [Platform](https://platform.symbl.ai)
2. Your App Secret that you can get from [Platform](https://platform.symbl.ai)
3. After setting up your Symbl.ai account, `cURL` Symbl.ai's authentication API endpoint for an authorization token in the following way:

```bash
curl -k -X POST "https://api.symbl.ai/oauth2/token:generate" \
     -H "accept: application/json" \
     -H "Content-Type: application/json" \
     -d "{ \"type\": \"application\", \"appId\": \"<appId>\", \"appSecret\": \"<appSecret>\"}"
```

4. Assign your authorization token as the value of `accessToken`. 

5. Run `python3 -m http.server 8000` in the root directory. 

6. You app should be running at http://localhost:8000


## Conclusion
You application interprets sentiments from Symbl.ai's Conversation API Message API with the /message's API's parameter for `sentiments` set to `true`. After making calls to the Message API, your application interprets the messages with scores below -0.3 as 😞, the messages with scores above 0.3 as 😃, the messages between those scores as 😐. It demonstrates how Symbl.ai's Conversation Intelligence API platform empowers developers to connect, transform or visualize conversation data in real-time with little to no coding. 

## Community

If you have any questions, feel free to reach out to us at devrelations@symbl.ai or through our [Community Slack][slack] or our [forum][developer_community].

This guide is actively developed, and we love to hear from you! Please feel free to [create an issue][issues] or [open a pull request][pulls] with your questions, comments, suggestions and feedback.  If you liked our integration guide, please star our repo!

This library is released under the [Apache License][license]

[license]: LICENSE.txt
[telephony]: https://docs.symbl.ai/docs/telephony/overview/post-api
[websocket]: https://docs.symbl.ai/docs/streamingapi/overview/introduction
[developer_community]: https://community.symbl.ai/?_ga=2.134156042.526040298.1609788827-1505817196.1609788827
[slack]: https://join.slack.com/t/symbldotai/shared_invite/zt-4sic2s11-D3x496pll8UHSJ89cm78CA
[signup]: https://platform.symbl.ai/?_ga=2.63499307.526040298.1609788827-1505817196.1609788827
[issues]: https://github.com/symblai/symbl-for-zoom/issues
[pulls]: https://github.com/symblai/symbl-for-zoom/pulls