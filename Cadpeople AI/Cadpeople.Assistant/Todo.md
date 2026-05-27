
Pipeplines/agent
- Ensure that each step in the pipeline is stored in the database, so we can trace what happens. Internal messages between assistant should be tagged with assistant-to-assistant

Agent/Assistants
- Make sure all user messages are stored before they are processes, so it is possible to go back and redo the task, if the LLM does not answer

Snippets
- Add categories and sub-categories to the snippets, so they will be easier to find when there are many. Add search-functionality.
- Add tagging to snippets so they can be sorted on guardrails, info, etc.

General todo
- Allow users to upload an image which is forwarded to the LLM
- Create RAG solutions
	- Azure Foundry
	- Ollama + ?
	- Others
- Generate media assets
	- Images
	- Video
	- Text to Image
	- Image to Image
- Speech to Text
- Text to Speech
- Azure Foundry Live
- Authentication
	- Work from any website using ?
	- Azure Entra SSO
	- Microsoft Identity
- Analtyics
	- Price calculate
- Accounts
	- Limit token usage pr. installation?
- Webhooks for external system communication

Evaluate on users answers. Did the user understand a specific task sufficiently? How can we measure this?