# Renovations & Contracting Business Website

A premium, highly responsive, and high-conversion multi-page static website designed for a professional residential remodeling and contracting business. 

This project features a clean Navy Blue and Gold color palette, modern typography, fluid CSS micro-animations, and interactive components. It is optimized for fast loading (lazy loading for off-screen assets) and fully compliant with modern accessibility (A11y) and SEO best practices.

---

## 📂 Project Structure & Architecture

The website is divided into a clean multi-page structure:

*   **`index.html` (Master Entry & Hub)**: Serves as the landing controller. Contains a high-impact Hero LCP optimized header, a viewport-observer trust stats counter, a brief overview narrative, a 3-service specialty preview section, and direct call-to-actions.
*   **`services.html` (Renovation Divisions)**: Displays all 5 primary contracting divisions (Whole-Home, Kitchen, Bathrooms, General Contracting, Decks & Porches) using an interactive grid. Features detail modal popups driven by modular JavaScript data mapping.
*   **`about.html` (Our Story & Values)**: Houses the company history, founder profile widget, and an interactive, auto-rotating benefit slider carousel (resetting dynamically on manual tab selection to prevent layout jumps).
*   **`contact.html` (Lead Generation & Location)**: Features local contact information, state registration licenses checklist (MD/VA/DC), a visual area map placeholder, and a customized lead capture form containing validation checks, field indicators, a loading spinner, and success message overlays.
*   **`walkthrough.md`**: Detailed architectural guide highlighting the developer-facing structures and verification checklist.
*   **`task.md`**: Living checklist showing completed features during the refactoring process.

---

## 🛠️ Tech Stack & Assets

*   **Core Structure**: HTML5 with semantic tags (`<header>`, `<main>`, `<section>`, `<footer>`).
*   **Styling & Design System**: Tailwind CSS v3 via Play CDN, extended with custom configuration classes for premium theme colors, fonts, and shadows.
*   **Typography**: 
    *   *Plus Jakarta Sans* (Bold, geometric font for high-impact uppercase headings).
    *   *Inter* (Clean, highly legible sans-serif for body descriptions).
*   **Icons**: FontAwesome v6.4.0 (embedded via CDN).
*   **Animations**: Custom keyframe animations (`pulse-gold-ring` for WhatsApp and `animate-float` for elements).

---

## 🌟 Interactive Components & Features

1.  **Dynamic Sticky Header**: Modifies its style, backdrop blur filters, and shadows dynamically as the user scrolls, transitioning from transparent to a solid premium card layout. Includes a mobile slide drawer overlay for small screens.
2.  **Viewport-Observer Counters**: Stats numbers count up dynamically from `0` to target statistics (e.g., `17+` years, `500+` remodels) only when they scroll into the viewport.
3.  **Details Dialog Modals**: The services grid loads bullet points from a JavaScript array directly into a viewport-centered modal card with Escape-key close handlers and overlay click triggers.
4.  **Benefits Showcase Slider**: Integrates an automatic benefit tabs selection slider (rotating every 8 seconds) with a smart reset mechanism when a tab is clicked manually.
5.  **Validated Client-Side Lead Form**: Validates inputs (name, address, email structure, telephone patterns) prior to submission. Highlights missing/incorrect inputs with a red border and helper error labels, shows a mock loading spinner (`1.8s`), resets the fields, and pops up a success message.
6.  **Floating WhatsApp Trigger**: Injected on all pages to ensure instant communication access, featuring a pre-filled client chat message: *"Hi! I'm interested in a free remodeling estimate."*

---

## 📝 Placeholders Customization Guide

To configure the website for a live business, search the project files (`index.html`, `services.html`, `about.html`, `contact.html`) for the following brackets and replace them with actual company details:

| Placeholder Bracket | Description | Example Replacement |
| :--- | :--- | :--- |
| `[Company Name]` | Name of the remodeling business | `Apex Remodeling LLC` |
| `[Location, State]` | Primary service city/state | `Frederick, MD` |
| `[Phone Number]` | Telephone contact link | `(301) 555-0199` |
| `[Email Address]` | Email contact link | `contact@yourdomain.com` |
| `[Street Address, City, State, ZIP]` | Physical office mailing address | `123 Main St, Frederick, MD 21701` |
| `[Founder Name]` | Owner profile widget | `John Doe` |
| `[MHIC Number]` / `[VA Number]` | Regulatory state licenses | `MHIC #123456` |
| `[WhatsApp Number]` | Floating API link | `13015550199` (Only digits, no dashes or signs) |
| `[Location 1]` to `[Location 6]` | List of local municipalities served | `Baltimore`, `Rockville`, `Bethesda` |

---

## 🚀 Deployment & Local Testing

### Local Server Setup (XAMPP / WampServer)
1.  Place the project directory inside the document root folder (e.g., `C:\xampp\htdocs\renovations-website`).
2.  Open your browser and navigate to:
    ```text
    http://localhost/renovations-website/index.html
    ```
3.  Click navigation items to verify that all relative links transition properly.

### Static Hosting (GitHub Pages / Netlify)
Since all paths and menu links are written with relative notation (`./index.html`, `./services.html`), you can push this directory to a GitHub repository and enable **GitHub Pages** instantly in settings without modifying any assets.

---

## ♿ Accessibility (A11y) & SEO Standards

*   **A11y Actions**: All interactive links, close triggers, hamburger selectors, and form elements contain descriptive `aria-label` tags, `aria-required`, `aria-live`, and keyboard accessibility wrappers.
*   **Focus Ring Highlight**: Inputs and select boxes feature a high-contrast focus ring (`focus:ring-2 focus:ring-brand-accent`) to support keyboard-only tab navigation.
*   **SEO Optimization**: Unified `<header>` navigation and `<footer>` maps. Each page maintains a unique `<title>` and `<meta name="description">` to improve click-through-rates in Google search engine rankings.
