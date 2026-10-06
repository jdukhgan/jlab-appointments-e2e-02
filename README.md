# JLab Appointment Board — disposable workflow acceptance fixture
Build a small web app for a team to manage appointments across users and work lanes. Use Node.js 24, a lightweight web UI and SQLite. No external calendar, authentication service or production deployment. Store only fictional seed data. Keep dependencies minimal. Follow DESIGN.md.

## Twelve tasks and acceptance criteria
1. Architecture and task plan: Lead inspects repository, records decisions and creates dependency-linked tasks using the configured workflow; no task is marked Done without evidence.
2. Visual design: UI Designer proposes component-based appointment board, forms and empty/error states, responsive layouts and light/dark themes in DESIGN-PLAN.md before UI implementation.
3. Application scaffold: Builder provides one documented command to start the app, health endpoint and meaningful test command; startup works on Node 24.
4. SQLite schema and seed: users, lanes and appointments with foreign keys and fictional sample data; database survives restart. Depends on 3.
5. Users and lanes API: create/list/edit users and lanes; reject blank names and unknown IDs with helpful errors. Depends on 4.
6. Appointment CRUD API: create/list/edit/delete appointments with title, assigned user, lane, start/end and notes; validate end after start. Depends on 4.
7. Responsive board: display dated appointments by lane, user/date filters and empty state. Depends on 2, 5, 6.
8. Appointment form: accessible create/edit dialog, validation and loading/error states; updates board after save. Depends on 2, 6, 7.
9. Conflict handling: reject overlapping appointments for the same user; allow different users at the same time; UI explains conflict without losing input. Depends on 6, 8.
10. User and lane management UI: add/edit users and lanes and reflect changes in selectors; keyboard operation works. Depends on 5, 7.
11. Independent review and integration checks: Reviewer checks exact integrated revision, CRUD, validation, persistence and conflict tests; findings return to Implement. Depends on 7-10.
12. Independent browser verification and Lead acceptance: verify real CRUD, filtering, conflict, reload/restart persistence, keyboard navigation, both themes at 1440/820/390 widths; record URL/revision, screenshots and console/network errors. Lead assesses all children and evidence. Depends on 11.

## Execution contract
Use the configured Lead, UI Designer, Builder, Reviewer and UI Tester / Verifier profiles and selected MCPs/skills. Run independent tasks in isolated worktrees. Respect actual configured concurrency limits. Record session/profile IDs, task transitions and delegation outcomes. Do not replace the workflow with a single agent doing everything. Report blocked authentication/tooling truthfully. This is a disposable acceptance project; do not touch unrelated projects or shared infrastructure.
