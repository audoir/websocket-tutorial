# WebSocket Tutorial

A real-time chat application built with Next.js, Socket.IO, and TypeScript that demonstrates WebSocket communication and message broadcasting.

## Features

- **Real-time messaging**: Send and receive messages instantly across all connected clients
- **Connection status**: Visual indicator showing connection state
- **Message history**: Persistent chat history during the session
- **Responsive UI**: Clean, modern interface built with Tailwind CSS
- **TypeScript support**: Full type safety throughout the application
- **Auto-scroll**: Messages automatically scroll to the latest message

## Tech Stack

- **Frontend**: Next.js 16, React 19, TypeScript
- **Backend**: Node.js with Socket.IO server
- **Styling**: Tailwind CSS
- **Real-time Communication**: Socket.IO
- **Development**: tsx for TypeScript execution

## Project Structure

```
websocket-tutorial/
├── src/
│   ├── app/
│   │   ├── page.tsx          # Main chat interface
│   │   ├── layout.tsx        # App layout
│   │   └── globals.css       # Global styles
│   ├── hooks/
│   │   └── useSocket.ts      # Custom hook for Socket.IO connection
│   └── types/
│       └── message.ts        # Message type definitions
├── server.ts                 # Socket.IO server with Next.js integration
├── package.json
└── README.md
```

## Getting Started

### Prerequisites

- Node.js (version 18 or higher)
- npm or yarn

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd websocket-tutorial
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
npm run dev
```

4. Open your browser and navigate to `http://localhost:3000`

### Production Build

To build and run the application in production mode:

```bash
npm run build
npm start
```

## How It Works

### Server Side (`server.ts`)

The server integrates Socket.IO with Next.js:

- Creates an HTTP server that handles both Next.js requests and WebSocket connections
- Listens for `chat message` events from clients
- Broadcasts received messages to all connected clients
- Logs connection and disconnection events

### Client Side

#### Custom Hook (`useSocket.ts`)

The `useSocket` hook manages the WebSocket connection:

- Establishes connection to the Socket.IO server
- Tracks connection status
- Handles incoming messages
- Provides a `sendMessage` function for sending messages

#### Main Component (`page.tsx`)

The main chat interface:

- Uses the `useSocket` hook for real-time communication
- Manages local message state and input handling
- Renders messages with sent/received styling
- Auto-scrolls to new messages
- Shows connection status

#### Message Type (`message.ts`)

Defines the structure of chat messages:

```typescript
interface Message {
  id: string;
  text: string;
  timestamp: Date | string;
  isSent: boolean;
}
```

## Key Concepts Demonstrated

1. **WebSocket Connection**: Establishing and maintaining real-time connections
2. **Event-driven Communication**: Using Socket.IO events for message passing
3. **Broadcasting**: Sending messages to all connected clients
4. **State Management**: Managing connection state and message history
5. **Custom Hooks**: Creating reusable React hooks for WebSocket functionality
6. **TypeScript Integration**: Type-safe WebSocket communication

## Testing the Application

1. Open multiple browser tabs/windows to `http://localhost:3000`
2. Type a message in one tab and press Send
3. Observe the message appearing in all other tabs in real-time
4. Notice the connection status indicator
5. Try refreshing a tab to see reconnection behavior

## Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build the application for production
- `npm start` - Start the production server
- `npm run lint` - Run ESLint for code quality checks

## Learning Objectives

This tutorial demonstrates:

- Setting up a WebSocket server with Socket.IO
- Integrating WebSocket communication in a React application
- Managing real-time state updates
- Building a responsive chat interface
- Handling connection states and error scenarios
- TypeScript best practices for real-time applications
