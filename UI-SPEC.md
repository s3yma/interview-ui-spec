# User Interface Specification - User Management Screen

## 1. Purpose
This document defines the UI specification for the **User Management Screen** of the application.  
It provides software developers with detailed information about components, interactions, initial states, and behavior to ensure consistent implementation.

---

## 2. Initial View
- **Page Title:** User Management
- **Default Components Visible:**
  - User table showing existing users with columns: ID, User Name, Email, Enabled
  - "+ New User" button (top-left)
  - "Hide Disabled User" checkbox (top-left)
  - "Save User" button (top-right)
- **Form Panel:** Right side shows the "New User" form, initially empty
- **Default States:**
  - User table: first row highlighted (optional)
  - New User form: all input fields empty
  - User Roles dropdown: placeholder "Select user roles..."
  - Enabled checkbox: unchecked

---

## 3. Screenshots / Wireframes

### User Table
![User Table](interview-ui-spec/user-table.png)

### New User Form
![New User Form](interview-ui-spec/new-user-form.png)

### Top Bar Buttons
![Top Bar Buttons](interview-ui-spec/top-bar-buttons.png)

---

## 4. UI Components

| Component | Type | Description | Behavior |
|-----------|------|-------------|----------|
| + New User Button | Button | Opens New User form (already visible in this layout) | Enabled at all times; clicking clears form fields for new entry |
| Hide Disabled User | Checkbox | Filters table to hide disabled users | Checked: only enabled users shown; Unchecked: all users shown |
| Save User | Button | Saves new or edited user data | Enabled only when form validation passes; clicking triggers save and refreshes table |
| User Table | Table | Displays list of users | Columns sortable; clicking a row highlights selection and populates form for editing |
| Table Columns | Column | ID, User Name, Email, Enabled | ID: read-only, sortable; Enabled: boolean displayed as checkbox; sortable |
| Username | Text Input | Enter username | Required; validation: non-empty, unique |
| Display Name | Text Input | Enter display name | Optional |
| Phone | Text Input | Enter phone number | Optional; validation: numeric and format |
| Email | Text Input | Enter email | Required; validation: valid email format |
| User Roles | Dropdown | Select one or multiple roles | Options: Guest, Admin, SuperAdmin; required field; default placeholder visible |
| Enabled | Checkbox | Enable or disable the user | Checked: active; unchecked: disabled |

---

## 5. Behavior and Interactions

1. **Table Interaction:**
   - Clicking a row populates the New User form with selected user’s data for editing
   - Sorting: Clicking column headers sorts ascending/descending
   - Filtering: Hide Disabled User checkbox updates table in real-time

2. **Form Interaction:**
   - Form clears when "+ New User" is clicked
   - Validation errors appear below respective fields
   - Save User button triggers save only if all required fields are valid
   - After save, the table refreshes to show updated list

3. **Dropdown Interaction:**
   - Multi-select roles allowed
   - Placeholder text disappears when roles selected

4. **Checkbox Interaction:**
   - Enabled checkbox updates user status upon save
   - Hide Disabled User checkbox filters table instantly

5. **Feedback & Notifications:**
   - Success: Toast message "User saved successfully"
   - Error: Inline messages for invalid fields
   - Loading spinner displayed while saving

---

## 6. Notes
- Follow application-wide design system: colors, fonts, spacing
- Responsive layout: form and table adjust for tablet and desktop
- Accessibility:
  - Keyboard navigation between table rows and form inputs
  - Screen reader labels for all fields and buttons
- Consistent terminology: “User Roles”, “Enabled”, “Save User”, etc.

---

## 7. References
- Mockup images located in `interview-ui-spec/` folder
