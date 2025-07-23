## 🧩 DOM and Events

### ❓ What is a DOM event, and how is it used?

**Answer:**
A DOM event is a signal that something has happened in the browser — like a user clicking a button, typing in a field, or submitting a form. JavaScript can respond to these events using event listeners.

**Example:**

```js
document.getElementById('btn').addEventListener('click', () => {
  alert('Button clicked');
});
```

---

### ❓ How to prevent the default action of an event?

**Answer:**
Use `event.preventDefault()` to stop the browser's default behavior for an event.

**Example (prevent form submission):**

```js
form.addEventListener('submit', (event) => {
  event.preventDefault();
  // Handle form data manually
});
```

---

### ❓ What is event delegation, and how to implement it in React?

**Answer:**
**Event delegation** means attaching a single event listener to a parent element to handle events from its child elements. This works because of **event bubbling**.

In React, event delegation is handled automatically — React attaches events to the root and uses synthetic events.

**Manual implementation in React:**

```jsx
<ul onClick={(e) => {
  if (e.target.tagName === 'LI') {
    console.log('Clicked item:', e.target.textContent);
  }
}}>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

