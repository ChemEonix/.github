# GitHub Copilot Instructions for ChemEonix Projects

## Core Architecture & Philosophy

Our architecture strictly separates concerns. The frontend is for presentation, and the backend is for business logic and data. All portfolio and static content is sourced from a central `lib/data.ts` file, not hardcoded in components. Our frontend is built with a component-driven design using small, reusable, single-purpose components.

## Frontend (Next.js)

-   **Framework**: Next.js 14+ with the App Router.
-   **Language**: TypeScript (strict mode).
-   **Styling**: Tailwind CSS. Do not use custom CSS files or inline styles.
-   **UI Components**: We use `shadcn/ui`. All UI primitives (buttons, cards, etc.) must be imported from `@/components/ui`. Do not reinvent basic components.
-   **State Management**: For simple, local state, use React Hooks (`useState`, `useEffect`). For complex, global client-side state, use `Zustand`. For server state, caching, and data fetching, use `TanStack Query (React Query)`.
-   **Data Fetching**: All data fetching from our backend APIs should be managed through TanStack Query.
-   **Animations**: Use `Framer Motion` for all UI animations. Keep them subtle and professional.
-   **Code Quality**: Adhere strictly to the rules defined in `.eslintrc.json` and format code with Prettier on save.

## Backend (FastAPI)

-   **Framework**: FastAPI.
-   **Language**: Python 3.11+.
-   **Code Quality**: All Python code must be formatted and linted with `Ruff` according to the rules in `pyproject.toml`.
-   **Dependencies**: Manage all dependencies with `uv`.
-   **API Design**: Adhere to RESTful principles. Use Pydantic for data validation and serialization.
-   **Database**: Use SQLAlchemy for ORM with PostgreSQL.
-   **Containerization**: All backend services must be fully containerized with Docker.

## General Conventions

-   **File Naming**: Use kebab-case for all file and folder names (e.g., `user-profile.tsx`).
-   **Component Naming**: Use PascalCase for React components (e.g., `UserProfile`).
-   **Commits**: Write clear, concise commit messages following the Conventional Commits specification.