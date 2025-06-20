# Chat Grid

A full-stack, multi-model AI chat application that allows users to interact with multiple AI models (e.g., GPT-4, Claude, Gemini, Llama, DeepSeek) simultaneously. The project features a modern, responsive frontend and a robust Java Spring Boot backend.

---

## Features
- Send prompts to one or more AI models and view responses side by side
- Model selection dropdown (single or all models)
- Chat history with timestamps and avatars
- Copy-to-clipboard for AI responses
- Clear chat functionality
- Responsive design (desktop & mobile)
- Light/dark mode toggle
- Error handling and loading indicators

---

## Tech Stack

### Frontend
- React (TypeScript)
- Tailwind CSS
- Vite

### Backend
- Java Spring Boot
- REST API

---

## Getting Started

### Prerequisites
- Node.js (v18+ recommended)
- Java 17+

### application.properties



### Backend Setup
1. `cd backend`
2. Build and run the Spring Boot application:
   - With Maven: `./mvnw spring-boot:run`
   - Or import into your favorite Java IDE and run `BackendApplication.java`
3. The backend will start on [http://localhost:8081](http://localhost:8081)

### Frontend Setup
1. `cd` to the project root
2. Install dependencies:
   - With npm: `npm install`
   - Or with bun: `bun install`
3. Start the frontend:
   - With npm: `npm run dev`
   - Or with bun: `bun run dev`
4. The frontend will start on [http://localhost:5173/](http://localhost:5173/)

---

## Usage
- Open [http://localhost:5173/](http://localhost:5173/) in your browser.
- Enter your prompt in the text box.
- Select one or more AI models from the dropdown.
- Click "Send" to get responses from the selected models.
- View responses side by side, copy responses, or clear the chat.

---

## API Endpoints

### Send a Message
`POST /api/chat/send`
```json
{
  "conversationId": "string",
  "aiModel": "string",
  "message": "string"
}
```
Response:
```json
{
  "id": "string",
  "content": "string",
  "aiModel": "string",
  "conversationId": "string",
  "timestamp": "string"
}
```

### Create a Conversation
`POST /api/conversations`
```json
{
  "aiModel": "string"
}
```

### Get a Conversation
`GET /api/conversations/{conversationId}`

### Clear a Conversation
`DELETE /api/conversations/{conversationId}`

---

## Customization
- To add or remove AI models, update the model list in the frontend and backend configuration.
- For production, configure CORS and environment variables as needed.

---

## License
MIT 