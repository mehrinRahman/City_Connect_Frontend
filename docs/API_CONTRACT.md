# API Contract — Pending backend confirmation

The backend team owns the API. The frontend must not invent endpoint paths or present assumed contracts as confirmed. Fill in this document after receiving the actual API specification.

## Required contract checklist
- [ ] API base URL and local proxy/CORS configuration
- [ ] Login, logout, registration and session/refresh behavior
- [ ] Actual role values and staff provisioning process
- [ ] Anonymous complaint creation endpoint and privacy requirements
- [ ] Verified citizen complaint creation endpoint
- [ ] Tracking-token lookup and safe invalid-token response
- [ ] Complaint list/detail endpoints and pagination/filter format
- [ ] Categories, zones, wards and departments
- [ ] Attachment types, maximum size and upload response
- [ ] Public progress/status history versus internal notes schema
- [ ] Ward Clerk screening, routing, deadlines, duplicate linking and manual review permissions
- [ ] Department Clerk assignment, field reports and status-transition permissions
- [ ] Mayor analytics endpoints and filter formats
- [ ] Admin configuration endpoints
- [ ] Notification list, unread count and mark-read behavior
- [ ] Standard error response, date format, timezone and pagination shape

## Contract table
| Feature | Method / endpoint | Request / response | Role | Status |
|---|---|---|---|---|
| Login | TBD | TBD | Public | Needs backend contract |
| Citizen registration | TBD | TBD | Public | Needs backend contract |
| Anonymous complaint creation | TBD | TBD | Anonymous | Needs backend contract |
| Verified complaint creation | TBD | TBD | Citizen | Needs backend contract |
| Tracking token lookup | TBD | Token only; public status response | Public | Needs backend contract |
| Public resolved complaints | TBD | Approved public fields only | Public | Needs backend contract |
| Citizen complaint list/detail | TBD | Authenticated user's own records | Citizen | Needs backend contract |
| Ward queue and actions | TBD | Assigned ward scope | Ward Clerk | Needs backend contract |
| Department queue and actions | TBD | Assigned scope | Department Clerk | Needs backend contract |
| Mayor analytics | TBD | Aggregate data | Mayor | Needs backend contract |
| Admin master data | TBD | Supported configuration fields | System Admin | Needs backend contract |
| Notifications | TBD | Role-scoped notifications | Authenticated | Needs backend contract |

## Privacy rules
- Do not request citizen identity details on the anonymous tracking page; token is the primary input.
- Do not expose anonymous identity, internal notes, restricted attachments or unauthorized records.
- Do not add device identifiers, extra cookies or IP-related values to anonymous submission requests.
- Duplicate complaints are linked rather than deleted. False complaints require manual review.
- Backend authorization is authoritative. Frontend route guards are not security controls.
