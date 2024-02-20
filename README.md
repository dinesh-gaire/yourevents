This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.


Step1: create next app
Step2: npx shadcn-ui@latest init
Step3: npx shadcn-ui@latest add button
        import { Button } from "@/components/ui/button"

        export default function Home() {
        return (
            <div>
            <Button>Click me</Button>
            </div>
        )
        }

        This automatically adds button.tsx file inside components/ui with necessary code


Step4: Update global.css and tailwind.config.ts
Step5: npm install uploadthing @uploadthing/react
        uploadthing is a package that allows for simple fil  upload -> for uploading events images

Step6: Create (auth) and (root) folder inside app
        Move pages.tsx from app to (root)

Replace Inter with Poppins as a font inside app/layout.tsx
Add weights and variable inside poppins
Update title and deescription and add logo inside metadata 
(Note: layout.tsx is layout for all files and folders inside app folder. But we can also add layout for each folders inside app by creating layout.tsx in each folder)

For logo and other necessary pictures add assests folder inside public with necessary pictures

Create layout.tsx inside app/(root)
Copy the code of function RootLayout only inside it

Create shared folder inside components and necessary files inside it (Header.tsx, Footer.tsx)

Import Header and Footer inside (root)/layout.tsx

Write necessary code in Header.tsx
Here we are going to use Clerk for authentication and User management
Set env keys
Go to CLerk and create app
npm install @clerk/nextjs
import ClerkProvider and then wrap code inside /src/app/layout.tsx
Create middleware.ts file in root directory and add necessary code copied from clerk website
Visit localhost to see the effect (If you want to add more social connections like Github, Facebook then goto User and Authentication/Social Connections)
Add necessary publicRoutes inside authMiddleware sothat users who are not logged in can also access those routes
Also add ignoredRoutes
Go to Header.tsx and wrap the Login button with Signout component from clerk -> The code inside Signout component is visible only when user is signed out
Create (auth)/sign-in/[[...sign-in]]/page.tsx write code
Create (auth)/sign-in/[[...sign-in]]/page.tsx write code
Create (auth)/layout.tsx and write code so that we can customize layout of signin and signup page

Add Signin component in Header.tsx and inside it add UserButton which display profile of user
Add NavItems and MobileNav
npx shadcn-ui@latest add sheet --> Here we are going to use sheet from sadchn for MobileNav
import and write code

npx shadcn-ui@latest add separator
import and use it inside MobileNav

Code for Navitems
Create constants/index.ts in root directory
Complete code for Navitems

Code for Footer.tsx

Code for (root)/page.tsx -> For home section up to h2->Trust by Thousands of events

Create database and events models
Create lib/database/index.ts &  lib/mongodb
npm install mongoose mongodb
(common pattern in used nodejs app specially in serverless env like vercel. This technique is used to cached a database connection in this case a mongodb connection via mongoose across multiple application of serverless API routes in nextjs)
Code for database/index.ts to make connection with database
Write User and Event model

npm install svix
Create types/index.ts
Create app/api/webhook/clerk/route.ts copy code and update -> this is one of our webhook events that create user in database as soon as new clerk user is created
Create lib/actions/user.actions.ts

Create lib/database/models/category.model.ts
Create lib/database/models/order.model.ts

Update code in utils.ts -> Copy Paste

Push code to github
Create account in vercel and connect repository and deploy
Go to webhooks in clerk dashboard and update url https://yourevents.vercel.app/api/webhook/clerk
WEBHOOK_SECRET=whsec_CDIYr9/1YWwWTiDMKaxoEuLMVhE7tvzm -> Get webhook and add to env variable in vercel
Signup the user then data added to database

Create components/shared/EventForm.tsx
Create (root)/events/[id]/update/page.tsx
Create (root)/events/create/page.tsx

npx shadcn-ui@latest add form
Create lib/validator.ts to add form validation

npx shadcn-ui@latest add select
Create components/Dropdown.tsx

npx shadcn-ui@latest add alert-dialog

npx shadcn-ui@latest add textarea

create components/FileUploader.tsx

npm install react-datepicker --save

npx shadcn-ui@latest add checkbox

Create actions/category.actions.ts

Create actions/event.actions.ts
Customize seession token in clerk dashboard/ sessions by adding object having userId as key
Update Event forms so that we can push the events to database

Create (root)/events/[id]/page.tsx to display event information
Update event.actions.ts
Update next.config.mjs so that you can accept image from uploadthing

Create components/shared/Collection.tsx
Add Collection to Home page

Create Card.tsx
Add Card to Collection
Create getEventById function in events.action.ts
Create updateEvent function in events.action.ts

Create deleteEvent function in events.action.ts
Create DeleteConfirmation.tsx
Add it to Card

Update (root)/events/[id]/update/page.tsx
Update EventForms 

Update (root)/events/[id]/page.tsx to show related events

Create (root)/profile/page.tsx

Create CheckoutButton.tsx
Create Checkout.tsx
Add Stripe integration in Checkout.tsx
update .env.local

Create order.actions.ts

Add stripe webhook to the application:
Add endpoint url: https://yourevents.vercel.app/api/webhook/stripe
Select event to listen to checkout.session.completed
Copy the code
Add endpoint
Create app/api/webhooks/stripe/route.ts and paste the copied code
Copy signing secret from stripe 

Update profile/page.tsx to display mytickets

Create (root)/orders/page.tsx

Create components/Search.tsx
Create components/CategoryFilter.tsx
Update both on home page





















