
## 🧠 Programming Paradigms

### ❓ What is a programming paradigm, and can you provide examples?

**Answer:**
A programming paradigm is a style or approach to writing code based on a set of principles. It defines how problems are structured and solved in a programming language. Common paradigms include:

* **Imperative programming** – focuses on describing *how* to perform tasks using step-by-step instructions.
  *Example:* C, Java, JavaScript

* **Declarative programming** – focuses on *what* result you want, not how to achieve it.
  *Example:* SQL, HTML, React JSX

* **Object-Oriented Programming (OOP)** – organizes code using objects and classes.
  *Example:* Java, C++, Python

* **Functional programming** – emphasizes pure functions, immutability, and avoiding side effects.
  *Example:* Haskell, Scala, JavaScript (functional style)

---

### ❓ Compare imperative and declarative programming paradigms with web examples.

**Answer:**
In **imperative programming**, the developer explicitly defines how things should happen, step by step. In **declarative programming**, the focus is on what the outcome should be, and the system figures out how to achieve it.

* **Imperative example (Vanilla JS):**

```js
const button = document.createElement('button');
button.innerText = 'Click me';
document.body.appendChild(button);
```

* **Declarative example (React JSX):**

```jsx
<button>Click me</button>
```

**Comparison:**

| Imperative               | Declarative                     |
| ------------------------ | ------------------------------- |
| Focuses on *how*         | Focuses on *what*               |
| Manual control of steps  | Abstracted logic                |
| More verbose             | More readable and concise       |
| Examples: JS DOM, jQuery | Examples: React, JSX, HTML, SQL |

---

### ❓ How does React align with declarative programming? Benefits?

**Answer:**
React is declarative because you describe **what** the UI should look like based on the current state, and React handles the DOM updates automatically.

**Benefits:**

* Code is easier to read and reason about
* Reduces bugs caused by manual DOM updates
* Components are reusable and predictable
* Simplifies state-driven UI logic

---

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
