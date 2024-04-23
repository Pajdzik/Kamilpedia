Design a system similar to ChatGPT, a chatbot platform powered a backend AI model. The AI component is out of scope and will be treated as a black box.
# Requirements
- The system must allow users to input prompts and receive AI-generated responses.
	- It may also support additional media types e.g. photos
	- It should maintain the context within the same conversation 
- The system must include a frontend component
- It should support up to 1000 concurrent users
- it should store the past conversations
- The system should incorporate content filtering capability
# Solution
## API
- `GET /user/:user-id/conversation` – Lists user's past conversations
	- takes user's ID as an URL parameter
- 