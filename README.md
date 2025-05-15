# Niche Genius AI Forge

A modern, AI-powered dashboard application for niche market analysis and insights, built with Next.js, TypeScript, and Tailwind CSS.

## Features

- 🎨 Modern, responsive UI with dark/light mode support
- 📊 Interactive dashboard with real-time analytics
- 📈 Market insights and trend analysis
- 🔒 Secure authentication and authorization
- ☁️ Google Cloud integration ready
- 📱 Mobile-friendly design

## Tech Stack

- **Frontend:**
  - Next.js 15.3
  - TypeScript
  - Tailwind CSS
  - Shadcn UI Components
  - Lucide Icons

- **Development Tools:**
  - ESLint
  - Prettier
  - PostCSS

## Getting Started

### Prerequisites

- Node.js 18.x or higher
- npm or yarn
- Git

### Installation

1. Clone the repository:
\`\`\`bash
git clone https://github.com/yourusername/niche-genius-ai-forge.git
cd niche-genius-ai-forge
\`\`\`

2. Install dependencies:
\`\`\`bash
npm install
# or
yarn install
\`\`\`

3. Start the development server:
\`\`\`bash
npm run dev
# or
yarn dev
\`\`\`

The application will be available at [http://localhost:8000](http://localhost:8000)

## Project Structure

\`\`\`
niche-genius-ai-forge/
├── src/
│   ├── app/                 # Next.js app directory
│   │   ├── layout.tsx      # Root layout
│   │   ├── page.tsx        # Main dashboard page
│   │   └── globals.css     # Global styles
│   ├── components/         # React components
│   │   ├── ui/            # Shadcn UI components
│   │   └── theme-toggle.tsx# Theme switcher
│   ├── providers/         # Context providers
│   │   └── theme-provider.tsx
│   ├── hooks/            # Custom React hooks
│   └── lib/              # Utility functions
├── public/              # Static assets
├── next.config.ts      # Next.js configuration
├── postcss.config.mjs  # PostCSS configuration
├── tailwind.config.js  # Tailwind CSS configuration
└── package.json        # Project dependencies
\`\`\`

## Development

### Code Style

- Follow TypeScript best practices
- Use ES6+ features
- Follow the Airbnb JavaScript Style Guide
- Use meaningful variable and function names
- Add JSDoc comments for functions and components

### Components

The UI components are built using Shadcn UI, which provides a set of accessible, reusable, and customizable components. The components are located in \`src/components/ui/\`.

### Styling

- Use Tailwind CSS for styling
- Follow the BEM naming convention for custom CSS classes
- Use CSS variables for theming
- Maintain responsive design principles

## Deployment

### Google Cloud Setup

1. Create a new Google Cloud project
2. Enable required APIs:
   - Cloud Run
   - Cloud Build
   - Container Registry

3. Install and configure Google Cloud CLI

4. Build and deploy:
\`\`\`bash
# Build the container
gcloud builds submit --tag gcr.io/PROJECT_ID/niche-genius-ai

# Deploy to Cloud Run
gcloud run deploy niche-genius-ai \
  --image gcr.io/PROJECT_ID/niche-genius-ai \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
\`\`\`

## Security

- All API routes are protected with appropriate authentication
- Environment variables are used for sensitive data
- Input validation is implemented for all forms
- HTTPS is enforced in production
- Regular security audits are performed

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, email support@nichegeniusai.com or join our Slack channel.

## Roadmap

- [ ] Advanced analytics dashboard
- [ ] AI-powered market predictions
- [ ] Integration with more data sources
- [ ] Enhanced user authentication
- [ ] Mobile app development
- [ ] API documentation
- [ ] Performance optimization
- [ ] Automated testing suite

## Acknowledgments

- Next.js team for the amazing framework
- Shadcn UI for beautiful components
- Tailwind CSS team for the utility-first CSS framework
- All contributors who have helped with the project
