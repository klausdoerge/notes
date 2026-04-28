
The system should support multiple roles for the users which can be used for
- Instant feedback
- Evaluation of user flow/state (?) - what is your progress and therefor next natural step?
- Scenario generation

Approach

Role based interface
We shall create a API for use within the various system. Instead of each system communicating with the LLM directly, they use the Gateway to communicate with a Role. Each role is defined by a set of system messages and instructions on how to format the messages between the user/system 

The role interface will ensure that the end prompt is optimally formatted and have all the required context for the LLM to ensure a qualified response.

LLM Manager
We will implement OpenAI for this project. However, the AI LLMs are moving fast and we must ensure that we can support multiple formats. The LLM manager will be able to format the data to a set of selected vendors and is extendible for further formats if needed.

Redis cache
All messages are vectorized and stored in a redis cache. When a user asks a common question the api will fetch the last response using similarity search from the cache instead of using the LLM for identical questions which will cut cost of the LLM. 