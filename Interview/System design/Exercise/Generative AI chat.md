Design a system similar to ChatGPT, a chatbot platform powered a backend AI model. The AI component is out of scope and will be treated as a black box.
# Requirements
- The system must allow users to input prompts and receive AI-generated responses.
	- It may also support additional media types e.g. photos
	- It should maintain the context within the same conversation 
- The system must include a frontend component
- It should support up to 1000 concurrent users
- it should store the past conversations
- The system should incorporate content filtering capability

## Objects
- Account – user's account
- Conversation – a group of messages, both prompts and response
- Message – a single paragraph of text
## Relationships
- Account -> Conversation
	- can start a conversation
	- can list 
# Solution
## API
- `GET /conversation` – lists user's past conversations
	- takes user's ID from the auth token
	- returns a list of `{ conversation_id, title, summary }`
- `POST /conversation` – creates a new conversation
- `GET /conversation/{uuid}` – retrieves a conversation
- `POST /conversation/{uuid}/message` – adds a message to a conversation