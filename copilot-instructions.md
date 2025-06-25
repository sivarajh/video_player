# GitHub Copilot Instructions for This React Project

## Project Tech Stack

- **React** (functional components, hooks preferred)
- **React DOM**
- **React Router** (v6+)
- **Salt Design System** for UI components

## General Guidelines

- Use **function components** and **React Hooks** (`useState`, `useEffect`, etc.). Do not use class components.
- Favor **ES6+ syntax** (arrow functions, destructuring, etc.).
- Use **TypeScript** if the project uses it, otherwise use JavaScript.
- All UI components should use the **Salt Design System** components where possible, instead of raw HTML or MUI.
- For navigation, use **React Router v6+** (`useNavigate`, `useParams`, `<Routes>`, `<Route>` components).
- Keep code modular: separate logic into small, reusable functions and components.

## Design System

- Prefer Salt Design System components for all UI elements (e.g., buttons, inputs, dialogs).
- Use consistent theming and spacing as per Salt guidelines.
- Refer to the Salt Design System documentation for component usage and theming.

## Example Imports

```js
import { Button, TextField, Dialog } from '@salt-ds/core';
import { useNavigate, useParams } from 'react-router-dom';
```

## State & Data

- Use `useState`, `useReducer`, or custom hooks for managing state.
- For shared global state, use React Context or a state management solution if configured.
- Fetch data using hooks such as `useEffect` or custom data-fetching hooks.

## Routing

- Use `<Routes>` and `<Route>` for route definitions.
- Use `useNavigate` for navigation, not `window.location`.

## Code Style

- Follow the project's ESLint and Prettier settings.
- Use clear, descriptive variable/function/component names.
- Write JSDoc or TypeScript types for public functions/components.

## Testing

- Suggest tests using React Testing Library if tests are requested.

## Example Component

```jsx
import React from "react";
import { Button, TextField } from "@salt-ds/core";
import { useNavigate } from "react-router-dom";

export function ExampleLoginForm() {
  const navigate = useNavigate();
  const [username, setUsername] = React.useState("");

  return (
    <form
      onSubmit={e => {
        e.preventDefault();
        // handle login
        navigate("/dashboard");
      }}
    >
      <TextField
        label="Username"
        value={username}
        onChange={e => setUsername(e.target.value)}
      />
      <Button type="submit">Login</Button>
    </form>
  );
}
```

---

**Remember:** Always use Salt Design System components for UI, React Router for navigation, and functional React patterns.
