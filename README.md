## 1. **Your Project’s Key Files and What They Do**

### a) **`package.json`**

- **What:** This is your project manifest.  
- **Why important:** It lists your project dependencies (like React, Tailwind), scripts (like `npm run dev`), and metadata.  
- **You use it to:** Install packages, run scripts (start dev server, build).

---

### b) **`vite.config.js` or `vite.config.ts`**

- **What:** Configuration for the Vite build tool.  
- **Why important:** Sets up how your app is built and served during development.  
- **You use it to:** Customize build options, proxy backend requests, add plugins.

---

### c) **`src/` folder**

- This is where your app code lives — most important folder for you.

Inside `src/`:

- **`main.jsx` or `main.tsx`**  
    - Entry point of your React app.  
    - Loads the root React component into the browser DOM.

- **`App.jsx` or `App.tsx`**  
    - The root React component, often contains routes or main layout.  
    - You usually build the app UI from here.

- **Components folder (e.g., `src/components/`)**  
    - Contains reusable UI components (e.g., your MovieCard, buttons).  
    - Keeps code modular and maintainable.

- **`index.css` or `index.css`**  
    - Global CSS styles and Tailwind directives (like `@tailwind base;` etc).

---

### d) **`postcss.config.js` & `tailwind.config.js`**

- **`postcss.config.js`** configures PostCSS plugins (Tailwind, autoprefixer).  
- **`tailwind.config.js`** controls your Tailwind setup (custom colors, screens, etc).

---

## 2. **How Frontend Talks to Backend**

- Your React frontend runs in the browser.  
- Your backend (maybe Node.js, Python, or any API) runs on a server or localhost.  
- They communicate via **HTTP requests** (usually REST API calls or GraphQL).

### Typical flow:

1. Frontend calls backend APIs using `fetch()` or libraries like `axios`.  
2. Backend processes the request (e.g., fetch movie data from DB or third-party API).  
3. Backend sends JSON data back.  
4. Frontend receives the JSON response, updates UI with the data.

---

## 3. **Example: Fetching Movies From Backend**

- You might have a backend endpoint: `GET /api/movies`  
- Your React component uses:

    ```jsx
    useEffect(() => {
      fetch('http://localhost:4000/api/movies')
        .then(res => res.json())
        .then(data => setMovies(data))
    }, [])
    ```

- This gets movie data and sets it in component state to display.

---

## 4. **Where To Start**

- Focus on files inside `src/`:  
    - Build components in `src/components/`.  
    - Manage routes and app state in `src/App.jsx`.  
    - Style globally in `src/index.css`.  
- Use `package.json` and your terminal to add dependencies and run the dev server.  
- Later, set up backend API and connect it with frontend fetch calls.

---

## Summary Cheat Sheet

| File/Folder          | Purpose                          | What you do with it              |
|---------------------|---------------------------------|---------------------------------|
| `package.json`       | Manages dependencies and scripts| Install packages, run dev/build scripts |
| `vite.config.js`     | Vite build and dev server config| Proxy backend, add plugins       |
| `src/main.jsx`       | React app entry point            | Usually no change, just bootstraps app |
| `src/App.jsx`        | Main React component             | Add routes, main layout          |
| `src/components/`    | UI components (MovieCard, buttons, etc) | Build reusable pieces           |
| `src/index.css`      | Global CSS + Tailwind setup      | Customize styles                |
| `postcss.config.js`  | PostCSS plugins config           | Mostly Tailwind + autoprefixer  |
| `tailwind.config.js` | Tailwind customizations          | Add colors, screens, variants   |

---
