# Codebase Map & File Registry

## 0. Last Synchronized Checkpoint

- **Last AI Analysis Timestamp**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Visual Codebase Overview

_Draw the entire project directory tree and explain each folder and file in one simple sentence. This is your bird's-eye view of the project._

### Directory Tree

```
project-name/
├── src/                          _Main application code_
│   ├── components/               _Reusable UI building blocks_
│   ├── pages/                    _Route definitions for each page_
│   ├── utils/                    _Helper functions used across the app_
│   └── index.js                  _Application entry point (where it all starts)_
├── server/                       _Backend logic and APIs_
│   ├── controllers/              _Handles what happens for each request_
│   ├── routes/                   _URL paths mapped to controllers_
│   └── config/                   _Server settings and database connection_
├── database/                     _Data layer_
│   ├── models/                   _What the data looks like (schemas)_
│   └── migrations/               _History of data structure changes_
├── public/                       _Static files served directly_
│   ├── images/                   _Pictures and icons_
│   └── favicon.ico               _Browser tab icon_
├── tests/                        _Automated tests_
│   ├── unit/                     _Tests for individual functions_
│   └── e2e/                      _Tests for full user workflows_
├── package.json                  _Project name, dependencies, and scripts_
├── .env                          _Secret keys and environment settings_
└── README.md                     _Project description and documentation_
```

> **Note:** This is a sample tree. Delete or modify these entries to match your actual project structure when running `-codebase`.

### Folder & File Descriptions

| Path | What It Does |
|------|-------------|
| `src/` | _Main application code — where most of your feature logic lives_ |
| `src/components/` | _Reusable UI building blocks — buttons, cards, modals, etc._ |
| `src/pages/` | _Route definitions — each file represents a different page/screen_ |
| `src/utils/` | _Helper functions — small tools used across multiple files_ |
| `src/index.js` | _Application entry point — where the app first starts running_ |
| `server/` | _Backend logic — handles requests from the frontend_ |
| `server/controllers/` | _Request handlers — decides what to do when someone hits a URL_ |
| `server/routes/` | _URL paths — maps each URL to its controller_ |
| `server/config/` | _Server settings — database connections, port numbers, etc._ |
| `database/` | _Data layer — where your data lives and how it's shaped_ |
| `database/models/` | _Data schemas — defines what fields each record has_ |
| `database/migrations/` | _Data version history — tracks changes to your database structure_ |
| `public/` | _Static files — served directly to the browser without processing_ |
| `tests/` | _Automated tests — code that checks if your app works correctly_ |
| `tests/unit/` | _Unit tests — tests each function in isolation_ |
| `tests/e2e/` | _End-to-end tests — simulates real user behavior from start to finish_ |
| `package.json` | _Project metadata — name, dependencies list, and runnable scripts_ |
| `.env` | _Secret configuration — API keys and settings (never commit this file!)_ |
| `README.md` | _Documentation — describes what the project does and how to use it_ |

---

## 2. Frontend Layer

### 1A. Logic, Functions & Code Structures

_Detailed documentation of every frontend logic, function, and code structure used in this project._

#### [FN-FE-001] Function/Logic Name

- **Purpose**: _What does this logic/function do?_
- **Location**: _File path where defined_
- **Input/Output**: _Parameters and return values_
- **Dependencies**: _What other functions/files does it rely on?_
- **Called By**: _Which components or functions invoke this?_
- **Side Effects**: _Any state mutations, API calls, or storage operations_

---

### 1B. File Registry & Connection Mapping

_Every frontend file and how it connects to the logics/functions documented in 1A above._

#### [FILE-FE-001] File Name

- **Path**: _Full relative path from project root_
- **Purpose**: _What does this file do?_
- **Functions Contained**: _References to FN-FE-XXX entries above_
- **Imports From**: _Other files it depends on_
- **Exports To**: _Files/components that import from this_
- **UI Role**: _What component, page, or feature does this file serve?_

---

## 3. Backend Layer

### 2A. Logic, Functions & Code Structures

_Detailed documentation of every backend logic, function, and code structure used in this project._

#### [FN-BE-001] Function/Logic Name

- **Purpose**: _What does this logic/function do?_
- **Location**: _File path where defined_
- **Input/Output**: _Parameters and return values_
- **Dependencies**: _What other functions/files does it rely on?_
- **Called By**: _Which endpoints, jobs, or processes invoke this?_
- **Side Effects**: _Any database mutations, cache operations, or external API calls_

---

### 2B. File Registry & Connection Mapping

_Every backend file and how it connects to the logics/functions documented in 2A above._

#### [FILE-BE-001] File Name

- **Path**: _Full relative path from project root_
- **Purpose**: _What does this file do?_
- **Functions Contained**: _References to FN-BE-XXX entries above_
- **Imports From**: _Other files it depends on_
- **Exports To**: _Files/services that import from this_
- **API Role**: _What endpoint, job, or service does this file serve?_

---

## 4. Data & Platform Layer

### 3A. Database Schema & Data Models

_Documents every database, table/collection, schema design, entity relationships, and ORM/ODM mappings used in this project._

#### [DB-001] Table/Collection Name

- **Database Type**: _[PostgreSQL, MongoDB, SQLite, etc.]_
- **Purpose**: _What this stores and why_
- **Schema Fields**: _Column/field name, type, constraints, defaults_
- **Relationships**: _Foreign keys, references to other tables or collections_
- **Indexes**: _Performance indexes defined_
- **ORM Model**: _File path of the model or schema definition_
- **Used By**: _Which backend functions query this (references to FN-BE-XXX)_

---

### 3B. Storage & File Management

_Documents file storage, asset pipelines, CDN, and cache layers._

#### [STG-001] Storage Service Name

- **Service/Provider**: _[Local disk, AWS S3, Cloudinary, Vercel Blob, etc.]_
- **Purpose**: _What kind of files are stored here_
- **Access Pattern**: _How files are uploaded, retrieved, and served_
- **Security**: _Public vs. private, signed URLs, access control_
- **Integration File**: _File path handling storage operations and configuration_

---

### 3C. Third-Party Services & Integrations

_Documents every external API, auth provider, payment gateway, webhook, and SaaS integration._

#### [SVC-001] Service Name

- **Provider**: _[Auth0, Stripe, Resend, OpenAI, etc.]_
- **Purpose**: _What this service does for the application_
- **Integration File**: _File path where this is configured or called_
- **Auth Method**: _API key, OAuth, JWT, webhook secret_
- **Environment Variables Needed**: _Keys and secrets (list names only, never actual values)_
- **Cost/Rate Limits**: _Any usage constraints or pricing model_

---

### 3D. Hosting & Deployment Environment

_Documents cloud platforms, domains, deployment pipelines, and environment configuration._

#### [DEP-001] Environment / Platform

- **Provider**: _[Vercel, Railway, AWS EC2, Netlify, etc.]_
- **Purpose**: _What runs here (frontend, backend, database, etc.)_
- **Domain**: _Custom domain or subdomain_
- **Deploy Method**: _Git push, CI/CD, Docker, manual_
- **Environment Variables**: _Required env vars (names only, never actual values)_
- **Build Command**: _How the project is built for this platform_
- **Health Check**: _URL or command to verify it is running_

---

### 3E. DevOps & Infrastructure Tooling

_Documents Docker, CI/CD pipelines, monitoring, logging, and orchestration._

#### [OPS-001] Tool / Config Name

- **Tool**: _[Docker, GitHub Actions, Nginx, Sentry, etc.]_
- **Purpose**: _What it automates or monitors_
- **Config File**: _Path to the configuration file_
- **Key Commands**: _Common CLI commands for this tool_

---

## 5. Learning Notes & Dependency Mapping

- **Critical Third-Party Libraries**: _[List packages used and a short sentence explaining why they are there to help you learn.]_
- **Tricky Code Paths**: _[Notes on complex loops, state mutations, or conditional rendering blocks that are hard to grasp at a glance.]_
<!-- c: worrie -->
