---

## ✅ GitHub Branching Best Practices for Developers

Whether you're working solo or in a team, following a consistent and clean workflow helps avoid conflicts, bugs, and messy history.

---

### 👩‍💻 1. **Never Push Directly to `main` or `develop`**

* Always create a **feature branch** for your work.
* All changes go through a **pull request (PR)** and **review**.
* CI/CD should be triggered via PR.

---

### 🌿 2. **Branch from the Right Place**

| Goal              | Branch From                             |
| ----------------- | --------------------------------------- |
| New feature       | `develop`                               |
| Bug fix (dev)     | `develop`                               |
| Hotfix (prod bug) | `main`                                  |
| Documentation     | `main` or `develop` depending on impact |

---

### 🏷️ 3. **Use Clear & Consistent Branch Names**

Follow the pattern:

```
<type>/<issue-id>-<short-description>
```

**Examples**:

```
feature/123-user-authentication  
bugfix/456-fix-login-error  
hotfix/789-crash-on-payment  
docs/update-api-readme  
chore/remove-unused-deps  
```

> 🔖 Tip: Include ticket/issue number if using Jira, Trello, GitHub Issues, etc.

---

### ⚙️ 4. **Create a Branch (Properly)**

Before starting work:

```bash
git checkout develop           # or 'main' for hotfix
git pull origin develop        # make sure you're up to date
git checkout -b feature/123-user-auth
```

---

### 🔀 5. **Open Pull Requests Early (but not too early)**

* Use PR titles like:
  `feat: add user authentication`
  `fix: resolve login redirect bug`

* Add a **clear description** (what changed, why, screenshots if UI)

* Tag reviewers (e.g., your team lead)

* Link the issue:
  `Closes #123`

---

### ✅ 6. **Pull Latest Before Pushing or Merging**

Keep your branch updated:

```bash
git pull origin develop --rebase
```

> 🔄 Rebasing keeps history clean — or use `merge` if your team prefers.

---

### 🧹 7. **Clean Up After Merge**

After your PR is merged:

```bash
git checkout develop
git pull origin develop
git branch -d feature/123-user-auth   # delete local
git push origin --delete feature/123-user-auth  # delete remote
```

> Keeps the repo clean and avoids branch clutter.

---

### 📋 8. **Stay Aligned with GitHub Flow / Git Flow**

| Team Workflow | What You Do                        |
| ------------- | ---------------------------------- |
| GitHub Flow   | Always branch off `main`           |
| Git Flow      | Branch off `develop`, merge via PR |

Check with your team which model is followed.

---

### 📦 9. **Use Semantic Commit Messages (Optional but Helpful)**

Use prefixes like:

* `feat:` – new feature
* `fix:` – bug fix
* `docs:` – documentation
* `refactor:` – code refactor
* `chore:` – non-code change (e.g. config)

**Example**:

```bash
git commit -m "feat: add forgot password screen"
```

---

### 🧪 10. **Test Before You Push**

* Run unit/integration tests locally.
* Lint your code.
* Don’t break the build 🙃

---

## 👇 Developer Branch Workflow (Visual)

```plaintext
develop
   │
   ├── feature/123-user-authentication
   │       ↓
   │     [Code]
   │       ↓
   ├── Pull Request → develop
   │       ↓
   └── Code Review + Merge → CI/CD
           ↓
       Delete branch ✅
```

---

## ✅ Summary for Developers

| Step               | Action                                |
| ------------------ | ------------------------------------- |
| 🔄 Stay updated    | `git pull` before starting work       |
| 🌿 Branch properly | `git checkout -b feature/...`         |
| 📥 PRs only        | Never push directly to `main/develop` |
| 🧪 Test + Lint     | Run all checks before committing      |
| 🧹 Clean up        | Delete branches after merge           |
| 🧠 Communicate     | Write meaningful PRs and commits      |

---
