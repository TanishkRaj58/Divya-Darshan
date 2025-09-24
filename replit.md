# Overview

TirthaYatra Sugam is a comprehensive pilgrimage management platform that combines traditional spiritual journeys with modern technology. The application serves as a one-stop solution for temple visitors, offering features like darshan booking, real-time temple information, parking management, accessibility services, and contact support. Built as a full-stack web application, it aims to make pilgrimage experiences seamless and spiritually fulfilling by eliminating common pain points like long queues, parking hassles, and accessibility barriers.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The client-side is built using **React 18** with **TypeScript**, utilizing a component-based architecture with the following key decisions:

- **Routing**: Uses Wouter for lightweight client-side routing instead of React Router, providing better performance for this application's needs
- **UI Framework**: Implements Radix UI primitives with shadcn/ui components for accessibility-first, customizable UI components
- **Styling**: Tailwind CSS with custom CSS variables for theming, supporting both light and dark modes with temple-inspired color schemes
- **State Management**: TanStack Query (React Query) for server state management, eliminating the need for complex state management libraries
- **Internationalization**: react-i18next for multi-language support (English, Hindi, Gujarati) to serve diverse pilgrims
- **Form Handling**: React Hook Form with Zod validation for type-safe form management

## Backend Architecture
The server-side follows a **Node.js/Express** architecture with the following design choices:

- **Runtime**: Uses tsx for TypeScript execution in development and esbuild for production builds
- **API Design**: RESTful API structure with dedicated routes for temples, bookings, parking, accessibility requests, and contact messages
- **Storage Layer**: Implements an abstraction pattern with IStorage interface, currently using in-memory storage (MemStorage) but designed for easy database integration
- **Validation**: Zod schemas shared between client and server for consistent data validation
- **Error Handling**: Centralized error handling middleware with proper HTTP status codes and JSON error responses

## Data Storage Solutions
The application uses a flexible storage architecture:

- **Current Implementation**: In-memory storage with predefined temple data and real-time simulation
- **Schema Design**: Drizzle ORM with PostgreSQL schema definitions, ready for production database integration
- **Migration Strategy**: Drizzle migrations configured for easy deployment to PostgreSQL databases
- **Data Models**: Well-defined entities for temples, bookings, parking lots, accessibility requests, and contact messages

## Authentication and Authorization
Currently implements a simplified approach suitable for the MVP stage:

- **Session Management**: Basic session handling without complex authentication flows
- **Security**: Input validation and sanitization through Zod schemas
- **Future-Ready**: Architecture supports easy integration of authentication providers

## External Dependencies

### Database Integration
- **Neon Database**: Serverless PostgreSQL solution configured for production deployment
- **Drizzle ORM**: Type-safe database operations with automatic migration support
- **Connection**: @neondatabase/serverless for serverless database connections

### UI and Styling
- **Radix UI**: Comprehensive primitive components for accessibility and customization
- **Tailwind CSS**: Utility-first CSS framework with custom design system
- **Lucide React**: Modern icon library for consistent iconography

### Development and Build Tools
- **Vite**: Fast build tool with HMR for development
- **TypeScript**: Full type safety across the entire application
- **ESBuild**: Fast bundling for production builds

### Third-Party Services
- **React Query**: Server state management and caching
- **React Hook Form**: Performant form handling with minimal re-renders
- **Date-fns**: Date manipulation and formatting utilities

The architecture prioritizes scalability, maintainability, and user experience while being prepared for easy integration of additional services like payment gateways, SMS notifications, and advanced authentication systems.