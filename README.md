Demo: Dark / Light theme toggle (React)

This component uses `useState` to track the current theme (`isDark`). On mount, a `useEffect` with an empty dependency array runs once and:

- Reads the saved theme from `localStorage` (defaults to "light").
- Updates the `isDark` state accordingly.
- Sets the `data-theme` attribute on the document element so CSS variables switch.

The toggle handler flips `isDark`, writes the new theme into `localStorage`, and updates `data-theme` so the page immediately reflects the chosen theme.

This README clarifies initialization and the roles of `useState`, `useEffect`, and the toggle handler.

Toggle function

The `toggle` function performs these steps when the user clicks the button:

- Compute the new theme: `const newTheme = isDark ? 'light' : 'dark'`.
- Update React state: `setIsDark(!isDark)` so the component reflects the new value.
- Persist the choice: `localStorage.setItem('theme', newTheme)` so the preference survives reloads.
- Apply immediately: `document.documentElement.setAttribute('data-theme', newTheme)` so CSS variables switch and the UI updates at once.

The toggle button in the app calls this `toggle` function on click and displays `Toggle Theme`.
