# Card Collection API

A RESTful API for managing a card collection built with Node.js and Express.

## Overview

This is a full-stack card management application that provides a backend API for creating, reading, updating, and deleting card records. The project follows a standard MVC (Model-View-Controller) architecture with separation of concerns across controllers, services, models, and routes.

## Project Structure

```
.
├── index.js                    # Main application entry point
├── package.json               # Project dependencies and scripts
├── pnpm-lock.yaml            # Dependency lock file
├── controllers/
│   └── card.controller.js     # Request handlers for card operations
├── models/
│   └── card.model.js          # Data model schema/structure
├── routes/
│   └── card.routes.js         # API route definitions
└── services/
    └── card.service.js        # Business logic layer
```

## Dependencies

- **Express.js** - Web framework for building the REST API
- **CORS** - Middleware for handling Cross-Origin Resource Sharing
- **Nodemon** (dev) - Auto-restart server during development

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- pnpm or npm

### Installation

1. Install dependencies:
```bash
pnpm install
```

### Running the Application

**Development mode** (with auto-reload):
```bash
pnpm dev
```

**Production mode**:
```bash
pnpm start
```

The server will start on `http://localhost:3000` by default.

## API Endpoints

### Base URL
```
http://localhost:3000
```

### Routes

All card operations are prefixed with `/cards`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/cards` | Get all cards |
| GET | `/cards/:id` | Get a specific card by ID |
| POST | `/cards` | Create a new card |
| PUT | `/cards/:id` | Update a card by ID |
| DELETE | `/cards/:id` | Delete a card by ID |

### Welcome Endpoint
- **GET** `/` - Returns a welcome message

## Architecture

### Controllers (`controllers/card.controller.js`)
Handles HTTP requests and responses for card operations:
- `getAllCards()` - Fetch all cards
- `getCardById()` - Fetch a single card
- `createCard()` - Create a new card
- `updateCard()` - Update an existing card
- `deleteCard()` - Delete a card

### Services (`services/card.service.js`)
Implements business logic for card operations:
- Validates data
- Handles card-related operations
- Interacts with the data model

### Models (`models/card.model.js`)
Defines the card data structure and schema.

### Routes (`routes/card.routes.js`)
Configures URL routing and maps endpoints to controller methods.

## Environment Variables

- `PORT` - Server port (default: 3000)

Set environment variables in a `.env` file or via system environment:
```bash
PORT=3001 pnpm dev
```

## Development

To ensure code quality during development:
- Use `pnpm dev` to run the server with auto-reload
- Follow the established MVC pattern
- Keep logic separated between controllers, services, and models

## Scripts

- `pnpm start` - Start the production server
- `pnpm dev` - Start the development server with nodemon

## License

This project is part of the Full Stack Development coursework.
