
## 💾 localStorage & sessionStorage

### ❓ What is the purpose of localStorage and sessionStorage?

**Answer:**
Both `localStorage` and `sessionStorage` store key-value data in the browser:

* `localStorage` persists data **even after the tab or browser is closed**
* `sessionStorage` keeps data only **for the current tab/session**

**Use cases:**

* `localStorage`: theme, language preference, login state
* `sessionStorage`: temporary form data, one-time alerts

---

### ❓ How to remove a specific item from sessionStorage, and what happens when the tab is closed?

**Answer:**
To remove:

```js
sessionStorage.removeItem('key');
```

When the tab is closed, the entire `sessionStorage` is cleared. It is not shared across tabs.

---

### ❓ How to synchronize data across tabs using localStorage and avoid conflicts?

**Answer:**
Use the `storage` event to detect changes:

```js
window.addEventListener('storage', (event) => {
  if (event.key === 'theme') {
    // Update UI
  }
});
```

To handle conflicts:

* Store data as JSON with a `timestamp`
* Compare timestamps before applying changes

---
