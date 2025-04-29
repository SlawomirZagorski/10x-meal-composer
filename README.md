# 10x Meal Composer

> Meal Composer is an application enabling users to modify their favorite recipes based on available ingredients, dietary preferences, and kitchen equipment. It leverages LLMs via to generate recipe candidates and offers an interactive review experience.

## Table of Contents

- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [Project Scope](#project-scope)
- [Project Status](#project-status)
- [License](#license)

## Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript 5, Tailwind CSS 4, Shadcn/ui
- **Backend**: Supabase
- **AI**: Openrouter.ai
- **CI/CD & Hosting**: GitHub Actions, Vercel

## Getting Started

### Prerequisites

- Node.js (>= 23)
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/YourUsername/10x-meal-composer.git
cd 10x-meal-composer

# Install dependencies
npm ci
```

### Environment Variables

Create a `.env.local` file in the project root with the following:

```env
NEXT_PUBLIC_OPENROUTER_API_KEY=your_openrouter_api_key
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### Running Locally

```bash
npm run dev
```

Open your browser at `http://localhost:3000`.

## Available Scripts

- `npm run dev` - Runs the development server with Turbopack.
- `npm run build` - Builds the application for production.
- `npm run start` - Starts the production server.
- `npm run lint` - Runs ESLint and reports issues.

## Project Scope

This MVP focuses on:

- CRUD for accepted textual recipes (US-005, US-008).
- Generating new recipe candidates based on user input (US-006).
- Interactive review: accept, reject, and iterate (US-009, US-010, US-011).
- Manual ingredient input (free text).
- User profile with dietary preferences and kitchen equipment.
- Profile completion reminders when generating recipes (US-012).
- Basic event tracking and AI cost collection per user.

## Project Status

✅ Proof-of-concept completed for recipe generation (US-006).
🔄 Interactive review and persistence features are in progress.
🚧 Remaining features: user authentication, profile management, analytics, and deployment optimizations.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
