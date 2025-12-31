
Gameflow
4-6 users attend a session with a specific topic. For this example it could be 5 managers which must handle a 15% budget-cut. They are presented with an introduction to the game and the topic, and must then agree on how to move forward. They can choose between a few predefined actions, but can also just write their own short response on how they want to handle the issue.

As soon as a user responds, the LLM evaluates the answer based on a system prompt, and provides the user with some short pros and cons to their decision.

As soon as all users have replied, the LLM evaluates all the feedback and sums up the various responses and  the users can then discuss the topics, before deciding on a common first step to solve the issue. This can be done by selecting from the summed up proposals or the group can write a short action description they all agree on and submit it.

The LLM evaluates the response and will reply with a short list of pros and cons from the response and create a new scenario for the "company" based on the decision, and the players must now again try and handle the consequences of their previous actions.


Services
- Multiuser server with state management
- LLM
- User-store?

Problem
The LLM need to know a lot of facts about the company to help guide the conversation.
- Maybe the LLM provides a list of options with an expected saving for each, so that the players can base their decisions on these facts, without having to know where the data comes from.



