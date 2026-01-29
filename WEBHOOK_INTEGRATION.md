# CareTutor Webhook Integration

## Authentication

| Parameter | Value |
|-----------|-------|
| Type | Basic Auth |
| Username | `tltm` |
| Password | `a#^hC(I$VBNnQD2@nBIuwUwp` |

**Header:** `Authorization: Basic dGx0bTphI15oQyhJJFZCTm5RRDJAbkJJdXdVd3A=`

---

## 1. Course Status Webhook

**URL:** `POST https://lmsi.info/caretutor/backend/api/webhooks/course-status`

**Body:**
```json
{
  "user_id": 12345,
  "course_id": 221,
  "status": "completed",
  "score": 85,
  "progress": 100,
  "is_completed": 1,
  "from_timestamp": "2025-01-01 00:00:00",
  "to_timestamp": "2025-01-29 12:30:00"
}
```

| Field | Required | Description |
|-------|----------|-------------|
| user_id | Yes | CareTutor User ID |
| course_id | Yes | Course ID |
| status | No | `registered`, `in_progress`, `completed`, `failed` |
| score | No | Score (0-100) |
| progress | No | Progress % (0-100) |
| is_completed | No | 1 = yes, 0 = no |
| from_timestamp | No | Start date |
| to_timestamp | No | Completion date |

---

## 2. Certificate Webhook

**URL:** `POST https://lmsi.info/caretutor/backend/api/webhooks/certificate`

**Body:**
```json
{
  "user_id": 12345,
  "course_id": 221,
  "certificate_id": 9999,
  "serial_number": "CERT-2025-12345",
  "awarded": "2025-01-29",
  "expires": "2026-01-29"
}
```

| Field | Required | Description |
|-------|----------|-------------|
| user_id | Yes | CareTutor User ID |
| course_id | Yes | Course ID |
| certificate_id | No | Certificate ID |
| serial_number | No | Certificate serial |
| awarded | No | Award date (YYYY-MM-DD) |
| expires | No | Expiry date (YYYY-MM-DD) |

---

## When to Trigger

| Event | Webhook |
|-------|---------|
| User registers for course | Course Status (`status: registered`) |
| User starts course | Course Status (`status: in_progress`) |
| User completes course | Course Status (`status: completed`) |
| User fails course | Course Status (`status: failed`) |
| Certificate awarded | Certificate Webhook |
