# 🌐 RitelKit Ecosystem: Platform Orchestration & Ecosystem Guide

Welcome to the **RitelKit Ecosystem**. This document serves as the high-level orchestration guide for the platform.

> [!IMPORTANT]
> **Internal Policy**: This project is a hybrid repository. While certain technical components are open to community contribution, the integration logic, business workflows, and orchestration strategies described here are **PROPRIETARY** and intended for internal team replication and consistency.

## 🏗️ Architecture Overview

The ecosystem consists of two main components (managed as Git Submodules):

1.  **RitelKit (Central Platform)**: `ritelkit/`
    *   Dashboard for global management.
    *   Technical details: [DEVELOPMENT_REF.md](./ritelkit/DEVELOPMENT_REF.md)
2.  **RitelKit App (Tenant Instance)**: `ritelkit-app/`
    *   Operational app for tenants.
    *   Technical details: [DEVELOPMENT_REF.md](./ritelkit-app/DEVELOPMENT_REF.md)

---

## 🔒 Multi-Tenancy Design (The Gold Standard)

The core value of RitelKit is its robust multi-tenancy.
*   **Isolation**: Every action MUST be filtered by `tenantId`.
*   **Security**: Unauthorized access to data outside the detected tenant context is a critical failure. Refer to sub-project `DEVELOPMENT_REF.md` for specific implementation patterns.

---

## 🛡️ Internal & Private Policy

1.  **Intellectual Property**: The orchestration logic in `ritelkit-dev` belongs to SandiKodev.
2.  **Data Handling**: Do NOT commit production `.env` files. Use `.env.production` placeholders only for known safe variables (like Turso URLs) while keeping secrets in secure KV/Environment variables.
3.  **Branching**: Feature branches should be created in the respective submodules. The `ritelkit-dev` repo only tracks the stable state of these submodules on its `main` branch.

## 🌐 Summary of Responsibilities

*   **ritelkit-dev**: Infrastructure, Submodule management, Shared Deployment strategies.
*   **ritelkit**: Tenant administrative interface, Global Configs, Audit Pipelines.
*   **ritelkit-app**: Storefronts, POS, Inventory Management, Tenant-specific logic.

---

### 🆘 Troubleshooting (Ecosystem Level)
*   **Submodule Out of Sync?**: Run `git submodule update --remote` to pull latest changes from all projects.
*   **Domain Resolution?**: Ensure your local `/etc/hosts` matches the entries in [Local Development Setup](#🛠️-local-development-setup).
*   **Database Sync?**: Changes to shared schemas in `ritelkit-app` may require updates to how `ritelkit` (dashboard) views that same data.
