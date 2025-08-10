# Overview

This is a futuristic crypto investment profit calculator web application built as a full-stack TypeScript application. The project provides real-time cryptocurrency price tracking, investment profit/loss calculations, and multiple calculation modes including basic profit/loss tracking, future projections, and dollar-cost averaging (DCA). The application features a modern glassmorphism UI with neon glow effects, responsive design, and is optimized for Google AdSense monetization with SEO-friendly features.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The frontend is built using React 18 with TypeScript, utilizing Vite as the build tool for fast development and optimized production builds. The application uses a component-based architecture with shadcn/ui components for consistent styling and behavior. The UI framework leverages Tailwind CSS with custom CSS variables for theming, implementing glassmorphism effects and neon glow animations for a futuristic appearance.

State management is handled through React Query (TanStack Query) for server state and React's built-in useState for local component state. The routing is implemented using Wouter, a lightweight client-side router. The application supports both dark and light themes with a toggle component, defaulting to dark mode for the futuristic aesthetic.

Chart functionality is implemented using Chart.js for displaying price history and profit projections with smooth animations. The form handling uses React Hook Form with Zod validation for type-safe form inputs and validation.

## Backend Architecture
The backend is an Express.js server written in TypeScript, serving both API endpoints and static files. The server implements a RESTful API design with endpoints for cryptocurrency price fetching and calculation history storage. The architecture uses a middleware pattern for request logging, error handling, and CORS management.

The server integrates with the CoinGecko API to fetch real-time cryptocurrency prices for major coins including Bitcoin, Ethereum, Solana, Cardano, Ripple, Dogecoin, Polygon, and Litecoin. Price data is cached and updated at regular intervals to minimize API calls and improve performance.

For development, the server integrates with Vite's middleware system to provide hot module replacement and seamless full-stack development experience. In production, it serves pre-built static files from the dist directory.

## Data Storage Solutions
The application uses a dual storage approach. For development and simple deployments, it implements an in-memory storage system using Maps to store users, calculation history, and cryptocurrency prices. This provides fast access and eliminates database setup complexity for development.

For production deployments, the application is configured with Drizzle ORM and PostgreSQL support through the @neondatabase/serverless package. The database schema includes tables for users, calculation history, and cryptocurrency price caching. Drizzle provides type-safe database queries and automated migrations.

The schema supports storing calculation results as JSON objects, allowing for flexible storage of different calculation types (profit-loss, future projections, DCA, portfolio tracking) without requiring schema changes for new calculation features.

## Authentication and Authorization
The current implementation includes a basic user system with username/password authentication, though the frontend doesn't currently implement user registration or login flows. The backend storage interface supports user creation and retrieval, preparing the foundation for user-specific calculation history and portfolio tracking.

Session management is prepared through the connect-pg-simple package for PostgreSQL session storage, though not yet implemented in the current codebase. The architecture supports adding authentication middleware and protected routes as needed.

# External Dependencies

## Cryptocurrency Data Provider
The application integrates with the CoinGecko API (api.coingecko.com) for real-time cryptocurrency price data. This free API provides current prices, 24-hour price changes, and historical data for major cryptocurrencies. The integration includes error handling, rate limiting awareness, and automatic retry logic.

## Database Services
The application is configured to work with Neon Database (neon.tech) for PostgreSQL hosting, utilizing the @neondatabase/serverless package for serverless-optimized database connections. This provides automatic connection pooling and edge-compatible database access.

## UI Component Library
The frontend extensively uses Radix UI primitives through shadcn/ui components, providing accessible and customizable UI components. This includes form controls, dialogs, tooltips, navigation menus, and data visualization components.

## Chart and Visualization
Chart.js is integrated for creating animated price charts and profit projections. The charts support real-time updates, responsive design, and custom styling to match the futuristic theme.

## SEO and Metadata
React Helmet Async is used for managing document head elements, enabling dynamic SEO optimization with custom meta tags, titles, and Open Graph data for social sharing.

## Font and Icon Resources
The application uses Google Fonts (Inter family) for typography and Lucide React for consistent iconography throughout the interface.

## Development Tools
The project includes several development-specific integrations including Replit-specific plugins for error overlay and cartographer integration when running in the Replit environment.