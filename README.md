# Employee Management Portal – React + Vite Assignment

## Overview
Build a frontend application using **React + Vite** that implements an Employee Management Portal.  
The project must include **4 pages**, routing, form handling, state management, and simulated API interactions.  
No backend should be used. All data must be stored using local state or LocalStorage.

---

## Tech Requirements
You may use:
- React
- React Router
- Context API or custom hooks
- LocalStorage
- Any UI library (optional)

You must simulate API calls using `setTimeout`.

---

## 🖥️ Pages & Requirements

---

## 1. Dashboard Page (`/`)

### Features:
- Fetch employee data through a simulated async API.
- Display summary cards:
  - Total Employees
  - Active Employees
  - Inactive Employees
- Show loading placeholders while data is being fetched.
- Show an error message if the simulated API randomly fails.
- Use memoization (`useMemo`) for calculated summary values.
- **Optional:** Add a simple chart (Active vs Inactive).

---

## 2. Employees List Page (`/employees`)

### Features:
- Display a table of employees showing:
  - Name  
  - Email  
  - Position  
  - Status  
  - Actions  
- Implement search with **300ms debounce**.
- Implement filtering:
  - All
  - Active
  - Inactive
- Implement **client-side pagination** (5 employees per page).
- Reflect page and filter values in URL query params.
- Implement optimistic delete:
  - Remove employee immediately
  - Restore if simulated API delete fails

---

## 3. Add Employee Page (`/add-employee`)

### Features:
- Required form fields:
  - Name
  - Email
  - Position
  - Status (Active/Inactive)
- Validations:
  - Name must be at least 3 characters.
  - Position must start with a capital letter.
  - Email must be valid.
- Simulated async email uniqueness check:
  - Show loading indicator while verifying.
  - Prevent submission until email is verified.
- Show browser "unsaved changes" confirmation when navigating away with incomplete form data.

---

## 4. Employee Details Page (`/employee/:id`)

### Features:
- Display full employee details.
- Redirect to `/employees` with a message if the employee ID is invalid.
- **Optional:** Activity timeline showing events such as creation and status changes.
- Implement soft delete:
  - Mark employee as deleted
  - Exclude deleted employees from dashboard and list pages
  - Keep deleted records stored

---

## 📁 Suggested Project Structure
src/
components/
pages/
hooks/
context/
utils/
App.jsx
main.jsx

---

## 📦 Deliverables
- GitHub repository containing your complete solution.
- send hosted Link
---

## Notes
- Focus on clean code, reusable components, meaningful file structure, and good UI/UX.
- Ensure all features work as described, including simulated API behavior.

