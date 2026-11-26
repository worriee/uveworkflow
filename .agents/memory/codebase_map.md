# Codebase Map

## 0. Last Checkpoint

- **Last Sync**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Directory Tree

```
project-name/
├── src/                    _Main app code_
│   ├── components/         _UI building blocks_
│   ├── pages/              _Route definitions_
│   ├── utils/              _Helper functions_
│   └── index.js            _Entry point_
├── server/                 _Backend logic_
│   ├── controllers/        _Request handlers_
│   ├── routes/             _URL mappings_
│   └── config/             _Server settings_
├── database/               _Data layer_
│   ├── models/             _Schemas_
│   └── migrations/         _DB changes_
├── public/                 _Static files_
├── tests/                  _Automated tests_
│   ├── unit/               _Unit tests_
│   └── e2e/                _E2E tests_
├── package.json            _Dependencies & scripts_
├── .env                    _Secrets (never commit!)_
└── README.md               _Documentation_
```

> Modify to match your actual project structure.

### File Descriptions

| Path | Purpose |
|------|---------|
| `src/` | Main application code |
| `src/components/` | Reusable UI blocks |
| `src/pages/` | Page/route definitions |
| `src/utils/` | Shared helper functions |
| `src/index.js` | App entry point |
| `server/` | Backend logic |
| `server/controllers/` | Request handlers |
| `server/routes/` | URL → controller mappings |
| `server/config/` | DB connections, ports |
| `database/` | Data layer |
| `database/models/` | Data schemas |
| `database/migrations/` | DB structure changes |
| `public/` | Static browser files |
| `tests/` | Automated tests |
| `package.json` | Project metadata & scripts |
| `.env` | API keys & settings |

---

## 2. Frontend Layer

### [FN-FE-001] Function Name

- **Purpose**: _What it does_
- **Location**: _File path_
- **Input/Output**: _Params & returns_
- **Dependencies**: _Other functions/files_
- **Called By**: _Who invokes this_
- **Side Effects**: _State/API/storage ops_

### [FILE-FE-001] File Name

- **Path**: _Relative path_
- **Purpose**: _What file does_
- **Functions**: _Refs to FN-FE-XXX_
- **Imports From**: _Dependencies_
- **Exports To**: _Who imports this_
- **UI Role**: _Component/page served_

---

## 3. Backend Layer

### [FN-BE-001] Function Name

- **Purpose**: _What it does_
- **Location**: _File path_
- **Input/Output**: _Params & returns_
- **Dependencies**: _Other functions/files_
- **Called By**: _Endpoints/jobs invoking_
- **Side Effects**: _DB/cache/API ops_

### [FILE-BE-001] File Name

- **Path**: _Relative path_
- **Purpose**: _What file does_
- **Functions**: _Refs to FN-BE-XXX_
- **Imports From**: _Dependencies_
- **Exports To**: _Who imports this_
- **API Role**: _Endpoint/job served_

---

## 4. Data & Platform Layer

### [DB-001] Table/Collection

- **Type**: PostgreSQL | MongoDB | SQLite
- **Purpose**: _What this stores_
- **Fields**: _Columns/fields, types, constraints_
- **Relationships**: _FKs, references_
- **ORM Model**: _File path_
- **Used By**: _Refs to FN-BE-XXX_

### [STG-001] Storage Service

- **Provider**: S3 | Cloudinary | Local
- **Purpose**: _Files stored here_
- **Access**: _Upload/retrieve pattern_
- **Security**: _Public/private, signed URLs_

### [SVC-001] Third-Party Service

- **Provider**: Auth0 | Stripe | etc.
- **Purpose**: _What it does_
- **Integration File**: _Config path_
- **Auth**: API key | OAuth | JWT
- **Env Vars**: _Names only, no values_

### [DEP-001] Deployment Environment

- **Provider**: Vercel | Railway | AWS
- **Purpose**: _What runs here_
- **Domain**: _Custom domain_
- **Deploy**: Git push | CI/CD | Docker
- **Build**: _Build command_

### [OPS-001] DevOps Tool

- **Tool**: Docker | GitHub Actions | etc.
- **Purpose**: _What it automates_
- **Config File**: _Path_

---

## 5. Learning Notes

- **Key Libraries**: _Packages & why they're used_
- **Tricky Paths**: _Complex logic, state mutations_

<!-- c: worrie -->
