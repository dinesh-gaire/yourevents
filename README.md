# 🌍 YourEvents - A Full Stack Next.js App

## 🌍 Overview

YourEvents is a modern platform for discovering, managing, and hosting events. With features like secure authentication, dynamic event management, ticket purchasing via Stripe, and personalized user experiences, this app provides an all-in-one solution for event organizers and attendees.

Whether you want to browse global events, host your own, or manage ticket sales, this app is built to provide seamless interactions with intuitive design.

## 📋 Table of Contents

- 🌍 Overview
- 🔧 Features
- ⚙️ Tech Stack
- 🛠️ Setup and Installation
- 📝 Contributing
- 💬 Support

## 🔧 Features

### 🎟️ Event Management (CRUD)
- **Create Events**: Easily add new events with details like title, date, location, and description.
- **Read Events**: View event details including descriptions, schedules, and related information.
- **Update Events**: Modify event information as needed to keep it current.
- **Delete Events**: Remove events when they are no longer relevant or active.

### 🔑 User Authentication
- **Authentication with Clerk**: Secure user sign-ups, logins, and profile management.
- **User Roles**: Admin and regular user roles to control access to features.

### 🔍 Event Discovery
- **Smart Event Suggestions**: The app suggests related events to increase user engagement.
- **Search & Filter**: Search and filter events by categories, date, location, and more.
- **Event Categories**: Easily add, edit, and manage dynamic categories for events.

### 💳 Stripe Integration
- **Ticket Payments**: Secure payment processing for event tickets via Stripe.
- **Order Management**: Track orders and transactions with a detailed order management system.

### 🧑‍💻 Code Architecture
- **Modular Design**: The app is built using a reusable and scalable architecture, making it easy to extend.
- **TailwindCSS**: Styling is handled with TailwindCSS for a responsive and customizable design.
- **TypeScript**: Type-safe development using TypeScript to improve maintainability and reduce bugs.

## ⚙️ Tech Stack

The app uses the following technologies:
- **Node.js**: Backend server-side JavaScript runtime.
- **Next.js 14**: React framework with built-in server-side rendering and static site generation.
- **TypeScript**: Static typing for JavaScript, offering better tooling and developer experience.
- **TailwindCSS**: A utility-first CSS framework for responsive and customizable design.
- **Stripe**: Payment gateway for processing ticket purchases.
- **Clerk**: Authentication solution for managing users securely.
- **Zod**: Type-safe schema validation.
- **React Hook Form**: Simplifies form management in React.
- **Shadcn**: A set of reusable UI components for rapid development.
- **Uploadthing**: Handles file uploads for user-generated content (such as event images).
- **MongoDB**: NoSQL database for storing user and event data.

## 🛠️ Setup and Installation

### Clone the Repository
First, clone the project repository:
```bash
git clone https://github.com/dinesh-gaire/yourevents.git
cd yourevents
```

### Install Dependencies
Install the required npm dependencies:
```bash
npm install
```

### Configure Environment Variables
Create a `.env` file in the root of the project and copy the contents from `.env.example`. Then, add your actual API keys and credentials.

Here's the structure of the `.env` file:
```env
# NEXT.js config
NEXT_PUBLIC_SERVER_URL=

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
NEXT_CLERK_WEBHOOK_SECRET=

NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/

# MongoDB
MONGODB_URI=

# Uploadthing
UPLOADTHING_SECRET=
UPLOADTHING_APP_ID=

# Stripe
STRIPE_SECRET_KEY=
STRIPE_WEBHOOK_SECRET=
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=
```

Replace all placeholders with your actual API keys and credentials:
- `NEXT_PUBLIC_SERVER_URL` would be the URL of your server (e.g., http://localhost:3000)
- Stripe keys can be obtained from your Stripe Dashboard
- Clerk keys are available in the Clerk Dashboard

### Run the App
Once you have configured the environment variables, run the development server:
```bash
npm start
```
Visit http://localhost:3000 in your browser to access the app.

## 📝 Contributing

We welcome contributions! To contribute:
- Fork the repo and clone it to your local machine
- Create a new branch for your feature or bug fix
- Write tests for new features and ensure all tests pass
- Open a pull request with a description of the changes you've made

We follow the Contributor Covenant Code of Conduct.


## 💬 Support

If you encounter issues or have questions, feel free to open an issue in the Issues section. We'll be happy to help!

By following these instructions, you can get the app running locally and start using or contributing to the project. 🎉
