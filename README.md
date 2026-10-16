# City Connect — A Complaint Management Platform

A responsive React + TypeScript frontend starter based on the supplied City Connect Master Prompt. It includes 27 principal route entries, shared layouts, role-aware navigation, accessible forms, demo-labelled sample data, charts, and API contract notes.

> **Important:** The backend API was not provided with the PDF. This project therefore runs in clearly labelled **Demo Mode**. Demo interactions demonstrate frontend flow only; they do not create or update real complaints. No backend endpoints are represented as confirmed.

## Features
- Public home, About, complaint submission, token tracking, resolved complaints, login and citizen registration.
- Citizen, Ward Clerk, Department Clerk, Mayor and System Admin portal routes.
- Responsive sidebar/top bar, search, filters, status badges, charts and table layouts.
- Anonymous tracking UI requests only the tracking token.
- Registration only creates citizen-style accounts; there is no public privileged-role selector.
- Clear demo-data labels, loading/error/empty-state patterns and API contract TODOs.
- Warm palette: `#F9F8F6`, `#EFE9E3`, `#D9CFC7`, `#C9B59C`.

## Technology stack
- React + TypeScript — component-based UI and typed domain models.
- Vite — local development server and production build.
- React Router — page routing.
- Lucide React — consistent interface icons.
- Recharts — dashboard charts.

## Routes
| Route | Purpose |
|---|---|
| `/` | Public home |
| `/about` | About City Connect |
| `/complaints/new` | Submit complaint |
| `/track` | Track by token |
| `/resolved-complaints` | Public resolved showcase |
| `/login` | Sign in |
| `/register` | Citizen registration |
| `/citizen/dashboard` | Citizen overview |
| `/citizen/complaints` | Citizen complaint list |
| `/citizen/complaints/:id` | Citizen complaint details |
| `/citizen/profile` | Citizen profile |
| `/ward/dashboard` | Ward Clerk overview |
| `/ward/complaints` | Ward queue |
| `/ward/complaints/:id` | Ward complaint details |
| `/ward/public-progress` | Public progress and deadlines |
| `/department/dashboard` | Department overview |
| `/department/complaints` | Department queue |
| `/department/complaints/:id` | Department complaint details |
| `/mayor/dashboard` | Mayor overview |
| `/mayor/reports` | Reports and analytics |
| `/admin/dashboard` | System Admin overview |
| `/admin/users` | Staff and roles |
| `/admin/locations` | Zone and ward management |
| `/admin/departments` | Department management |
| `/admin/categories` | Categories and routing |
| `/notifications` | Notifications |
| `/unauthorized` | Access denied |

## Prerequisites
Install a current LTS version of Node.js (npm is included). Confirm with:
```powershell
node -v
npm -v
```

## Windows PowerShell setup
1. Extract the ZIP file.
2. Open VS Code.
3. Select **File → Open Folder** and choose the extracted `city-connect` folder.
4. Open **Terminal → New Terminal**. Make sure the terminal is in the folder containing `package.json`.
5. Install dependencies and start the server:
```powershell
npm install
npm run dev
```
6. Open the local URL Vite prints (usually `http://localhost:5173`).
7. Stop the server with `Ctrl+C` in that terminal.

To reopen later, open the same folder and run `npm run dev`. Do not run `npm create vite` again.

## Environment variables
Copy `.env.example` to `.env` if needed. Set `VITE_API_BASE_URL` only to the API base URL confirmed by the backend team. Vite variables are public in the browser; never place passwords, secret keys or database credentials in them.

`VITE_DEMO_MODE=true` documents that the current app is a local demonstration. Actual API integration is not complete because no backend contract was supplied.

## Build and checks
```powershell
npm run typecheck
npm run build
npm run preview
```
Only use scripts present in `package.json`. The build may be run after dependencies are installed.

## Demo mode and data
The UI contains sample complaint rows and illustrative chart values, marked **DEMO DATA**. They are not live city statistics and must be replaced with API responses before production. Demo form submissions show a local confirmation only. No real tracking token is generated locally.

## Roles and privacy
- Anonymous citizens can submit without logging in and track using a 16-character token.
- Verified citizens should only see their own records after backend authorization.
- Ward Clerks should only access their assigned wards.
- Department Clerks should only access authorized department/ward assignments; internal notes must not appear in public views.
- Mayor dashboard is read-only in V1 unless the backend contract says otherwise.
- System Admin configuration is separate from Mayor analytics.
- Frontend route guards are UX only; the backend must authorize every protected API request.

## API integration
See [`docs/API_CONTRACT.md`](docs/API_CONTRACT.md). Every endpoint and payload is **TBD** until confirmed by the backend team. Do not infer routes, fields, role permissions, attachment limits, or status transitions from UI mockups.

## Known limitations
- Authentication is a frontend demonstration, not secure backend authentication.
- Complaint rows, chart values, categories and zones are sample/demo data.
- API integration, real uploads, token lookup, real notification delivery and role enforcement require backend contracts.
- No production security is provided by client-side route checks.
