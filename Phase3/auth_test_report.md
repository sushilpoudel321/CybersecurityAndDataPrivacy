Administrator
✅ Can do
Can register and log in as administrator — /login + /register
Observation: Admin registration and login succeed; admin is redirected to admin dashboard
Spec: ✔️ Matches spec (point 2 – registered users can log in; point 4 – admin role)

Can access resource form via /resources
Observation: Resource creation form is displayed; admin can fill in and submit to create a resource
Spec: ✔️ Matches spec (point 4 – admin can add resources)

Can access reservation API — GET /api/reservations
Observation: Admin receives full reservation data in JSON, including all reservations from all users
Spec: ✔️ Matches spec (point 4 – admin can view/manage all reservations)

Can access users API — GET /api/users
Observation: Admin receives full user list in JSON, including usernames, roles, and user tokens
Spec: ✔️ Matches spec (point 4 – admin can view all users)

Can access reservation details — /reservation?id=3
Observation: Administrator can view reservation details for any reservation, regardless of owner
Spec: ✔️ Matches Point 4 – admin can manage all reservations

Can update any reservation — /reservation?id=3
Observation: Administrator can update reservations created by any reserver via UI or direct URL
Spec: ✔️ Matches Point 4 – full reservation management

Can delete any reservation — /reservation?id=3
Observation: Administrator can delete reservations created by any user via UI or direct URL
Spec: ✔️ Matches Point 4 – full reservation management

❌ Cannot do / Issues
Cannot access admin resource creation page — /admin/resources/new
Observation: Status page shows “Not Found” with back-to-home button; UI link missing, but admin can still create resources via /resources
Spec: ⚠️ Not defined in spec (UI inconsistency — admin functionality exists but the dedicated admin page is unavailable)

Cannot delete a reserver — /admin/users/delete/:id
Observation: Status page shows “Not Found” with back-to-home button; admin cannot delete users via the UI/API
Spec: ⚠️ Not defined in spec (expected: admin should be able to delete users; current behavior prevents it)

Cannot manage all reservations — /admin/reservations
Observation: Status page shows “Not Found” with back-to-home button; admin cannot access reservation management UI
Spec: ⚠️ Not defined in spec (expected: admin should be able to view/manage all reservations)
