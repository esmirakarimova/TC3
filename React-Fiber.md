

## ⚛️ React Fiber

### ❓ What is React Fiber and why was it introduced?

**Answer:**
React Fiber is the **new core engine** introduced in React 16 to improve rendering performance and flexibility.

**Why introduced:**

* Make rendering interruptible and resumable
* Add support for priorities and scheduling
* Enable features like Concurrent Mode and Suspense

---

### ❓ How does React Fiber improve the reconciliation process?

**Answer:**
Fiber improves reconciliation by:

* Breaking work into units (fiber nodes)
* Allowing React to pause and resume rendering
* Prioritizing updates (e.g., user input > animation)
* Providing better error handling (`componentDidCatch`)

---

### ❓ How does Fiber manage commit and reconciliation phases?

**Answer:**
React rendering is split into two phases:

1. **Render (Reconciliation) Phase**

   * Builds a new fiber tree
   * Interruptible and async
   * No DOM changes yet

2. **Commit Phase**

   * Applies changes to the DOM
   * Runs lifecycle methods
   * Synchronous and non-interruptible

Fiber assigns **"lanes"** to schedule updates based on priority.
