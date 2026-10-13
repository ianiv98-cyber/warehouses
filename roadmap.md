# Item identification codes
- [x] Generate unique four-digit codes for existing and future items.
- [x] Show codes in inventory, search, and Excel export; use them on the code-entry page.
- [x] Verify existing names, unique codes, and a stock deduction end to end.

# Code-entry confirmation
- [x] Show product name before selecting taking or returning.
- [x] Ask quantity after action selection and update stock only on confirmation.
- [x] Test cancellation, taking, and returning with inventory readback.

# Live code suggestions
- [x] Show matching products as soon as the first digit is typed in the code field.
- [x] Selecting a suggestion opens the product popup; a digit with no match shows a hint.
- [x] Test suggestion ordering, popup on selection, and cancellation without stock change.

# Employee access
- [x] Roles: new signups are employees and see only product search and code entry; Excel upload, export and manual editing stay admin-only and are blocked on the server too.
- [x] Verified with a real employee account: took one unit via code entry and the quantity dropped.

# Settings
- [x] Users screen (admin-only) listing every user with role change, password reset and delete.
- [x] Add-user button on the users screen: username + password, new user starts as employee; verified end to end (created and deleted a test user).
- [x] Gear icon at the top-left opens a menu with "משתמשים" (admins only) and "יציאה מהמערכת"; the separate logout icon is gone.
- [ ] Admin confirms the menu and the user list appear correctly in the app.

# Back to home
- [x] Login screen gets a back arrow to the home screen; users and code-entry screens keep their existing back arrows.
- [x] Verified: arrow visible on the login screen at a narrow viewport and opens the home screen.
