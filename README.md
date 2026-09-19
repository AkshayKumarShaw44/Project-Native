<div align="center">

  <img src="./assets/images/logo-glow.png" alt="Grocify Logo" width="120" height="120" />

  # 🛒 Grocify

  ### Modern Full-Stack Grocery & Pantry Planner Mobile App

  [![React Native](https://img.shields.io/badge/React_Native-0.83.2-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactnative.dev/)
  [![Expo](https://img.shields.io/badge/Expo-v55.0-000000?style=for-the-badge&logo=expo&logoColor=white)](https://expo.dev/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![Clerk](https://img.shields.io/badge/Clerk-Auth-6C47FF?style=for-the-badge&logo=clerk&logoColor=white)](https://clerk.com/)
  [![Neon Database](https://img.shields.io/badge/Neon-PostgreSQL-00E599?style=for-the-badge&logo=postgresql&logoColor=black)](https://neon.tech/)
  [![Drizzle ORM](https://img.shields.io/badge/Drizzle_ORM-v0.45-C5F74F?style=for-the-badge&logo=drizzle&logoColor=black)](https://orm.drizzle.team/)
  [![TailwindCSS](https://img.shields.io/badge/NativeWind-v4.2-38BDF8?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://nativewind.dev/)
  [![Sentry](https://img.shields.io/badge/Sentry-Monitoring-362D59?style=for-the-badge&logo=sentry&logoColor=white)](https://sentry.io/)

  <p align="center">
    <b>Streamline your grocery shopping with real-time cloud sync, priority tagging, analytics, and slick glassmorphic UI.</b>
  </p>

  <p align="center">
    <a href="#-features">Key Features</a> •
    <a href="#-tech-stack--architecture">Tech Stack</a> •
    <a href="#-getting-started">Getting Started</a> •
    <a href="#-environment-variables">Environment Setup</a> •
    <a href="#-database--seeding">Database</a> •
    <a href="#-project-structure">Project Structure</a>
  </p>

  ---

  <img src="./assets/images/hero.png" alt="Grocify Hero Banner" width="100%" style="border-radius: 12px; margin: 20px 0;" />

</div>

---

## 📖 Overview

**Grocify** is a production-ready, cross-platform full-stack mobile application designed to simplify grocery list management and pantry planning. Built with **React Native (Expo SDK 55)** and **Expo Router**, it features seamless OAuth authentication with **Clerk**, real-time serverless database integration using **Drizzle ORM & Neon PostgreSQL**, state management powered by **Zustand**, and beautiful iOS liquid-glass tabs crafted with **NativeWind (Tailwind CSS)**.

---

## ✨ Features

### 🔐 Authentication & User Profiles
- **Multi-Provider SSO**: Instant login via Google, Apple, and GitHub powered by Clerk SDK.
- **Secure Sessions**: Expo Secure Store token persistence and automatic redirect routes.
- **User Dashboard**: Displays user avatar, email address, and single-tap logout flow.

### 🛒 Intelligent List Management
- **Active vs Completed**: Categorized lists separating pending items from checked items.
- **Interactive Checkbox**: Quick check/uncheck toggle with instant serverless sync.
- **Quantity Adjustments**: Micro-controls to scale quantities (`+` / `-`) on the fly.
- **Single-Tap Clear**: Bulk clear all completed items to keep your list clutter-free.
- **Swipe & Delete**: Instant deletion of outdated or unneeded items.

### 📝 Smart Planner & Item Creator
- **Categorization**: Organize groceries into 5 key categories: *Produce*, *Dairy*, *Bakery*, *Pantry*, and *Snacks*.
- **Priority Indicators**: Set item priority (*Low*, *Medium*, *High*) with distinct color badges.
- **Custom Quantity Selection**: Fine-tune required quantities before adding to list.

### 📊 Analytics & Insights
- **Shopping Breakdown**: Visual overview of active vs completed item ratios.
- **Category Statistics**: Distribution summary across food groups.
- **User Feedback Portal**: Integrated feedback modal for feature requests and bug reports.

### 🎨 Design & Experience
- **Liquid Glass Tab Bar**: Native iOS glassmorphism tab design using `expo-glass-effect`.
- **Theme Support & NativeWind**: Scalable Tailwind CSS utility classes customized for mobile screens.
- **Cross-Platform**: Seamless performance on iOS, Android, and Web platforms.
- **Sentry Crash Analytics**: Real-time error monitoring and performance tracking.

---

## 🛠️ Tech Stack & Architecture

| Category | Technology | Description |
| :--- | :--- | :--- |
| **Framework** | [React Native](https://reactnative.dev/) + [Expo](https://expo.dev/) (v55) | Cross-platform mobile development engine |
| **Routing** | [Expo Router](https://docs.expo.dev/router/introduction/) (v55) | File-based navigation & API endpoints |
| **Database** | [Neon PostgreSQL](https://neon.tech/) | Serverless Postgres database in the cloud |
| **ORM** | [Drizzle ORM](https://orm.drizzle.team/) | Type-safe database queries & migration tooling |
| **Authentication**| [Clerk Auth](https://clerk.com/) | Identity management with OAuth & SSO |
| **State Management**| [Zustand](https://zustand-demo.pmnd.rs/) (v5) | Lightweight client-side reactive store |
| **Styling** | [NativeWind](https://nativewind.dev/) (v4) + TailwindCSS | Utility-first CSS engine for React Native |
| **Monitoring** | [Sentry](https://sentry.io/) | Application performance & error tracking |

### 🏗️ Data Architecture Flow

```
┌─────────────────────────┐          ┌──────────────────────────┐
│  React Native App       │          │  Clerk Cloud Auth        │
│  (Expo SDK 55 Client)   │─────────►│  (OAuth / User Sessions) │
└────────────┬────────────┘          └──────────────────────────┘
             │
             │ Fetch / API Requests
             ▼
┌─────────────────────────┐
│ Expo Router API Routes  │
│ (/src/app/api/items)    │
└────────────┬────────────┘
             │
             │ Type-safe Queries
             ▼
┌─────────────────────────┐          ┌──────────────────────────┐
│ Drizzle ORM             │─────────►│ Neon PostgreSQL          │
│ (Schema & Client)       │          │ (Serverless Database)    │
└─────────────────────────┘          └──────────────────────────┘
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your local machine:
- **Node.js** (`v18.0.0` or higher)
- **npm** or **yarn** / **pnpm** / **bun**
- **Expo Go** app on your iOS/Android device OR **iOS Simulator** / **Android Studio Emulator**

### 1. Clone & Install Dependencies

```bash
git clone https://github.com/your-username/grocify.git
cd grocify
npm install
```

---

## ⚙️ Environment Variables

Create a `.env` file in the root directory of the project based on `.env.example`:

```bash
cp .env.example .env
```

Fill in the required credentials:

```ini
# Neon PostgreSQL Database Connection String
DATABASE_URL=postgresql://user:password@ep-example.neon.tech/grocify?sslmode=require

# Clerk Authentication Publishable Key
EXPO_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...

# Sentry Error Monitoring (Optional for production tracking)
EXPO_PUBLIC_SENTRY_DSN=https://example@sentry.io/123456
SENTRY_AUTH_TOKEN=sntryu_...
```

---

## 🗄️ Database & Seeding

Grocify utilizes **Drizzle ORM** connected to a serverless **Neon PostgreSQL** database.

### 1. Push Database Schema

Push the defined Drizzle schema (`src/lib/server/db/schema.ts`) to your Neon Postgres database:

```bash
npm run db:push
```

### 2. Seed Sample Grocery Data

Populate your database with starter grocery items:

```bash
npm run seed:grocery
```

---

## 🏃 Running the Application

Start the Expo development server:

```bash
# Start Expo Dev Server
npm start

# Run on iOS Simulator (macOS required)
npm run ios

# Run on Android Emulator
npm run android

# Run on Web Browser
npm run web
```

---

## 📂 Project Structure

```
grocify/
├── assets/                  # App icons, splash screens, and README media
│   └── images/              # Screen captures and brand logos
├── scripts/                 # Utility & database seed scripts
│   └── seed-grocery.cjs     # Pre-populates grocery items into Postgres
├── src/
│   ├── app/                 # Expo Router file-based pages & API routes
│   │   ├── (auth)/          # Authentication routes (Sign In / OAuth)
│   │   ├── (tabs)/          # Main Tab Navigator (List, Planner, Insights)
│   │   ├── api/             # Serverless REST API endpoints (/api/items)
│   │   └── _layout.tsx      # Root application layout with Clerk Provider
│   ├── components/          # Reusable UI components (List, Planner, Insights)
│   ├── hooks/               # Custom React hooks
│   ├── lib/                 # Database connection & Drizzle actions
│   │   └── server/db/       # Schema definitions & Neon client setup
│   └── store/               # Zustand global store for state management
├── app.json                 # Expo project configuration
├── drizzle.config.ts        # Drizzle ORM configuration
├── global.css               # Global Tailwind CSS definitions
├── nativewind-env.d.ts      # NativeWind type declarations
├── package.json             # App dependencies & scripts
└── tailwind.config.js       # Tailwind CSS design tokens
```

---

## 📜 Available Scripts

In the project directory, you can run:

| Command | Action |
| :--- | :--- |
| `npm start` | Runs `expo start` to initiate the Metro bundler |
| `npm run ios` | Boots iOS Simulator and runs the app |
| `npm run android` | Boots Android Emulator and runs the app |
| `npm run web` | Launches the app in a web browser |
| `npm run db:push` | Pushes Drizzle database schema to Neon Postgres |
| `npm run seed:grocery` | Seeds demo grocery items into the database |
| `npm run reset-project` | Cleans and resets initial project templates |

---

## 🤝 Contributing

Contributions are always welcome! If you'd like to improve Grocify:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

<div align="center">
  <p>Crafted with 🤟🏻 (swag) for frictionless grocery planning.</p>
  <p>⭐ Star this repository if you find it helpful!</p>
</div>

