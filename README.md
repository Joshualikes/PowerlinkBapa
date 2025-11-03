# PowerLink Admin Dashboard

A comprehensive admin dashboard for managing consumers, billing, applications, and announcements.

## Features

- **Admin Dashboard**: Complete overview with analytics and charts
- **Consumer Management**: View and manage consumer accounts
- **Billing System**: Track payments and generate bills
- **Application Processing**: Handle consumer applications
- **Announcements**: Create and manage system announcements
- **Authentication**: Secure login system

## Tech Stack

- **Framework**: Next.js 14 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **UI Components**: Shadcn/ui
- **Database**: PostgreSQL/MySQL (configurable)
- **Charts**: Recharts
- **Authentication**: Stack Auth

## Getting Started

### Prerequisites

- Node.js 18+ 
- pnpm (recommended) or npm
- PostgreSQL or MySQL database

### Installation

1. Clone the repository
2. Install dependencies:
   \`\`\`bash
   pnpm install
   \`\`\`

3. Set up environment variables:
   - Copy `.env.local` and fill in your database connection details
   - Configure authentication keys if using Stack Auth

4. Set up the database:
   - For PostgreSQL: Run `scripts/01_create_tables.sql`
   - For MySQL: Run `scripts/01_create_tables_mysql.sql`
   - Run seed data: `scripts/02_seed_data.sql` or `scripts/02_seed_data_mysql.sql`

5. Start the development server:
   \`\`\`bash
   pnpm dev
   \`\`\`

6. Open [http://localhost:3000](http://localhost:3000) in your browser

### Database Setup

The project includes SQL scripts for both PostgreSQL and MySQL:

- **PostgreSQL**: Use files without `_mysql` suffix
- **MySQL**: Use files with `_mysql` suffix

Run the scripts in order:
1. `01_create_tables[_mysql].sql` - Creates all tables
2. `02_seed_data[_mysql].sql` - Adds sample data
3. Additional migration scripts as needed

### Project Structure

\`\`\`
├── app/                    # Next.js app directory
│   ├── admin/             # Admin dashboard pages
│   ├── api/               # API routes
│   ├── dashboard/         # Consumer dashboard
│   └── login/             # Authentication pages
├── components/            # Reusable UI components
├── lib/                   # Utility functions and configurations
├── scripts/               # Database scripts
└── public/                # Static assets
\`\`\`

### Environment Variables

Required environment variables:

- `DATABASE_URL`: Your database connection string
- `NEXTAUTH_SECRET`: Secret for NextAuth.js
- `NEXT_PUBLIC_STACK_PROJECT_ID`: Stack Auth project ID (if using)
- `STACK_SECRET_SERVER_KEY`: Stack Auth secret key (if using)

### Development

- `pnpm dev` - Start development server
- `pnpm build` - Build for production
- `pnpm start` - Start production server
- `pnpm lint` - Run ESLint

### Deployment

The project is configured for deployment on Vercel with automatic environment variable detection.

## License

MIT License
