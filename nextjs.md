---

## ✅ Folder & File Naming in a Next.js Project

### 🔧 **Folder Naming (Use `lowercase-with-hyphens`)**

This is ideal for:

* `/components`
* `/pages`
* `/lib`
* `/utils`
* Any custom folders you create (e.g., `user-profile`, `admin-dashboard`)

**✅ Examples**:

```
/components
/components/user-card
/pages
/pages/user-profile
/lib/api-client
/utils/format-date
```

---

### 📄 **File Naming (Use `lowercase-hyphenated` OR `camelCase` depending on usage)**

#### ✅ UI Components (PascalCase for React Components)

React components should use **PascalCase**:

```
/components/UserCard.js
/components/Navbar.jsx
/pages/AboutUs.jsx
```

> 📌 **Why?** React treats capitalized filenames as components.

---

#### ✅ Utility, Config, or Static Files

Use **kebab-case** or **camelCase** — either is fine, but be consistent:

```
/utils/format-date.js
/lib/api-client.js
/config/site-settings.js
/public/favicon.ico
```

---

### 🛣️ **Routes and Pages (`/pages` Folder)**

Next.js uses the **file structure inside `/pages`** to define routes.

* Use **kebab-case** for filenames that become routes
* Avoid uppercase in URLs

**✅ Examples**:

```
/pages/index.js          →  /
/pages/about-us.js       →  /about-us
/pages/user-profile.js   →  /user-profile
/pages/blog/[slug].js    →  /blog/my-article-title
```

> ⚠️ Use square brackets `[param]` for dynamic routes (Next.js convention).

---

### 📚 Suggested Folder Structure for a Next.js Project

```
my-nextjs-app/
│
├── public/                 # Static assets
├── pages/                  # Page routes
│   ├── index.js
│   ├── about-us.js
│   └── blog/
│       └── [slug].js
│
├── components/             # Reusable UI components
│   └── Header.jsx
│   └── BlogCard.jsx
│
├── lib/                    # API clients, data fetching, helpers
│   └── api-client.js
│
├── utils/                  # Utility functions
│   └── format-date.js
│
├── styles/                 # CSS/SCSS modules or global styles
│   └── globals.css
│
├── config/                 # Configuration files
│   └── site-settings.js
│
├── .gitignore
├── README.md
└── next.config.js
```

---

### 📝 Summary

| Element        | Naming Style                      | Example                          |
| -------------- | --------------------------------- | -------------------------------- |
| Folders        | `lowercase-hyphens`               | `user-profile`                   |
| Pages (routes) | `lowercase-hyphens.js`            | `/about-us.js`                   |
| Components     | `PascalCase.jsx`                  | `UserCard.jsx`                   |
| Utils / Config | `camelCase.js` or `kebab-case.js` | `apiClient.js`, `format-date.js` |

---
