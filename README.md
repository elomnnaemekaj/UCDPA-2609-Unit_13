# Unit 13 – Student Hands-On Lab

## Forms Deep Dive: Accessible, Validated Contact Form

---

## Purpose of this lab

In this lab, you will:

- Build a complete contact form using semantic HTML
- Apply client-side validation using HTML attributes
- Improve accessibility for keyboard and screen reader users
- Style the form using:
  - Custom CSS, and optionally
  - Bootstrap utility and form classes

The focus is on **structure, accessibility, and validation**, not visual complexity.

---

## What you will build

A fully functional **contact form** that:

- Uses semantic form elements
- Includes labels for all fields
- Applies browser-level validation
- Is accessible via keyboard and screen readers
- Is styled for clarity and usability

---

## Prerequisites

Before starting, make sure you have:

- VS Code (or another editor)
- A web browser
- Basic HTML and CSS knowledge
- Understanding of semantic elements
- (Optional) Familiarity with Bootstrap

---

## Part 1 — Project Setup

### Goal

Create a clean project structure.

---

### Steps

1. Create a new project folder, for example:

   ```bash
   mkdir accessible-form
   ```

2. Inside the folder, create:

   ```
   index.html
   style.css
   ```

3. Open `index.html` and add the following base structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Contact Form</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <!-- Form will go here -->
  </body>
</html>
```

---

### Checkpoint

- `index.html` loads in the browser
- `style.css` is linked correctly

---

## Part 2 — Build the Form Structure

### Goal

Create a semantic, well-structured form.

---

### Steps

1. Inside `<body>`, add a `<form>` element:
   - Use `method="post"`
   - Use `action="#"`

2. Group fields using `<fieldset>` and `<legend>`:

```html
<form method="post" action="#">
  <fieldset>
    <legend>Contact Information</legend>
    <!-- Fields go here -->
  </fieldset>
</form>
```

3. Add the following fields **with labels**:
   - Full Name (text input)
   - Email (email input)
   - Subject (text input)
   - Message (textarea)

Example:

```html
<label for="name">Full Name</label>
<input type="text" id="name" name="name" />

<label for="email">Email</label>
<input type="email" id="email" name="email" />

<label for="subject">Subject</label>
<input type="text" id="subject" name="subject" />

<label for="message">Message</label>
<textarea id="message" name="message"></textarea>
```

---

### Checkpoint

- Every input has a visible label
- `for` and `id` attributes match correctly

---

## Part 3 — Add Validation

### Goal

Apply browser-level validation using HTML attributes.

---

### Steps

1. Make all fields required:

   ```html
   required
   ```

2. Ensure the email field uses:

   ```html
   type="email"
   ```

3. Add a pattern to the Subject field (letters only):

```html
<input
  type="text"
  id="subject"
  name="subject"
  pattern="[A-Za-z ]+"
  title="Letters only"
  required
/>
```

4. Add appropriate constraints:
   - `minlength`
   - `maxlength`
   - `rows` for textarea

5. Add a submit button:

```html
<button type="submit">Submit</button>
```

---

### Checkpoint

- Browser blocks submission when fields are empty
- Invalid email formats are rejected
- Subject field only accepts letters

---

## Part 4 — Accessibility Enhancements

### Goal

Improve accessibility for assistive technologies.

---

### Steps

1. Add help text and associate it using `aria-describedby`:

```html
<label for="email">Email</label>
<input
  type="email"
  id="email"
  name="email"
  aria-describedby="emailHelp"
  required
/>
<small id="emailHelp">We'll never share your email.</small>
```

2. Navigate the form using **keyboard only** (`Tab`, `Shift + Tab`)
3. Ensure the tab order is logical
4. Avoid using `tabindex` unless absolutely necessary

---

### Checkpoint

- All inputs are reachable via keyboard
- Focus order follows visual order
- Help text is read by screen readers

---

## Part 5 — Styling the Form

### Goal

Improve readability and usability with styling.

---

## Part 5A — Custom CSS Styling

Add the following to `style.css`:

```css
form {
  max-width: 600px;
  margin: auto;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 6px;
}

label {
  display: block;
  margin-top: 1rem;
}

input,
textarea {
  width: 100%;
  padding: 0.5rem;
  margin-top: 0.5rem;
}

button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
}
```

---

### Checkpoint

- Form is centred
- Inputs are easy to read and interact with
- Layout feels clear and uncluttered

---

## Part 5B — Optional Bootstrap Styling

### Goal

Style the form using Bootstrap components.

---

### Steps

1. Add Bootstrap in `<head>`:

```html
<link
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
  rel="stylesheet"
/>
```

2. Update the form structure:

```html
<form class="p-4 border rounded mx-auto" style="max-width: 600px;">
  <fieldset>
    <legend>Contact Information</legend>

    <div class="mb-3">
      <label for="name" class="form-label">Full Name</label>
      <input type="text" class="form-control" id="name" required />
    </div>

    <!-- Repeat for other fields -->
  </fieldset>

  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

---

### Checkpoint

- Bootstrap styles are applied
- Form controls look consistent
- Validation still works

---

## Final Review

Before finishing, confirm that:

- All fields have labels
- Form works with keyboard only
- Validation triggers correctly
- Help text is accessible
- Styling improves clarity, not complexity

---

## End of Unit 13 Hands-On Lab

You should now be able to:

- Build accessible, validated HTML forms
- Apply semantic structure and ARIA attributes
- Style forms for usability
- Combine accessibility and design best practices

You are now ready to move on to **JavaScript-enhanced forms and client-side behaviour** in upcoming units.