# Project Walkthrough - Multi-Page Renovations Website

This document provides a summary of the completed renovations website, detailing the multi-page structure, styling conventions, interactive features, refactored best practices, and verification steps.

---

## 📂 Project Architecture

The website is structured as a static multi-page site composed of four specialized pages located in the workspace folder `C:\xampp\htdocs\renovations-website\`:

1. **index.html (Home/Hub)**: Serves as the master entry point and controller. It features the primary Hero section, trust statistic counts, a welcome overview, a 3-service teaser grid (linking to the full grid), and a high-impact call-to-action.
2. **services.html (Services Grid)**: Displays all 5 renovation specialties (Whole-Home, Kitchen, Bathroom, General Contracting, Decks/Porches) in an interactive card grid. Clicking any specialty opens a descriptive modal loaded with code-compliant specifications.
3. **about.html (Our Story & Benefits)**: Contains the company story, founder biography card, trust counters, and a dynamic, auto-sliding benefit tabs system (Craftsmanship, Communication, Custom Solutions, Local Experience, Full-Service).
4. **contact.html (Lead Capture & Map)**: Integrates office details, operational hours, state license credentials (MHIC, VA, DC), a visual area map mockup, and a lead capture form with custom validation, loading spinner, and success message overlay.

---

## 🌟 Visual Styling & Typography

Each page imports the Tailwind CSS v3 Play CDN with a unified config extension and shares the same design system:
- **Color Palette**:
  - **Backgrounds**: Slate-tinted off-white (`bg-brand-cream` / `#f8fafc`) and clean white panels.
  - **Primary Base**: Deep slate navy (`bg-brand-navy` / `#0b1329`) for typography, structural headers, and footer backgrounds.
  - **Accent Hilite**: Gold/Amber (`bg-brand-accent` / `#f59e0b` & `#d97706` hover states) for buttons, tags, counter values, active link states, and interactive states.
- **Typography**:
  - **Headings**: *Plus Jakarta Sans* with clean, bold uppercase tracking.
  - **Body Text**: *Inter* for maximum readability on small mobile devices.

---

## 🛠️ Global Features & Refactored Best Practices

### 1. Sticky Navigation Header
- Semantically structured with the `<header>` element.
- Starts transparent with a light blur and transition-scales to solid white with an elegant shadow when scrolled.
- Fully responsive: collapses into a mobile slide drawer overlay on smaller screens.
- **Top Utility Bar**: Houses the prominent **Licensed & Insured** badge, company hours, and a clickable telephone anchor.
- **Active States**: Hardcoded in each file to highlight the current page instantly using gold text and an underline border block.

### 2. Relative & Portable Links
- All navigation menu anchors, buttons, and logos use relative path links (e.g. `href="./services.html"`).
- This ensures the navigation functions properly in local preview (via `http://localhost/renovations-website/...`) and on static deployment platforms (e.g. GitHub Pages) without needing absolute system paths.

### 3. SEO & Semantic HTML
- Fully structured with semantic tags: `<header>`, `<main>`, `<section>`, and `<footer>` on every page.
- Unique `<title>` tags and `<meta name="description">` configurations are injected into each header.
- In `index.html`, the LCP Hero image uses `fetchpriority="high"` and does *not* use lazy loading. All lower-fold images across all pages utilize `loading="lazy"` to optimize page speed scores.

### 4. Accessibility (A11y)
- Specific `aria-label` descriptors are attached to hamburger menu buttons, navigation links, social icons, close buttons, and WhatsApp triggers.
- Clear `aria-required="true"` properties and validation status alerts keep the lead form screen screen-reader friendly.

### 5. Floating WhatsApp Element
- Embedded on all four pages, providing a uniform, floating entrance button that prompts a WhatsApp Web chat link pre-filled with: *"Hi! I'm interested in a free remodeling estimate."*
- Features a clean, pulse-gold-ring CSS animation and a mock notifications pill.

---

## 🧪 Interactive Page Features

### 1. Statistics Counters (`index.html` & `about.html`)
- An intersection observer monitors viewport visibility.
- Numbers count up dynamically from `0` to target values (e.g. `17` years, `500` remodels) over a `1.5s` transition as soon as they become visible.

### 2. Service Modal Popups (`services.html`)
- Instead of cluttering the grid, cards use inline click events (`openServiceModal(index)`) that map to a structured JavaScript array.
- Detail modals display a list of code-compliant specialties, complete with click-to-book links, smooth backdrop transitions, and Escape-key closure listeners.

### 3. Benefit Carousel / Tabs (`about.html`)
- A slide selector allows users to click through 5 benefit categories.
- Uses an auto-rotation transition timer (every 8 seconds). The timer resets automatically whenever the user manually selects a tab to prevent layout jumps.

### 4. Form Validation & Overlay (`contact.html`)
- The lead form checks inputs on submission:
  - Required empty values get a red border (`border-red-500`) and field-specific error text.
  - Validates email and telephone expressions.
- Intercepts the submit event to display a loading spinner overlay for `1.8s` (simulating network requests) before transitioning to a gold-accented success message.

---

## 📝 Customization Instructions

To configure placeholders for production, search the HTML files and replace the following tokens:

| Placeholder Tag | Description | Example Replacement |
| :--- | :--- | :--- |
| `[Company Name]` | Your business name | `Apex Remodeling LLC` |
| `[Location, State]` | Primary service city/state | `Frederick, MD` |
| `[Phone Number]` | Telephone contact link | `(301) 555-0199` |
| `[Email Address]` | Email contact link | `contact@yourdomain.com` |
| `[Street Address, City, State, ZIP]` | Office mailing address | `123 Main St, Frederick, MD 21701` |
| `[Founder Name]` | Owner profile widget | `John Doe` |
| `[MHIC Number]` / `[VA Number]` | Regulatory licenses | `MHIC #123456` |
| `[WhatsApp Number]` | Floating API link | `13015550199` (Use numbers only, no dashes) |

---

## 🌐 Verification & Testing Instructions

1. **Local Server View**:
   - Access the site locally at http://localhost/renovations-website/index.html.
2. **Responsiveness Test**:
   - Shrink the browser width to verify that the desktop menu switches to a hamburger icon, and check that the service grids collapse into single columns.
3. **Link Verification**:
   - Click through all navigation headers on every page to ensure relative linking maintains context.
4. **Interactive Validation**:
   - Test modal click opens and Esc-key closes on the services page.
   - Test tab changes on the about page benefits carousel.
   - Trigger validation alerts on the contact form by submitting empty fields, then submit valid data to confirm the success overlay.
