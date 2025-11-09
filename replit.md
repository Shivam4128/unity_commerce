# Unity Commerce - Export Platform

## Overview

Unity Commerce is a B2B e-commerce platform focused on exporting certified Ayurvedic herbs, botanical extracts, and natural ingredients from India to global markets. The platform serves as a digital storefront and informational hub for international buyers seeking compliant, quality-driven access to Indian herbal products. It emphasizes trust, transparency, and regulatory compliance across multiple international trade regions including North America, Europe, and the Middle East.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build System**
- React 18 with TypeScript for type-safe component development
- Vite as the build tool and development server, providing fast HMR and optimized production builds
- Wouter for lightweight client-side routing (single-page application pattern)

**UI Component System**
- shadcn/ui components built on Radix UI primitives for accessible, customizable interface elements
- Tailwind CSS for utility-first styling with a custom design system
- Design approach inspired by professional B2B platforms (Stripe, Shopify Partners, AWS) combined with Material Design principles
- Custom theme system using CSS variables for consistent brand colors and elevation states
- Typography: Inter for headings/UI, Source Sans Pro for body text (Google Fonts)

**State Management**
- TanStack Query (React Query) for server state management and data fetching
- Custom hooks for UI concerns (intersection observer for scroll animations, mobile detection)
- Form handling via react-hook-form with Zod validation

**Key Frontend Patterns**
- Section-based landing page architecture (Hero, About, Products, Certifications, Geographic Reach, Why Partner, Contact, Footer)
- Intersection observer pattern for scroll-triggered animations to enhance user engagement
- Responsive design with mobile-first breakpoints
- Smooth scroll navigation between sections

### Backend Architecture

**Server Framework**
- Express.js running on Node.js with TypeScript
- HTTP server created via Node's native `http` module
- Development mode uses Vite's middleware mode for seamless integration with frontend

**API Structure**
- RESTful API design with `/api` prefix for all application routes
- Request logging middleware capturing method, path, status, duration, and JSON responses
- Body parsing for JSON and URL-encoded data
- Raw body access for webhook verification scenarios

**Current State**
- Minimal backend implementation with placeholder route registration
- In-memory storage layer (MemStorage) implementing a storage interface pattern
- Storage interface designed for CRUD operations on User entities
- Prepared for future expansion to include product catalogs, inquiries, and order management

### Data Layer

**Database Setup**
- Drizzle ORM configured for PostgreSQL dialect
- Neon Database serverless driver for PostgreSQL connections
- Schema-first approach with TypeScript type inference
- Migrations stored in `/migrations` directory
- Zod integration for runtime schema validation

**Current Schema**
- Users table with UUID primary keys, username, and password fields
- Schema validation using drizzle-zod for type-safe inserts
- Database configuration requires `DATABASE_URL` environment variable

**Storage Pattern**
- Abstract storage interface (IStorage) defining contract for data operations
- In-memory implementation (MemStorage) for development/testing
- Architecture supports swapping to database-backed storage without changing business logic
- User operations: getUser, getUserByUsername, createUser

### External Dependencies

**UI & Component Libraries**
- @radix-ui/* (v1.x): Comprehensive primitive component library for accessible UI elements including dialogs, dropdowns, navigation, tooltips, and form controls
- shadcn/ui: Pre-built component patterns configured in components.json with "new-york" style
- class-variance-authority: Type-safe variant styling for components
- tailwindcss: Utility-first CSS framework with custom configuration
- lucide-react: Icon library for consistent iconography
- embla-carousel-react: Carousel/slider functionality

**Data & Forms**
- @tanstack/react-query (v5): Server state management and caching
- react-hook-form: Performant form handling with validation
- @hookform/resolvers: Integration layer for validation libraries
- zod: Schema validation for runtime type checking
- drizzle-zod: Bridge between Drizzle ORM schemas and Zod validators

**Database & ORM**
- drizzle-orm (v0.39): TypeScript ORM with strong type inference
- @neondatabase/serverless: PostgreSQL client optimized for serverless/edge environments
- connect-pg-simple: PostgreSQL session store for Express (prepared for session management)

**Routing & Navigation**
- wouter: Minimalist router for React (~1.2KB)
- Client-side routing with smooth scroll navigation to page sections

**Development Tools**
- @replit/vite-plugin-runtime-error-modal: Development error overlay
- @replit/vite-plugin-cartographer: Replit-specific development tooling
- @replit/vite-plugin-dev-banner: Development environment indicators
- tsx: TypeScript execution for development server
- esbuild: Fast bundler for production server build

**Utilities**
- clsx & tailwind-merge: Conditional class name composition
- date-fns: Date formatting and manipulation
- nanoid: Secure unique ID generation
- cmdk: Command menu component

**Design Assets**
- Google Fonts integration (Inter, Source Sans Pro)
- Custom hero image and product imagery stored in attached_assets
- Favicon and brand assets

### Authentication & Session Management

**Prepared Infrastructure**
- Session store dependency (connect-pg-simple) installed for PostgreSQL-backed sessions
- User schema in place with username/password fields
- Storage interface includes user lookup by username
- No active authentication implementation yet—prepared for future auth middleware

### Build & Deployment

**Development**
- `npm run dev`: Runs Express server with tsx in NODE_ENV=development
- Vite middleware mode serves frontend with HMR
- TypeScript type checking via `npm run check`

**Production**
- `npm run build`: Vite builds frontend to dist/public, esbuild bundles server to dist/
- `npm start`: Runs bundled server in NODE_ENV=production
- Static file serving handled by Express in production mode

**Database Operations**
- `npm run db:push`: Drizzle schema push to database without migrations

### Design System & Branding

**Color Strategy**
- Primary: Green theme (hsl 142 76% 36%) representing natural, Ayurvedic focus
- Neutral base colors with semantic naming (background, foreground, muted, accent)
- Card elevation system using subtle borders and shadows
- Light mode only (dark mode classes present but not actively used)

**Component Patterns**
- Elevation states: hover-elevate, active-elevate-2 for tactile feedback
- Consistent border radius: lg (9px), md (6px), sm (3px)
- Shadow system: shadow-xs, shadow-sm, shadow-md for depth hierarchy
- Button variants: default, destructive, outline, secondary, ghost
- Spacing system using Tailwind's 4-based scale

**Responsive Breakpoints**
- Mobile-first approach with sm (640px), md (768px), lg (1024px) breakpoints
- Container max-widths: 7xl for full sections, 6xl for content, 4xl for text-heavy areas
- Mobile menu implementation using sheet/drawer pattern