# Tinder4Movies

## What is Tinder4Movies?

Tinder4Movies helps you and your friends find the perfect movie to watch together by letting everyone swipe on their own devices. Here’s how it works:

- Everyone swipes on movies individually in a shared group session.
- The app finds movies that the whole group likes.
- No more arguing over what to watch — just pick from movies you all want to see.
- Makes planning movie nights with friends simple and fun!

<br>


## ✅ Summary of the Technology Stack

| Layer    | Technology                              |
|----------|---------------------------------------|
| Frontend | HTML + Tailwind CSS + TypeScript + React |
| Backend  | Python + FastAPI + WebSockets          |
| Database | SQLite (PostgreSQL-ready structure)    |
| API      | TMDB API                              |
| IDE      | VSCode                               |

---
<br>
<br>

## Most important Files:

### 1. **Key Files and Their Purpose**

#### a) **`package.json`**

- Defines project dependencies (like React, Tailwind), scripts (such as `npm run dev`), and metadata.  
- Used to install packages and run development/build scripts.

<br>

#### b) **`vite.config.js` or `vite.config.ts`**

- Configuration file for the Vite build tool.  
- Sets up how the app is built and served during development.  
- Can customize build options, proxy backend requests, and add plugins.

<br>

#### c) **`src/` folder**

- Contains the main application code.

Inside `src/`:

- **`main.jsx` or `main.tsx`**  
    - Entry point of the React application.  
    - Loads the root React component into the browser DOM.

- **`App.jsx` or `App.tsx`**  
    - Root React component, often includes routes or main layout.  
    - The main UI is built from here.

- **Components folder (e.g., `src/components/`)**  
    - Contains reusable UI components such as MovieCard or buttons.  
    - Helps keep code modular and maintainable.

- **`index.css`**  
    - Global CSS styles and Tailwind directives (like `@tailwind base;`).

<br>

#### d) **`postcss.config.js` & `tailwind.config.js`**

- `postcss.config.js` configures PostCSS plugins including Tailwind and autoprefixer.  
- `tailwind.config.js` controls Tailwind CSS setup, such as custom colors and screen sizes.

---


### 2. **Frontend-Backend Communication**

- The React frontend runs in the browser.  
- The backend (Node.js, Python, or other API) runs on a server or localhost.  
- Communication happens via **HTTP requests** (usually REST API calls or GraphQL).

#### Typical flow:

1. Frontend calls backend APIs using `fetch()` or libraries like `axios`.  
2. Backend processes the request (e.g., fetching movie data from a database or third-party API).  
3. Backend sends JSON data as a response.  
4. Frontend receives the JSON and updates the UI accordingly.

---


### 3. **Example: Fetching Movies from Backend**

- A backend endpoint might be: `GET /api/movies`.  
- The React component example:

    ```jsx
    useEffect(() => {
      fetch('http://localhost:4000/api/movies')
        .then(res => res.json())
        .then(data => setMovies(data))
    }, [])
    ```

- This fetches movie data and stores it in component state for display.

---


### 4. **Getting Started**

- Focus on files inside the `src/` folder:  
    - Components in `src/components/`.  
    - Routes and app state managed in `src/App.jsx`.  
    - Global styles in `src/index.css`.  
- Use `package.json` and the terminal to install dependencies and run the development server.  
- Later, set up backend API endpoints and connect them with frontend fetch calls.

---
<br>

### **Summary Cheat Sheet**

| File/Folder          | Purpose                          | Typical Usage                      |
|----------------------|---------------------------------|----------------------------------|
| `package.json`       | Manages dependencies and scripts| Installing packages, running scripts |
| `vite.config.js`     | Vite build and dev server config| Proxying backend, adding plugins  |
| `src/main.jsx`       | React app entry point            | Bootstraps the React application  |
| `src/App.jsx`        | Main React component             | Defines routes and main layout    |
| `src/components/`    | UI components (MovieCard, buttons, etc) | Building reusable UI parts     |
| `src/index.css`      | Global CSS and Tailwind setup   | Styling and Tailwind configuration|
| `postcss.config.js`  | PostCSS plugin configuration    | Mainly Tailwind and autoprefixer  |
| `tailwind.config.js` | Tailwind CSS customization      | Custom colors, screens, variants  |

---
