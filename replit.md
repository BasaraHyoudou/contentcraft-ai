# Replit.md - ContentCraft AI

## Overview

ContentCraft AI is a full-stack web application that provides AI-powered content generation services. It allows users to generate text content, images, or both using OpenAI's API. The application features a modern React frontend built with shadcn/ui components and a Node.js/Express backend with PostgreSQL database integration through Drizzle ORM.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight client-side routing)
- **State Management**: TanStack Query (React Query) for server state management
- **UI Framework**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **Build Tool**: Vite with hot module replacement

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js with middleware for JSON parsing and logging
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Database Provider**: Neon Database (@neondatabase/serverless)
- **API**: RESTful endpoints for content generation and management

### Key Components

#### Database Schema (shared/schema.ts)
- **Users Table**: Basic user authentication (id, username, password)
- **Contents Table**: Stores generated content (text, images, or both) with edit history
- **Templates Table**: Predefined content generation templates
- **Validation**: Zod schemas for type safety and validation

#### Content Generation System
- **Text Generation**: Uses OpenAI GPT-4o model for text content
- **Image Generation**: Uses OpenAI DALL-E for image generation
- **Content Types**: Supports text-only, image-only, or combined generation
- **Template System**: Pre-built templates for common content types (blog posts, emails, etc.)

#### Storage Layer
- **Interface**: IStorage interface defining data operations
- **Implementation**: MemStorage for in-memory development storage
- **Database**: Production-ready with Drizzle ORM and PostgreSQL

## Data Flow

1. **User Input**: User enters prompts through the input panel component
2. **Content Generation**: Request sent to `/api/generate` endpoint
3. **AI Processing**: OpenAI API calls for text and/or image generation
4. **Storage**: Generated content saved to database with metadata
5. **Response**: Content returned to frontend and displayed
6. **Edit Workflow**: Users can edit content through `/api/edit` endpoint

## External Dependencies

### Core Dependencies
- **OpenAI API**: Content and image generation
- **Neon Database**: PostgreSQL hosting and connection
- **Drizzle ORM**: Database operations and migrations
- **TanStack Query**: Data fetching and caching
- **Radix UI**: Accessible component primitives

### Development Tools
- **Vite**: Development server and build tool
- **TypeScript**: Type safety across the stack
- **Tailwind CSS**: Utility-first styling
- **ESBuild**: Fast bundling for production

## Deployment Strategy

### Development Environment
- **Server**: Express server with Vite middleware for HMR
- **Database**: PostgreSQL connection via DATABASE_URL environment variable
- **API Keys**: OpenAI API key required for content generation
- **Scripts**: `npm run dev` for development, `npm run build` for production

### Production Build
- **Frontend**: Vite builds static assets to `dist/public`
- **Backend**: ESBuild bundles server code to `dist/index.js`
- **Database**: Drizzle migrations handle schema changes
- **Environment**: Production mode serves static files and API routes

### Configuration Files
- **Drizzle Config**: Database connection and migration settings
- **Vite Config**: Frontend build configuration with path aliases
- **Tailwind Config**: Theming and component styling
- **TypeScript**: Shared configuration for client, server, and shared code

The application follows a monorepo structure with clear separation between client, server, and shared code, enabling efficient development and deployment workflows.