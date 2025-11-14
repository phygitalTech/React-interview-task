
# Employee Management Portal – React + Vite

A fully client-side Employee Management Portal built using **React + Vite**, featuring routing, form handling, state management, simulated API calls, data analytics, optimistic updates, and LocalStorage persistence.

This assignment requires building **4 pages** with advanced UI, validation, and data-manipulation logic.

---

#  Tech Stack

You may use:

* **React**
* **React Router**
* **Context API / Custom Hooks**
* **LocalStorage**
* Any UI library (optional)
* Simulated APIs using `setTimeout()`

Backend **not allowed**.
All data must be stored in state or LocalStorage.

---

#  Pages & Requirements

---

# 1️⃣ Dashboard (`/`)

### ✔ Features

* Simulated async fetch of employee data (with random failure).
* Loading placeholders while fetching.
* Error rendering if simulated API fails.

### ✔ Summary Cards (use `useMemo`)

* Total employees
* Active employees
* Inactive employees
* **Percentage** of active vs inactive
* **Top 3 positions** with most employees
* **Average tenure** (derived from `dateJoined`)
* **Growth trend**:

  * Employees added in the last 30 days
  * % change from previous 30 days

> All calculations must update automatically when employee data changes.

---

# 2️⃣ Employees List (`/employees`)

### ✔ Display

A table showing:

* Name
* Email
* Position
* Status
* Salary
* Date Joined
* Tenure (computed)
* Actions

### ✔ Search + Filtering

* 300ms debounce search (client-side).
* Filters:

  * All / Active / Inactive
  * Position
  * Salary range (`<50k`, `50–100k`, `>100k`)
* Filters must combine (e.g., "Active + Engineering + 50–100k").

### ✔ Sorting

* Multi-field sorting:

  * Name
  * Position
  * Salary
  * Date Joined
* Ascending/Descending
* Sort state must be reflected in URL query params.

### ✔ Pagination

* Client-side pagination (5 rows per page).
* Page number stored in URL query params.

### ✔ Optimistic Delete

* Remove row immediately.
* Restore if simulated delete API fails.

### ✔ Bulk Actions (optional but recommended)

* Bulk delete
* Bulk mark active / inactive

---

# 3️⃣ Add Employee (`/add-employee`)

### ✔ Required Fields

* Name
* Email
* Position
* Salary
* Status (Active/Inactive)
* Date Joined

### ✔ Validations

* Name ≥ 3 characters
* Email must be valid
* Position must start with a capital letter
* Salary must be a positive number

### ✔ Email Uniqueness Check (simulated async)

* Uses `setTimeout()`
* Prevent submission until validation passes
* Show loading indicator while checking

### ✔ Auto-Generated Employee Code

* Format: `EMP-{year}-{increment}`
  Example: `EMP-2025-0031`
* Derived from LocalStorage employee list.

### ✔ Salary Recommendation (computed)

Based on existing employees in the same position:

* Minimum
* Maximum
* Average

Show:
**“Recommended: 70k – 100k (Avg: 86k)”**

### ✔ Unsaved Changes Protection

If user tries to navigate away with dirty form fields, show a browser confirmation dialog.

---

# 4️⃣ Employee Details (`/employee/:id`)

### ✔ Display full details

* Name / Email / Position / Salary
* Status
* Date joined
* Employee code
* Computed tenure (years, months, days)

### ✔ Redirect on invalid ID

If employee does not exist, redirect to `/employees` and show a message.

### ✔ Status Change History

Whenever status changes:

```json
{
  "date": "2025-05-02",
  "oldStatus": "Inactive",
  "newStatus": "Active"
}
```

Stored in LocalStorage and displayed as a timeline.

### ✔ Similar Employees

* Based on same position
* Sorted by closest salary

### ✔ Soft Delete

* Employee remains stored but marked `deleted: true`.
* Deleted employees must:

  * Not appear in Dashboard counts
  * Not appear in Employees List table
* Details page should indicate deletion state and show:

  * Time since deletion
  * Impact on team totals (computed)

---

# 📁 Suggested Folder Structure

```
src/
  components/
  pages/
  hooks/
  context/
  utils/
  App.jsx
  main.jsx
```

---

# 📦 Deliverables

* GitHub repository with complete solution
* Hosted link (Vercel, Netlify, etc.)

---

# 📝 Notes

* Use clean folder structure and reusable components.
* Follow good UI/UX practices.
* Ensure all simulated APIs include:

  * Loading delays
  * Randomized success/failure (where required)
* Use memoization and derived values properly.
* Handle LocalStorage errors gracefully.


