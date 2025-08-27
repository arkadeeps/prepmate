# 🚀 PrepMate - AI-Powered Career Coach

[![Next.js](https://img.shields.io/badge/Next.js-15.1.4-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.0.0-blue?style=flat-square&logo=react)](https://reactjs.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6.8.2-2D3748?style=flat-square&logo=prisma)](https://prisma.io/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4.1-38B2AC?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![Clerk](https://img.shields.io/badge/Clerk-Auth-purple?style=flat-square&logo=clerk)](https://clerk.com/)

**PrepMate** is an AI-powered career coaching platform that helps professionals accelerate their career growth through personalized guidance, interview preparation, resume optimization, and industry insights.

---

## ✨ Features

- 🧠 **AI-Powered Career Guidance** – Personalized advice, industry insights, real-time market trends  
- 📝 **Smart Resume Builder** – ATS-optimized resumes, AI feedback, professional templates  
- 💼 **Interview Preparation** – Role-specific questions, behavioral & technical assessments, AI scoring  
- 📊 **Industry Insights** – Salary data, in-demand skills, growth trends, career paths  
- 📄 **AI Cover Letter Generator** – Tailored letters for roles/companies with professional formatting  
- 📈 **Progress Tracking** – Dashboard analytics, history, and personalized recommendations  

---

## 🛠️ Tech Stack

- **Frontend:** Next.js 15, React 19, Tailwind CSS  
- **Backend:** Next.js API Routes, Server Actions  
- **Database:** PostgreSQL + Prisma ORM  
- **Auth:** Clerk  
- **AI:** Google Gemini  
- **UI:** Radix UI, shadcn/ui  
- **Styling:** Tailwind CSS (custom animations)  
- **Background Jobs:** Inngest  
- **PDF Generation:** html2pdf.js  

---

## 🚀 Getting Started

### Prerequisites

- Node.js **18+**  
- PostgreSQL instance (local or cloud)  
- **GEMINI_API_KEY** (Google AI Studio / Cloud)  
- **Clerk** account & keys

---

## Installation & Install dependencies

1. **Clone the repository**
```bash
git clone https://github.com/arkadeeps/prepmate.git
cd prepmate
```

2. **Install dependencies**
```bash
# Using npm
npm install

# or using pnpm
pnpm install

# or using yarn
yarn install
```

> If you're using `node` managers like `nvm`, make sure you're on Node 18+:
```bash
nvm use 18
```

---

## Environment variables

Create a `.env.local` file in the project root and add the following (replace values with your real keys):

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/prepmate"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_your_publishable_key_here
CLERK_SECRET_KEY=sk_test_your_secret_key_here
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/onboarding
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/onboarding

# Google Gemini
GEMINI_API_KEY=your_actual_gemini_api_key_here

# Optional: other settings
NEXTAUTH_URL=http://localhost:3000
```

**Security tip:** Never commit `.env.local` to version control. Add it to `.gitignore`.

---

## Database setup

Generate Prisma client and push schema to your database:

```bash
npx prisma generate
npx prisma db push
```

(Optional) Open Prisma Studio:
```bash
npx prisma studio
```

If you want migrations instead of `db push`:
```bash
npx prisma migrate dev --name init
```

---

## Run the development server

```bash
npm run dev
```

Open http://localhost:3000 in your browser.

For production build & serve:
```bash
npm run build
npm start
```

---

## 📁 Project Structure

```
prepmate/
├── app/                 # Next.js App Router
│   ├── (auth)/          # Authentication routes (sign-in, sign-up)
│   ├── (main)/          # Main application routes (dashboard, resume, interview, etc.)
│   ├── api/             # API routes
│   └── globals.css      # Global styles
├── actions/             # Server Actions (resume, interview, cover-letter, etc.)
├── components/          # Reusable UI components (shadcn/ui wrappers, layout, header)
├── data/                # Static content (features, FAQs, testimonials, industries)
├── hooks/               # Custom React hooks
├── lib/                 # Utilities (prisma client, helpers, inngest jobs)
├── prisma/              # Prisma schema & migrations
├── public/              # Static assets (images, icons)
├── scripts/             # Optional scripts (seeds, maintenance)
└── package.json
```

---

## 🔧 Available Scripts

```bash
# Development
npm run dev          # Start development server with Turbopack (or next)

# Production
npm run build        # Build for production
npm start            # Start production server

# Linting & Formatting
npm run lint         # Run ESLint
npm run format       # (if configured) Run Prettier

# Prisma
npx prisma generate
npx prisma db push
npx prisma studio
```

---

## 🔐 Authentication & Security

- **Clerk** for authentication (social providers & SSO)  
- Protected routes via server-side checks and middleware  
- Input validation & rate limiting on API endpoints  
- Sensitive keys stored in environment variables  
- HTTPS recommended in production (handled by hosting like Vercel)

---

## 🤖 AI Integration

PrepMate uses **Google Gemini** for:

- Career guidance and personalized recommendations  
- Resume content suggestions & ATS optimization hints  
- Interview question generation and AI feedback  
- Industry trend analysis and salary insights

> Ensure your Gemini API key has proper access and quotas for your usage patterns.

---

## 🎨 UI/UX & Accessibility

- Responsive, mobile-first layout  
- Light/Dark mode theme switching  
- ARIA-compliant components for accessibility  
- Smooth animations built with Tailwind CSS utilities  
- Modern, clean design using shadcn/ui + Radix primitives

---

## 📊 Performance & SEO

- Next.js 15 + Turbopack for fast builds and development  
- Automatic route-level code splitting  
- Next.js Image optimization for media assets  
- Structured metadata & SEO-friendly server rendering where applicable

---

## 🚀 Deployment

### Vercel (Recommended)
1. Push repository to GitHub.  
2. Import the repo into Vercel.  
3. Add environment variables in Vercel Project Settings (use the same keys as `.env.local`).  
4. Deploy — Vercel will build on each push to `main` (or your selected branch).

### Other Hosts (manual)
```bash
npm run build
npm start
```
Ensure environment variables are provided by the host (e.g., Render, Railway, Heroku, DigitalOcean App Platform).

---

## 🤝 Contributing

1. Fork the repository  
2. Create a branch: `git checkout -b feature/your-feature`  
3. Commit changes: `git commit -m "feat: add your feature"`  
4. Push: `git push origin feature/your-feature`  
5. Open a Pull Request and describe your changes

>Please add tests or manual verification steps for non-trivial features.

## 📝 License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/)  
- [Clerk](https://clerk.com/)  
- [Prisma](https://prisma.io/)  
- [Google AI / Gemini](https://ai.google.dev/)  
- [shadcn/ui](https://ui.shadcn.com/)  
- [Tailwind CSS](https://tailwindcss.com/)

---

**Made with ❤️ by the PrepMate Team**  
Website: https://prepmate-eta.vercel.app • Contact: contact@prepmate.com • Twitter: https://twitter.com/prepmate
