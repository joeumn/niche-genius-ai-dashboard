# Niche Genius AI Forge - Developer Guide

This comprehensive guide covers the technical aspects, architecture, and development guidelines for the Niche Genius AI Forge dashboard application.

## Table of Contents

1. [Architecture Overview](#architecture-overview)
2. [Component Structure](#component-structure)
3. [State Management](#state-management)
4. [Theming System](#theming-system)
5. [Security Implementation](#security-implementation)
6. [Google Cloud Integration](#google-cloud-integration)
7. [Monetization Strategies](#monetization-strategies)
8. [Development Workflow](#development-workflow)
9. [Troubleshooting](#troubleshooting)
10. [Glossary](#glossary)
11. [FAQ](#faq)

## Architecture Overview

### Tech Stack Details

- **Next.js 15.3**
  - App Router for improved routing and layouts
  - Server Components for optimal performance
  - API Routes for backend functionality

- **TypeScript**
  - Strict type checking enabled
  - Custom type definitions in \`types/\` directory
  - Interface-first development approach

- **Tailwind CSS**
  - Custom theme configuration
  - Responsive design utilities
  - Dark mode support

- **Shadcn UI**
  - Reusable component library
  - Accessible by default
  - Customizable through Tailwind

### Directory Structure Explained

\`\`\`
src/
├── app/                    # Next.js app directory
│   ├── layout.tsx         # Root layout with providers
│   ├── page.tsx           # Dashboard page
│   └── globals.css        # Global styles
├── components/            # React components
│   ├── ui/               # Shadcn UI components
│   └── theme-toggle.tsx  # Theme switcher
├── providers/            # Context providers
├── hooks/               # Custom React hooks
└── lib/                # Utility functions
\`\`\`

## Component Structure

### Core Components

1. **Layout Component (\`src/app/layout.tsx\`)**
   - Root layout wrapper
   - Theme provider integration
   - Global styles application

2. **Dashboard Page (\`src/app/page.tsx\`)**
   - Main dashboard interface
   - Analytics display
   - Market insights presentation

3. **Theme Toggle (\`src/components/theme-toggle.tsx\`)**
   - Theme switching functionality
   - System theme detection
   - Persistent theme storage

### Best Practices

- Use TypeScript interfaces for props
- Implement error boundaries
- Add accessibility attributes
- Include proper documentation
- Follow component composition patterns

## State Management

### Theme Context

The application uses Next Themes for theme management:

\`\`\`typescript
// src/providers/theme-provider.tsx
export function ThemeProvider({ children, ...props }: ThemeProviderProps) {
  return <NextThemesProvider {...props}>{children}</NextThemesProvider>
}
\`\`\`

## Theming System

### Color Scheme

The application uses a carefully crafted color system:

\`\`\`css
:root {
  --background: oklch(1 0 0);
  --foreground: oklch(0.145 0 0);
  /* ... other color variables */
}

.dark {
  --background: oklch(0.145 0 0);
  --foreground: oklch(0.985 0 0);
  /* ... dark theme colors */
}
\`\`\`

### Theme Switching

Theme switching is handled through the ThemeToggle component:

\`\`\`typescript
export function ThemeToggle() {
  const { setTheme } = useTheme()
  // ... implementation
}
\`\`\`

## Security Implementation

### Authentication

1. **Setup Google Cloud Identity Platform**
   - Enable the service in Google Cloud Console
   - Configure OAuth 2.0
   - Set up email/password authentication

2. **Implement Protected Routes**
   - Create middleware for auth checks
   - Set up role-based access control
   - Handle authentication state

### Data Protection

1. **Environment Variables**
   - Store sensitive data in .env files
   - Use Google Cloud Secret Manager
   - Implement proper key rotation

2. **API Security**
   - Input validation
   - Rate limiting
   - CORS configuration

## Google Cloud Integration

### Setup Instructions

1. **Initial Setup**
\`\`\`bash
# Install Google Cloud SDK
curl https://sdk.cloud.google.com | bash

# Initialize SDK
gcloud init

# Set project
gcloud config set project YOUR_PROJECT_ID
\`\`\`

2. **Deployment Configuration**

Create \`app.yaml\`:
\`\`\`yaml
runtime: nodejs18
env: standard
instance_class: F1

automatic_scaling:
  target_cpu_utilization: 0.65
  min_instances: 1
  max_instances: 10

env_variables:
  NODE_ENV: "production"
\`\`\`

### Service Configuration

1. **Cloud Run Setup**
\`\`\`bash
# Build container
gcloud builds submit --tag gcr.io/PROJECT_ID/niche-genius-ai

# Deploy
gcloud run deploy niche-genius-ai \
  --image gcr.io/PROJECT_ID/niche-genius-ai \
  --platform managed
\`\`\`

2. **Database Integration**
   - Set up Cloud SQL
   - Configure connection pooling
   - Implement backup strategies

## Monetization Strategies

### 1. Subscription Tiers

- **Basic Plan**: $9.99/month
  - Basic market analysis
  - Limited API calls
  - Standard support

- **Pro Plan**: $29.99/month
  - Advanced analytics
  - Unlimited API calls
  - Priority support

- **Enterprise Plan**: Custom pricing
  - Custom features
  - Dedicated support
  - SLA guarantees

### 2. API Monetization

- Implement usage-based pricing
- Offer API key management
- Monitor API usage

### 3. Additional Revenue Streams

- Sponsored insights
- Premium reports
- Consultation services

## Development Workflow

### 1. Local Development

\`\`\`bash
# Start development server
npm run dev

# Run tests
npm test

# Build for production
npm run build
\`\`\`

### 2. Code Quality

- ESLint configuration
- Prettier setup
- Git hooks with Husky
- Continuous Integration

## Troubleshooting

### Common Issues

1. **Build Failures**
   - Check Node.js version
   - Clear .next directory
   - Verify dependencies

2. **Theme Issues**
   - Check localStorage
   - Verify CSS variables
   - Debug theme provider

3. **API Errors**
   - Validate environment variables
   - Check API permissions
   - Verify request format

## Glossary

- **App Router**: Next.js 13+ routing system
- **Server Components**: React components that render on the server
- **Shadcn UI**: Component library based on Radix UI
- **Tailwind CSS**: Utility-first CSS framework
- **TypeScript**: JavaScript with syntax for types

## FAQ

### Development

Q: How do I add a new component?
A: Create a new file in src/components, export the component, and import it where needed.

Q: How do I modify the theme?
A: Edit the theme variables in globals.css and tailwind.config.js.

### Deployment

Q: How do I deploy to Google Cloud?
A: Follow the deployment instructions in the Google Cloud Integration section.

Q: How do I update environment variables?
A: Use Google Cloud Console or update .env files locally.

### Troubleshooting

Q: Why isn't the theme switching working?
A: Verify the ThemeProvider is properly configured and localStorage is accessible.

Q: How do I debug API calls?
A: Use browser developer tools and check server logs in Google Cloud Console.

## Additional Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Google Cloud Documentation](https://cloud.google.com/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
