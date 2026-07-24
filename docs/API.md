# 📚 Laxa API Documentation

## Base URL
http://localhost:3000/api

## Authentication

All endpoints (except login/register) require JWT token in header:

## Endpoints

### Auth
- `POST /auth/register` - Create new account
- `POST /auth/login` - Login
- `POST /auth/refresh` - Refresh token
- `POST /auth/logout` - Logout

### Users
- `GET /users/profile` - Get current user
- `PUT /users/profile` - Update profile
- `GET /users/:id` - Get user by ID

### Projects
- `GET /projects` - List user projects
- `POST /projects` - Create new project
- `GET /projects/:id` - Get project details
- `PUT /projects/:id` - Update project
- `DELETE /projects/:id` - Delete project

### Files
- `GET /projects/:id/files` - List project files
- `POST /projects/:id/files` - Create file
- `GET /files/:id` - Get file content
- `PUT /files/:id` - Update file
- `DELETE /files/:id` - Delete file

### Execution
- `POST /execute` - Execute code
- `GET /executions/:id` - Get execution result
- `GET /executions` - List executions

### AI
- `POST /ai/suggest` - Get code suggestions
- `POST /ai/analyze` - Analyze code
- `POST /ai/debug` - Debug code

### Collaboration
- `GET /sessions` - List active sessions
- `POST /sessions` - Create session
- `DELETE /sessions/:id` - End session

## WebSocket Events

### Client to Server
- `code-change` - Code updated
- `cursor-move` - Cursor position changed
- `selection-change` - Selection changed
- `execute-code` - Execute code request
- `chat-message` - Send message

### Server to Client
- `code-updated` - Code changed by other user
- `cursor-updated` - Cursor position from other user
- `execution-result` - Execution result
- `chat-message` - Received message
- `error` - Error occurred

## Error Responses

```json
{
  "error": "Error message",
  "code": "ERROR_CODE",
  "status": 400
}
