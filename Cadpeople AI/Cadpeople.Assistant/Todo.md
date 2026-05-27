
Pipeplines/agent
- Ensure that each step in the pipeline is stored in the database, so we can trace what happens. Internal messages between assistant should be tagged with assistant-to-assistant

Agent/Assisstants
- Make sure all user messages are stored before they are processes, so it is possible to go back and redo the task, if the LLM does not answer