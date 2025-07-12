# Gurukul Points Management System (GSTATUS)

## Overview

GSTATUS is a comprehensive web application for managing student points in a gurukul (educational institution) environment. The system allows administrators to track student performance, assign positive/negative points based on various activities, and generate rankings. It's built as a full-stack application with a React frontend and Express backend, utilizing PostgreSQL for data persistence.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: Radix UI primitives with shadcn/ui components
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: TanStack Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ESM modules
- **Database**: PostgreSQL via Neon serverless
- **ORM**: Drizzle ORM for type-safe database operations
- **Session Management**: Express sessions with PostgreSQL store
- **API Design**: RESTful API with JSON responses

## Key Components

### Database Schema
The system uses two main tables:
- **Students**: Stores student information including ID, name, room, floor, points, grade, and activity status
- **Actions**: Tracks all point changes with timestamps, admin names, and action descriptions

### Frontend Components
- **Dashboard**: Main interface with tabbed navigation (Home, Administration, Rankings, Responses)
- **Student Search**: Real-time search functionality with autocomplete
- **Point Management**: Forms for assigning positive/negative points with predefined actions
- **Rankings Display**: Sortable and filterable student rankings
- **Response History**: Audit trail of all point changes

### Backend Services
- **Student Management**: CRUD operations for student records
- **Point System**: Handles point calculations and action logging
- **Search Service**: Fuzzy search across student names, IDs, and rooms
- **Rankings Service**: Generates sorted student rankings with filters

## Data Flow

1. **User Interaction**: Admin interacts with React components
2. **API Calls**: Frontend makes REST API calls using TanStack Query
3. **Request Processing**: Express server validates and processes requests
4. **Database Operations**: Drizzle ORM executes type-safe database queries
5. **Response**: Server returns JSON responses with updated data
6. **UI Updates**: Frontend updates automatically via query invalidation

## External Dependencies

### Production Dependencies
- **Database**: Neon PostgreSQL serverless database
- **UI Components**: Radix UI primitives for accessible components
- **Validation**: Zod for runtime type checking and validation
- **Date Handling**: date-fns for date manipulation
- **Icons**: Lucide React icons

### Development Dependencies
- **Development Server**: Vite dev server with HMR
- **Database Tools**: Drizzle Kit for migrations and schema management
- **Type Checking**: TypeScript compiler with strict mode
- **Build Tools**: ESBuild for server bundling

## Deployment Strategy

### Development
- **Frontend**: Vite dev server with proxy to backend
- **Backend**: tsx for TypeScript execution with hot reload
- **Database**: Drizzle push for schema synchronization

### Production
- **Frontend**: Static build served by Express server
- **Backend**: Compiled to ESM bundle with external dependencies
- **Database**: Managed migrations through Drizzle Kit
- **Hosting**: Designed for Node.js hosting platforms (Replit, Railway, etc.)

The application follows a monorepo structure with shared TypeScript types and utilities, enabling type safety across the entire stack. The architecture prioritizes developer experience with hot reload, type safety, and modern tooling while maintaining simplicity and performance.