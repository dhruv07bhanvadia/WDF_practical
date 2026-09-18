# ITUE203: Web Development Frameworks
## Semester 3 - Faculty of Technology and Engineering
### Project: StudentHub Portal (Completed till Practical 5)

---

## 📌 Practical 1: Project Initiation, Requirement Analysis, Sitemap, Wireframe, and GitHub Setup

### 1. Problem Definition & Scope
**StudentHub** is a central digital campus web portal designed to streamline communication, course management, student profiles, and administrative tracking for university students, faculty members, and administrators.

#### User Roles & Permissions:
1. **Student**: Access course resources, view academic progress (grades), check announcements, and update profile details.
2. **Faculty**: Manage course syllabus and publish notices/announcements.
3. **Administrator**: Oversee platform user accounts and monitor system performance.

---

### 2. Official StudentHub Sitemap Architecture

```text
                                 [ ROOT: StudentHub Home ]
                                        index.html
                                             │
      ┌──────────────────┬───────────────────┼───────────────────┬──────────────────┐
      │                  │                   │                   │                  │
  [ About Us ]    [ Contact Us ]      [ User Auth Gate ]    [ Auth Gate ]     [ Student Portal ]
  about.html       contact.html          login.html         register.html     pages/dashboard.html
                                                                                    │
                                                                   ┌────────┬───────┼───────┬────────┐
                                                                   │        │       │       │        │
                                                              [Profile] [Courses] [Grades] [Announcements]

### 3. Project Folder Structure
StudentHub/
├── README.md                # Complete Practicals 1, 2, 3, 4, & 5 Documentation & Viva Answers
├── index.html               # Page 1: Home Page 
├── about.html               # Page 2: About Page 
├── contact.html             # Page 3: Contact & Support Page 
├── login.html               # Page 4: User Login Page 
├── register.html            # Page 5: Student Registration Page 
│
├── pages/
│   ├── dashboard.html       # Page 6: Student Dashboard Main Hub
│   ├── profile.html         # Page 7: Student Profile Management
│   ├── courses.html         # Page 8: Course Catalog & Enrollment
│   ├── grades.html          # Page 9: Academic Results & Grades
│   └── announcements.html   # Page 10: Campus Noticeboard & Alerts
│
├── css/
│   └── style.css            # Fully Responsive Master CSS 
└── js/
    └── main.js
```

### 4. Answers to Practical 1 Key Questions / Analysis

#### Q1: What is URL and parts of URL?
- **URL (Uniform Resource Locator)**: A web address specifying the location of a resource on a network.
- **Parts of a URL**: `https://www.studenthub.edu:443/courses/index.html?dept=cs#main-content`
  1. **Protocol / Scheme**: `https://` (Security rules).
  2. **Domain Name**: `studenthub.edu` (Registered hostname).
  3. **Port Number**: `:443` (Default HTTPS port).
  4. **Path**: `/courses/index.html` (File location).
  5. **Query Parameters**: `?dept=cs` (Extra request parameters).
  6. **Fragment / Anchor**: `#main-content` (Navigates directly to element ID).

#### Q2: How is an HTML file processed in a web browser?
1. **HTML Parsing**: HTML bytes are parsed to tokens and nodes to form the **DOM Tree**.
2. **CSS Parsing**: Stylesheets are parsed to create the **CSSOM Tree**.
3. **Render Tree**: DOM and CSSOM combine into a Render Tree.
4. **Layout (Reflow)**: Calculates exact positions and sizes on screen.
5. **Paint**: Draws visual pixels to screen display.

#### Q3: How will page navigation flow be managed among all HTML pages?
- Managed using standard relative hyperlinks inside `<nav role="navigation">` header menus, footer site links, and `<nav aria-label="Breadcrumb">` bars on subpages.

#### Q4: How will GitHub commits be maintained after each practical?
- Clean commit workflow after each practical:
  ```bash
  git add .
  git commit -m "Practical 5: Completed Registration Form Regex validation and Password Strength Meter"
  git push origin main
  ```

---

## ♿ Practical 2: Semantic HTML5 Pages with Accessibility-Ready Structure

### Implemented Accessibility & Semantic Rules:
- ✅ **Semantic HTML5 Tags**: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`, `<form>`, `<fieldset>`, `<legend>`, `<table>`.
- ✅ **Skip Links**: Accessible `<a href="#main-content" class="skip-link">Skip to main content</a>` on all HTML pages.
- ✅ **Intermediate Extension - Breadcrumbs**: Implemented `<nav aria-label="Breadcrumb" class="breadcrumb-wrapper">` on all subpages.
- ✅ **ARIA Landmarks**: `aria-current="page"`, `aria-expanded`, `aria-label`, `role="navigation"`, `role="main"`.
- ✅ **Form Field Labeling**: Explicit `<label for="...">` matching input `id="..."`.

---

### Answers to Practical 2 Key Questions / Analysis

#### Q1: Are semantic tags used properly?
- **Yes**. `<header>` for site banner and navbar, `<nav>` for menus/breadcrumbs, `<main>` for primary content, `<section>` for content groups, `<article>` for cards, `<aside>` for sidebar, and `<footer>` for footer.

#### Q2: Are form labels, headings, image alt text, and navigation links accessible?
- **Yes**. All inputs have explicit `<label>` tags. Heading hierarchy (`<h1>`-`<h3>`) is sequential, icons use `aria-hidden="true"`, and focus states feature high-contrast outlines.

#### Q3: Is the page structure consistent across all pages?
- **Yes**. All pages follow the exact same template structure and share `css/styles.css`.

---

## 📱 Practical 3: Responsive UI Design using CSS Grid, Flexbox, and Mobile-First Layout

### Problem Definition:
Design responsive layouts for Home, About, Registration, Dashboard, Courses, and Feedback pages using CSS Grid and Flexbox. Ensure mobile-first responsiveness across desktop, tablet, and mobile screens.

### Implementation Summary:
1. **Flexbox Architecture**: Used for primary header navigation, button groups, breadcrumbs, and card headers.
2. **CSS Grid Architecture**: Used for main content card grids (`.grid-3`, `.grid-2`, `.grid-4`) and footer link columns.
3. **Responsive Breakpoints**:
   - **Desktop (1200px+)**: 3 and 4-column cards grid layout with fixed sidebar.
   - **Tablet (@media max-width: 992px)**: 2-column cards grid layout.
   - **Mobile (@media max-width: 768px)**: 1-column single-column stack, collapsible mobile hamburger menu drawer, stacked sidebars.

---

### Answers to Practical 3 Key Questions / Analysis

#### Q1: How does the layout adapt for mobile, tablet, and desktop screens?
- Adaptations occur via CSS media queries (`@media (max-width: 992px)` and `@media (max-width: 768px)`). Multicolumn grid layouts automatically collapse to 2 columns on tablets and 1 column on mobile phones. The top navigation transforms into a mobile hamburger menu drawer.

#### Q2: Which layout technique is used and why?
- **CSS Grid** is used for 2D layout areas (card grids, multi-column dashboard stats, footer columns) because it manages both rows and columns.
- **CSS Flexbox** is used for 1D layout components (header nav link alignment, breadcrumbs, stat icons, button rows) because it handles vertical alignment and wrapping efficiently.

#### Q3: Are typography, spacing, colors, and contrast readable?
- **Yes**. Plus Jakarta Sans font is used with WCAG AA compliant high contrast dark text (`#0f172a`) on light background (`#f8fafc`). Interactive focus states (`:focus-visible`) feature a 3px indigo outline ring (`#4f46e5`).

#### Q4: Is the framework used consistently without unnecessary inline CSS?
- **Yes**. All layout, grid, typography, and responsive rules are centralized in `css/styles.css` using CSS custom properties (`:root` variables) without inline CSS clutter.

---

## ⚡ Practical 4: JavaScript DOM Manipulation, Event Handling, and UI Interactivity

### Problem Definition:
Add dynamic UI components such as collapsible FAQ accordion, modal popup, notification banner, mobile hamburger menu, and light/dark theme switcher using JavaScript.

### Implemented UI Components:
1. **Light / Dark Theme Switcher**: Toggle button in header. Changes `data-theme="dark"` attribute on `<html>` root and persists preference in `localStorage`.
2. **Collapsible FAQ Accordion**: Interactive click-to-expand Q&A section with toggle icons.
3. **Modal Popup Dialog**: Campus info modal with backdrop overlay, dismiss button, and keyboard `Escape` key support.
4. **Dismissible Notification Banner**: Announcement bar at top of page with close button (`X`).
5. **Mobile Hamburger Drawer**: Accessible mobile menu drawer with `aria-expanded` toggle.

---

### Answers to Practical 4 Key Questions / Analysis

#### Q1: How are DOM elements selected and modified?
- Selected using `document.getElementById()`, `document.querySelector()`, and `document.querySelectorAll()`. Modified using `element.textContent`, `element.classList.toggle()`, `element.setAttribute()`, and `element.removeAttribute()`.

#### Q2: Are event listeners attached correctly?
- **Yes**. Event listeners are attached using `addEventListener('click', callback)`, `addEventListener('input', callback)`, and `addEventListener('keydown', callback)` without inline JS clutter.

#### Q3: Is `localStorage` used for remembering theme choice?
- **Yes**. `localStorage.setItem('theme', 'dark')` saves preference and `localStorage.getItem('theme')` restores theme state automatically on page load.

#### Q4: Does interactivity improve usability without breaking accessibility?
- **Yes**. Modal popup supports `Escape` key closing, focus states are maintained, and ARIA attributes (`aria-expanded`, `aria-selected`, `aria-controls`) keep screen readers synced.

---

## 📝 Practical 5: Registration Form with Frontend Validation and User-Friendly Error Handling

### Problem Definition:
Create a student registration form with HTML5 input types and JavaScript validation for name, email, mobile number, password, confirm password, course, year, gender, and terms acceptance. Use Regular Expression for validations.

### Implemented Form & Validation Features:
1. **Form Fields**: Full Name, Email, Mobile Number (10 digits), Password, Confirm Password, Course Select, Year Select, Gender Radio Buttons, Terms Checkbox.
2. **Regular Expressions Used**:
   - **Name**: `/^[A-Za-z\s]{3,50}$/` (Letters and spaces only, min 3 chars).
   - **Email**: `/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/` (Standard email format).
   - **Mobile**: `/^[0-9]{10}$/` (Exactly 10 digits).
   - **Password**: `/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&#])[A-Za-z\d@$!%*?&#]{8,}$/` (Min 8 chars, 1 uppercase, 1 lowercase, 1 number, 1 special symbol).
3. **Password Strength Meter**: Dynamic color-coded bar (Red = Weak, Amber = Medium, Green = Strong) updating live on `input` events.
4. **User-Friendly Error Messages**: Inline `<span class="error-text">` messages displayed directly below each invalid input field.

---

### Answers to Practical 5 Key Questions / Analysis

#### Q1: Are correct input types and attributes used?
- **Yes**. `type="text"`, `type="email"`, `type="tel"`, `type="password"`, `type="radio"`, `type="checkbox"`, `required`, and `novalidate` (to allow custom JS UX error handling).

#### Q2: Are validation errors displayed near the relevant fields?
- **Yes**. Inline error message labels in red text are dynamically rendered directly below the specific field that failed validation.

#### Q3: Is password strength checked?
- **Yes**. Real-time scoring calculates character length, uppercase/lowercase presence, numbers, and special symbols, providing live visual feedback via `.strength-bar-fill`.

#### Q4: Is the form accessible using keyboard and screen-reader-friendly labels?
- **Yes**. All inputs have explicit `<label for="...">` tags matching `id="..."`, keyboard focus rings (`:focus-visible`), and clear instructions.
