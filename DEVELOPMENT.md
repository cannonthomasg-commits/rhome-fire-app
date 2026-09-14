# Rhome Fire mobile app — version 0.1
This is an initial React Native / Expo prototype, not a production department system.
## Run
Install Node.js and run:
```
npm install
npx expo install --fix
npx expo start
```
Use a compatible Expo Go client or development build on iOS/Android. Native device builds have not been tested in this session.
## Implemented
Six navigable screens; sample personnel search; in-memory training topic entry; monthly A/B/C 48/96 calendar; resettable officer shift checklist.
Calendar anchor: C Shift on September 2–3, 2026, followed by A then B. Shift-change hour is not yet configured.
## Next implementation
Cloud authentication; invitation-only accounts; admin/officer/instructor/member authorization enforced on the server; personnel editing; training hours and attendance; certification verification and expiration queries; persistent officer worksheets.
No authentication, cloud sync, persistence, reminders, document uploads, or operational incident command functionality is implemented yet. Do not enter real department records into this prototype.
## Proposed data model
profiles(id, name, shift, role); training_sessions(id, title, start_at, hours, instructor_id); attendance(session_id, member_id, status); certifications(id, member_id, credential, issued_on, expires_on, verified_by); shift_settings(anchor_date, anchor_shift, change_hour); checklists(id, owner_id, title, items).
Roles must be assigned by an administrator using trusted backend operations. Members view their own records, instructors manage training, officers view assigned personnel and worksheets, administrators manage membership. Never rely on hiding controls for authorization.

