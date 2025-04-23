# UnifiedBits Branching Guidelines

To ensure a clean, scalable, and team-friendly development workflow, UnifiedBits follows a consistent branching strategy using base and working branches.

---

## 🔀 Core Branches

### `main`
- 🔒 **Production-ready branch**
- Always contains the latest **stable release**
- Direct changes are restricted; merged only through pull requests (usually from `dev`)

### `dev` or `develop`
- 🚧 **Primary development branch**
- All new features and fixes are merged into `dev` first
- Acts as a staging area before pushing to production (`main`)
- Frequently rebased or updated from `main` to stay in sync

---

## 🧪 Feature & Support Branches

| Branch Type      | Purpose | Example |
|------------------|---------|---------|
| `feature/`       | For adding new features | `feature/api-user-dashboard` |
| `fix/`           | For bug fixes | `fix/ui-navbar-overlap` |
| `refactor/`      | For internal refactoring (no behavior change) | `refactor/core-cleanup` |
| `docs/`          | For documentation updates | `docs/readme-api-guide` |
| `test/`          | For adding or modifying tests | `test/auth-unit-tests` |
| `chore/`         | For setup/config/CI/CD work | `chore/ci-add-lint-check` |
| `hotfix/` (optional) | For urgent fixes to production (`main`) | `hotfix/api-token-expiry` |

---

## 🌱 Branch Naming Convention

Always follow this structure when naming your branches:

```
<branch-type>/<domain>-<short-description>
```

> Use lowercase letters and hyphens for readability.

### ✅ Examples

```
feature/auth-add-otp-login
fix/ui-fix-navbar-overlap
refactor/api-cleanup-old-endpoints
docs/readme-update-api-usage
test/dashboard-add-user-metrics-tests
```

---

## 🧩 Common Domains

| Domain     | Description |
|------------|-------------|
| `auth`     | Authentication logic |
| `ui`       | User interface |
| `api`      | Backend endpoints |
| `dashboard`| Analytics & reporting |
| `core`     | Business logic |
| `readme`   | Project documentation |
| `ci`       | Continuous Integration/Deployment |
| `infra`    | Infrastructure & DevOps |

---

## ⚙️ Workflow Overview

🛑 **Always create your branch from the latest `dev` branch to ensure you're working with the most recent code.**

1. **Checkout and pull the latest `dev`:**
   ```bash
   git checkout dev
   git pull origin dev
   ```

2. **Create your new branch from `dev`:**
   ```bash
   git checkout -b feature/ui-add-sidebar
   ```

3. **Work on your feature/fix and commit using [Conventional Commits](https://github.com/UnifiedBits/unifiedbits-commit-guidelines):**
   ```bash
   feat(ui): add collapsible sidebar component
   ```

4. **Push your branch:**
   ```bash
   git push origin feature/ui-add-sidebar
   ```

5. **Open a Pull Request to `dev` for review.**

6. ✅ Once reviewed and tested, maintainers will merge `dev` into `main` when ready for production.

---

## 🧼 Maintenance Tips

- Sync `dev` regularly with `main`
- Delete local and remote feature branches after merge
- Never commit directly to `main` or `dev` unless it's critical (via `hotfix/`)

---

## 🧠 Summary

| Branch     | Purpose                       |
|------------|-------------------------------|
| `main`     | Stable production-ready code  |
| `dev`      | Integration of features & fixes |
| `feature/` | New enhancements & modules     |
| `fix/`     | Bug fixes                      |
| `hotfix/`  | Emergency production fixes     |
| `docs/`    | Documentation-only changes     |
| `test/`    | Testing logic                  |
| `chore/`   | Meta tasks & setup             |

---

## 📚 Resources

- 🔗 [UnifiedBits Commit Guidelines](https://github.com/unifiedbits/commit-guidelines).
- 📘 [GitHub Flow vs Git Flow](https://guides.github.com/introduction/flow/)

---

> “Organized branches mean faster development and cleaner launches.” — UnifiedBits

Let’s branch smartly and build boldly! 🚀
