## 🔄 Lifecycle Methods & Optimization

### ❓ What are lifecycle methods in React and why are they important?

**Answer:**
Lifecycle methods are special methods in class components that allow you to run code during different stages of a component’s life.

**Main stages:**

* **Mounting:** `constructor`, `componentDidMount`
* **Updating:** `shouldComponentUpdate`, `componentDidUpdate`
* **Unmounting:** `componentWillUnmount`

**Why important:**
They allow data fetching, DOM interaction, setting timers, cleanup, and performance optimization.

---

### ❓ How to fetch data using componentDidMount?

**Answer:**
Use `componentDidMount` to fetch data after the initial render:

```js
componentDidMount() {
  fetch('/api/users')
    .then(res => res.json())
    .then(data => this.setState({ users: data }));
}
```

* Safe to interact with DOM
* Runs only once

---

### ❓ Best practices for componentDidMount and optimizing with shouldComponentUpdate?

**Answer:**

**componentDidMount:**

* Handle loading and error states
* Prevent memory leaks (track mounted state or abort fetch)
* Avoid setting state if component is unmounted

**shouldComponentUpdate:**

* Avoid unnecessary re-renders
* Compare props/state before re-rendering
* Use `PureComponent` or `React.memo` for shallow comparison
* Improves performance in large applications

```js
shouldComponentUpdate(nextProps) {
  return nextProps.value !== this.props.value;
}
```
