# User Management Screen - UI Specification

## 1. Overview
This document describes the User Management interface. The screen allows administrators to:
- View users
- Filter/search users
- Add new users
- Edit user details
- Enable/disable users

---

## 2. Initial Page State
When the page loads:
- A table of users is displayed on the left side
- The first user in the list is selected by default
- User details appear on the right panel
- "Hide Disabled User" checkbox is checked by default
- "Enabled" users are shown unless filtered out

---

## 3. Layout Structure

### 3.1 Left Panel (User List)
Contains:
- + New User button
- Hide Disabled User checkbox
- User table

#### Table Columns:
- ID
- User Name
- Email
- Enabled (true/false)

#### Features:
- Sorting (by clicking column headers)
- Filtering (via icons in headers)
- Row selection

---

### 3.2 Right Panel (User Form)
Displays selected user details or empty form for new user.

#### Fields:
- Username (text input, required)
- Display Name (text input, required)
- Phone (text input, optional)
- Email (text input, required, must be valid format)
- User Roles (multi-select dropdown)
  - Options: Guest, Admin, SuperAdmin
- Enabled (checkbox)

#### Buttons:
- Save User

---

## 4. Functional Requirements

### 4.1 Create New User
- Clicking "+ New User":
  - Clears the form
  - Sets default values:
    - Enabled = false
    - Roles = empty
- User fills form and clicks "Save User"
- Validation rules applied
- New user added to table

---

### 4.2 Edit Existing User
- Clicking a row loads user data into form
- User edits fields
- Click "Save User" to update

---

### 4.3 Validation Rules
- Username: required, unique
- Display Name: required
- Email: required, valid email format
- Phone: optional
- At least one role should be selectable (optional depending on system design)

---

### 4.4 Enable/Disable User
- Controlled via "Enabled" checkbox
- Disabled users:
  - Still exist in system
  - Hidden when "Hide Disabled User" is checked

---

### 4.5 Filtering & Sorting
- Users can:
  - Sort by any column
  - Filter via column filters
- "Hide Disabled User":
  - When checked → hide users where Enabled = false
  - When unchecked → show all users

---

## 5. User Interaction Flow

### Scenario 1: Add User
1. Click "+ New User"
2. Fill in form
3. Select role(s)
4. Click "Save User"
5. User appears in list

### Scenario 2: Edit User
1. Select user from table
2. Modify fields
3. Click "Save User"
4. Changes reflected immediately

### Scenario 3: Filter Users
1. Toggle "Hide Disabled User"
2. Table updates dynamically

---

## 6. Non-Functional Requirements
- Responsive UI (usable on different screen sizes)
- Fast table rendering
- Form validation feedback (inline errors)
- Accessibility (labels for inputs, keyboard navigation)

---

## 7. Assumptions
- Only admins can access this page
- Backend API handles persistence
- Roles are predefined and static

---

## 8. Future Improvements
- Search bar
- Pagination
- Bulk actions (enable/disable multiple users)
- User activity logs

---
