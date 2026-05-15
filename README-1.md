# Studex – Reusable Component Library

Task 2 submission. A reusable UI component library built with React for the Studex study productivity platform.

---

## Live Demo
🔗 [View Component Library](https://YOUR-USERNAME.github.io/studex-component-library/)

## GitHub Repository
🔗 [View Code](https://github.com/YOUR-USERNAME/studex-component-library)

---

## Tech Stack

| Technology | Purpose |
|---|---|
| React 18 | Component framework |
| Babel (standalone) | JSX compilation in browser |
| CSS-in-JS (inline styles) | Component-scoped styling |
| Google Fonts | Typography (Syne + DM Sans) |

---

## Components Built

### 1. Button
A flexible button component with multiple variants and sizes.

**Props:**
| Prop | Type | Default | Description |
|---|---|---|---|
| label | string | "Click Me" | Button text |
| variant | string | "primary" | Style: primary, secondary, ghost, danger, success |
| size | string | "md" | Size: sm, md, lg |
| disabled | boolean | false | Disables the button |
| onClick | function | — | Click handler |

**Usage:**
```jsx
<Button label="Get Started" variant="primary" size="lg" />
<Button label="Learn More" variant="secondary" size="md" />
<Button label="Delete" variant="danger" size="sm" disabled={false} />
```

---

### 2. Card
A feature card component used to display product features or content.

**Props:**
| Prop | Type | Default | Description |
|---|---|---|---|
| icon | string | "📚" | Emoji or icon |
| title | string | "Card Title" | Card heading |
| description | string | "..." | Card body text |

**Usage:**
```jsx
<Card icon="⏱️" title="Smart Timer" description="Adaptive focus sessions." />
```

---

### 3. Navbar
A responsive navigation bar component.

**Props:**
| Prop | Type | Default | Description |
|---|---|---|---|
| brand | string | "Studex" | Brand/logo name |
| links | array | [...] | Array of navigation link labels |
| ctaLabel | string | "Get Started" | CTA button text |

**Usage:**
```jsx
<Navbar
  brand="Studex"
  links={["Features", "Pricing", "About"]}
  ctaLabel="Try Free"
/>
```

---

### 4. Modal
A popup/overlay component for displaying content over the page.

**Props:**
| Prop | Type | Default | Description |
|---|---|---|---|
| isOpen | boolean | false | Controls visibility |
| onClose | function | — | Called when modal closes |
| title | string | "Modal Title" | Modal heading |
| children | ReactNode | — | Content inside modal |

**Usage:**
```jsx
const [open, setOpen] = React.useState(false);

<Button label="Open" onClick={() => setOpen(true)} />
<Modal isOpen={open} onClose={() => setOpen(false)} title="Sign Up">
  <p>Modal content goes here</p>
</Modal>
```

---

### 5. Form
A dynamic form component that renders fields from a config array.

**Props:**
| Prop | Type | Default | Description |
|---|---|---|---|
| fields | array | [] | Array of field config objects |
| submitLabel | string | "Submit" | Submit button text |
| onSubmit | function | — | Called on form submission |

**Field object shape:**
```js
{ label: "Email", name: "email", type: "email", placeholder: "you@example.com" }
```

**Usage:**
```jsx
<Form
  fields={[
    { label: "Name", name: "name", type: "text", placeholder: "Your name" },
    { label: "Email", name: "email", type: "email", placeholder: "Your email" },
  ]}
  submitLabel="Sign Up Free"
  onSubmit={(values) => console.log(values)}
/>
```

---

### 6. Badge
A small label component for status indicators and tags.

**Props:**
| Prop | Type | Default | Description |
|---|---|---|---|
| label | string | "New" | Badge text |
| color | string | "accent" | Color: accent, success, warning, danger |

**Usage:**
```jsx
<Badge label="New Feature" color="accent" />
<Badge label="Active" color="success" />
```

---

## Folder Structure

```
studex-component-library/
├── index.html        ← All components + demo page
└── README.md         ← This documentation
```

---

## Key Decisions

**1. All components in one file**
Since this uses browser-based React (no Node.js build tool), all components live in one HTML file. This makes it easy to run anywhere without installation.

**2. Props-driven design**
Every component accepts props so it can be customized without editing the component itself. This is the core principle of reusable components.

**3. CSS-in-JS styling**
Styles are written as JavaScript objects inside each component. This keeps styles scoped to the component and prevents conflicts.

**4. Consistent design tokens**
All components use the same CSS variables (--accent, --bg, --text etc.) ensuring visual consistency across the entire library.

---

## Author
Built by Ubah Joy — Week 1 Task 2, Frontend Development Internship
