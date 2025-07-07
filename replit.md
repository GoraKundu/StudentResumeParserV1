# Resume Parser Application

## Overview

This is a full-stack web application that allows users to upload resumes in various formats (PDF, DOC, DOCX) and automatically extracts structured data using AI. The application features a clean, modern interface built with React and shadcn/ui components, with a robust backend powered by Express.js and PostgreSQL.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: TanStack Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon serverless PostgreSQL
- **File Processing**: Custom parsers for PDF and Word documents
- **AI Integration**: OpenAI API for intelligent resume data extraction
- **File Upload**: Multer for handling multipart/form-data

### Database Schema
The application uses a simple but effective schema:
- `users` table: Basic user information (id, username, password)
- `resumes` table: Stores uploaded resume metadata and parsed data
  - File information (name, type, size)
  - Original text content
  - Structured parsed data (JSON format)
  - Timestamps for tracking

## Key Components

### File Processing Pipeline
1. **File Upload**: Accepts PDF, DOC, and DOCX files up to 10MB
2. **Text Extraction**: Custom parsers extract raw text from various formats
3. **AI Processing**: OpenAI API structures the raw text into standardized resume data
4. **Database Storage**: Saves both original content and structured data

### Resume Data Structure
The application extracts and structures:
- Personal information (name, email, phone, location, LinkedIn)
- Professional summary
- Work experience with detailed job descriptions
- Educational background
- Technical and soft skills
- Certifications with validity periods

### User Interface Components
- **File Upload**: Drag-and-drop interface with progress indicators
- **Processing State**: Real-time feedback during AI processing
- **Resume Form**: Comprehensive editing interface for all resume sections
- **Responsive Design**: Mobile-first approach with adaptive layouts

## Data Flow

1. User uploads resume file through the web interface
2. Frontend validates file type and size before sending to backend
3. Backend processes file, extracts text, and calls OpenAI API
4. Structured data is saved to PostgreSQL database
5. Frontend receives parsed data and displays it in an editable form
6. User can review and modify the extracted information
7. Final data is saved back to the database

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL driver
- **drizzle-orm**: Type-safe database ORM
- **@tanstack/react-query**: Server state management
- **@radix-ui**: Accessible UI primitives
- **openai**: Official OpenAI API client
- **pdf-parse**: PDF text extraction
- **multer**: File upload handling
- **zod**: Runtime type validation

### Development Tools
- **Vite**: Fast build tool and dev server
- **TypeScript**: Static type checking
- **Tailwind CSS**: Utility-first CSS framework
- **ESBuild**: Fast JavaScript bundler for production

## Deployment Strategy

The application is configured for deployment on Replit with:
- **Development**: Hot-reload development server with Vite
- **Production**: Optimized build with static file serving
- **Database**: Environment-based configuration for different deployment stages
- **Environment Variables**: Secure handling of API keys and database credentials

### Build Process
1. Frontend builds to `dist/public` directory
2. Backend bundles with ESBuild to `dist/index.js`
3. Static files served by Express in production
4. Database migrations managed through Drizzle Kit

## Changelog
- July 07, 2025. Initial setup
- July 07, 2025. Complete resume parser application implemented with:
  - Full-stack architecture with React frontend and Express backend
  - AI-powered resume parsing using OpenAI API
  - PostgreSQL database with user and resume tables
  - File upload support for PDF, DOC, and DOCX formats
  - Comprehensive form interface for editing extracted data
  - Real-time processing feedback with progress indicators
  - Responsive design with modern UI components

## User Preferences

Preferred communication style: Simple, everyday language.