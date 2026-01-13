
### Current Status: ✅ READY FOR TESTING

All core features have been implemented. The system is now ready for comprehensive testing before production deployment.

---

## 📊 Implementation Progress

### Completed Phases (✅ 100%)

| Phase | Tasks | Status |
|-------|-------|--------|
| Backend Foundation | 5 tasks | ✅ Complete |
| Authentication System | 3 tasks | ✅ Complete |
| Core APIs | 3 tasks | ✅ Complete |
| Reports & Groups | 4 tasks | ✅ Complete |
| Caching & Sync | 3 tasks | ✅ Complete |
| Frontend Setup | 4 tasks | ✅ Complete |
| Frontend Core | 4 tasks | ✅ Complete |
| Frontend Pages | 6 tasks | ✅ Complete |
| Frontend Features | 7 tasks | ✅ Complete |
| **Critical Features** | **15 tasks** | **✅ Complete** |


---

## 🚦 TLM  Report

### Status: FULLY IMPLEMENTED AND READY


### What is TLM Report?

The TLM Report provides a visual, color-coded view of training compliance and certificate expiry status, making it easy to identify:
- ✅ Compliant users (Green)
- ⚠️ Users needing attention (Orange)
- ❌ Non-compliant users (Red)

### Implementation Status

| Component | Status | Details |
|-----------|--------|---------|
| **Progress Report TLM** | ✅ Complete | Color-coded by training status |
| **Certificate Report TLM** | ✅ Complete | Color-coded by expiry date |
| **Excel Export with Colors** | ✅ Complete | ExcelJS library with full color support |
| **API Endpoints** | ✅ Complete | `/api/reports/progress` & `/api/reports/certificates` |
| **Frontend Display** | ✅ Complete | React components with color indicators |
| **Bulk Export** | ✅ Complete | Export all data with colors preserved |

---

### TLM Color Coding System

#### Progress Report (Training Status)
| Status | Color | Hex Code | Meaning |
|--------|-------|----------|---------|
| **Completed** | 🟢 Green | `#008000` | Training completed successfully |
| **Registered** | 🔵 Blue | `#3BB6FF` | User enrolled but not started |
| **In Progress** | 🟠 Orange | `#CC6600` | Training in progress |
| **Failed** | 🔴 Red | `#FF0000` | Training failed or incomplete |

#### Certificate Report (Expiry Status)
| Status | Color | Hex Code | Meaning | Criteria |
|--------|-------|----------|---------|----------|
| **Valid** | 🟢 Green | `#008000` | Certificate valid | >60 days until expiry |
| **Expiring Soon** | 🟠 Orange | `#FF7800` | Action needed | ≤60 days until expiry |
| **Expired** | 🔴 Red | `#FF0000` | Critical - Retraining required | ≤0 days (expired) |

---

### OLD System (PHP/WordPress) vs NEW System (Node.js/React)

#### Progress Report Comparison

| Feature | Old PHP System | New Node.js System | Improvement |
|---------|---------------|-------------------|-------------|
| **Color Coding** | ❌ No colors in Excel | ✅ Full color support | Major improvement |
| **Export Format** | Basic CSV/Excel | Professional Excel with colors | Better visualization |
| **Library Used** | PHPExcel (deprecated) | ExcelJS (modern, maintained) | More reliable |
| **Cell Formatting** | Plain white cells | Colored cells with white text | Easy to read |
| **Status Tracking** | Basic text status | Color-coded with visual indicators | Faster identification |
| **Filtering** | Limited server-side | Advanced filtering options | More flexible |
| **Performance** | Slow for large datasets | Optimized queries with pagination | Faster loading |
| **User Experience** | Manual download only | In-browser view + download | More convenient |

#### Certificate Report Comparison

| Feature | Old PHP System | New Node.js System | Improvement |
|---------|---------------|-------------------|-------------|
| **Expiry Colors** | ❌ No color coding | ✅ Traffic light colors | Instant visual status |
| **Days Calculation** | Manual calculation | Auto-calculated "days until expiry" | Automated |
| **Export Format** | Plain Excel | Color-coded Excel | Better compliance tracking |
| **Expiry Alerts** | None | Visual red/orange alerts | Proactive management |
| **Bulk Actions** | Not available | Bulk certificate download (ZIP) | Time-saving |
| **Frozen Headers** | No | Yes - Frozen columns & headers | Easier navigation |
| **Cell Colors** | White background | Colored backgrounds | Clear visual cues |
| **Font Color** | Black on white | White on colored background | High contrast |

---

### Technical Implementation Details

#### Backend (Node.js)
```javascript
// Progress Report with Status
GET /api/reports/progress
- Returns user course status with color indicators
- Supports filtering by status, branch, user, course
- Pagination for large datasets
- Optimized SQL queries with JOIN operations
```

#### Frontend (React)
```javascript
// Components Created
1. ProgressReportExcel.jsx
   - Uses ExcelJS library
   - Applies cell colors based on status
   - Frozen headers and columns
   - Timestamp in filename

2. CertificateReportExcel.jsx
   - Uses ExcelJS library
   - Applies colors based on days until expiry
   - Calculates expiry status automatically
   - Frozen headers for easy scrolling
```

#### Excel Features Implemented
1. **Color-coded cells** - Based on status/expiry
2. **White text on colored backgrounds** - High visibility
3. **Frozen headers** - Always visible when scrolling
4. **Frozen columns** - First 2 columns remain visible
5. **Professional formatting** - Bold headers, proper widths
6. **Timestamp in filename** - `TLM_Report_YYYY-MM-DD_HHmmss.xlsx`
7. **All data included** - Name, course, status, dates, scores

---

### Sample TLM Report Output

#### Progress Report Excel
```
| User Name    | Course Name      | Status      | Score | Progress | Completed Date |
|--------------|------------------|-------------|-------|----------|----------------|
| John Doe     | Fire Safety      | completed   | 85%   | 100%     | 2026-01-10     |  ← GREEN
| Jane Smith   | First Aid        | in_progress | 45%   | 60%      | -              |  ← ORANGE
| Bob Johnson  | Manual Handling  | registered  | 0%    | 0%       | -              |  ← BLUE
| Mary Wilson  | Health & Safety  | failed      | 35%   | 100%     | 2026-01-12     |  ← RED
```

#### Certificate Report Excel
```
| User Name    | Course Name      | Awarded    | Expires    | Days Until Expiry | Status         |
|--------------|------------------|------------|------------|-------------------|----------------|
| John Doe     | Fire Safety      | 2025-01-10 | 2026-01-10 | 362 days          | Valid          |  ← GREEN
| Jane Smith   | First Aid        | 2025-06-15 | 2026-03-15 | 45 days           | Expiring Soon  |  ← ORANGE
| Bob Johnson  | Manual Handling  | 2024-01-01 | 2025-01-01 | -15 days          | EXPIRED        |  ← RED
```

---

### Conclusion: TLM Report Status

✅ **FULLY COMPLETED** 

The TLM Report system has been successfully migrated and enhanced with:
- ✅ Better color coding than old system
- ✅ Modern, maintained libraries (ExcelJS)
- ✅ Automated expiry calculations
- ✅ Professional Excel formatting
- ✅ Easy-to-use interface
- ✅ Fast performance with caching
- ✅ Bulk export capabilities

---

## 🎯 Key Features Completed

### 1. User Management System ✅
- User listing with pagination and search
- Create, update, and deactivate users
- Branch-based user organization
- Role and permissions management

### 2. Course Management System ✅
- Complete course catalog
- Course creation and editing
- Category-based organization
- Course groups and hierarchies

### 3. Certificate Management ✅
- Automatic PDF generation (Puppeteer)
- Individual certificate download
- Bulk ZIP download (multiple certificates)
- Certificate status tracking
- Template system (Handlebars)

### 4. Real-time Data Synchronization ✅
- **Primary Method:** Webhooks from CareTutor platform
- **Backup Method:** Scheduled API sync (midnight + every 4 hours)
- Auto-sync for users, courses, branches, status, certificates

### 5. Reporting System ✅
- **Progress Report:** User course completion tracking
- **Certificate Report:** Expiry tracking with TLM colors
- **Excel Export:** Color-coded cells (ExcelJS library)
  - Green: Completed/Not due
  - Orange: In Progress/Due soon
  - Red: Failed/Expired

### 6. Admin Dashboard ✅
- Login system (JWT authentication)
- Sync control panel
- Real-time statistics
- Certificate generation tools

### 7. Branch Hierarchy System ✅
- Tree structure view
- Parent-child relationships
- Branch path traversal
- Search functionality
- Descendant tracking

### 8. Logging System ✅
- Winston logger with daily file rotation
- HTTP request logging
- Error tracking
- Separate log files for errors

---

## 🔌 API Endpoints Reference

### Base URL
```
Production: https://lmsi.info/caretutor/backend/api
Development: http://localhost:3000/api
```

### Authentication Required
All endpoints require JWT authentication via `Authorization: Bearer <token>` header (except login).

---

## 📋 Complete API Documentation

### 1. Authentication Endpoints

#### POST /api/auth/login
**Purpose:** Admin login to the system
**Authentication:** None (public endpoint)
**Request Body:**
```json
{
  "email": "admin@example.com",
  "password": "password123"
}
```
**Response:**
```json
{
  "success": true,
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIs...",
    "user": {
      "id": 1,
      "email": "admin@example.com",
      "name": "Admin User",
      "role": "super_admin"
    }
  }
}
```

#### GET /api/auth/me
**Purpose:** Get current logged-in user information
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "data": {
    "id": 1,
    "email": "admin@example.com",
    "name": "Admin User",
    "role": "super_admin"
  }
}
```

#### POST /api/auth/logout
**Purpose:** Logout current user
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "message": "Logged out successfully"
}
```

---

### 2. User Management Endpoints

#### GET /api/users
**Purpose:** Get paginated list of all users
**Authentication:** Required
**Query Parameters:**
- `page` (optional): Page number (default: 1)
- `limit` (optional): Items per page (default: 50)
- `search` (optional): Search by name/email
- `branch` (optional): Filter by branch ID

**Response:**
```json
{
  "success": true,
  "data": {
    "users": [
      {
        "id": 123,
        "caretutor_user_id": 456,
        "login": "john.doe",
        "name": "John",
        "surname": "Doe",
        "email": "john@example.com",
        "branch": "5",
        "active": 1
      }
    ],
    "pagination": {
      "total": 150,
      "page": 1,
      "limit": 50,
      "totalPages": 3
    }
  }
}
```

#### POST /api/users
**Purpose:** Create a new user in the system
**Authentication:** Required
**Request Body:**
```json
{
  "login": "john.doe",
  "email": "john@example.com",
  "name": "John",
  "surname": "Doe",
  "branchId": 5,
  "caretutorUserId": 456,
  "active": true
}
```

#### GET /api/users/:id
**Purpose:** Get detailed information about a specific user
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "data": {
    "id": 123,
    "caretutor_user_id": 456,
    "login": "john.doe",
    "name": "John",
    "surname": "Doe",
    "email": "john@example.com",
    "branch": "5",
    "active": 1,
    "user_type_id": "2",
    "user_type_name": "Employee"
  }
}
```

#### PUT /api/users/:id
**Purpose:** Update an existing user
**Authentication:** Required
**Request Body:** (all fields optional)
```json
{
  "name": "John",
  "surname": "Doe",
  "email": "newemail@example.com",
  "branchId": 6,
  "active": false
}
```

#### DELETE /api/users/:id
**Purpose:** Deactivate a user (soft delete)
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "message": "User deactivated successfully"
}
```

---

### 3. Course Management Endpoints

#### GET /api/courses
**Purpose:** Get list of all active courses
**Authentication:** Required
**Query Parameters:**
- `search` (optional): Search by course name
- `category` (optional): Filter by category ID

**Response:**
```json
{
  "success": true,
  "data": [
    {
      "id": 789,
      "caretutor_course_id": 101,
      "name": "Fire Safety Training",
      "slug": "fire-safety-training",
      "category": "Safety",
      "refresher_period": {"months": 12}
    }
  ]
}
```

#### POST /api/courses
**Purpose:** Create a new course
**Authentication:** Required
**Request Body:**
```json
{
  "name": "New Course Name",
  "slug": "new-course-name",
  "description": "Course description",
  "caretutorCourseId": 101,
  "refresherPeriod": {"months": 12},
  "categoryId": 5
}
```

#### GET /api/courses/:id
**Purpose:** Get detailed course information
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "data": {
    "id": 789,
    "caretutor_course_id": 101,
    "name": "Fire Safety Training",
    "slug": "fire-safety-training",
    "description": "Learn fire safety procedures",
    "category": "Safety",
    "refresher_period": {"months": 12}
  }
}
```

#### PUT /api/courses/:id
**Purpose:** Update an existing course
**Authentication:** Required
**Request Body:** (all fields optional)
```json
{
  "name": "Updated Course Name",
  "description": "New description",
  "refresherPeriod": {"months": 24}
}
```

#### DELETE /api/courses/:id
**Purpose:** Archive a course (soft delete - sets to draft)
**Authentication:** Required

#### POST /api/courses/by-groups
**Purpose:** Get courses filtered by group IDs
**Authentication:** Required
**Request Body:**
```json
{
  "groupIds": [1, 2, 3]
}
```

---

### 4. Branch Management Endpoints

#### GET /api/branches
**Purpose:** Get flat list of all branches
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "data": [
    {
      "term_id": 5,
      "name": "Head Office",
      "slug": "head-office",
      "parent": 0
    }
  ]
}
```

#### GET /api/branches/hierarchy
**Purpose:** Get branches organized as a tree structure
**Authentication:** Required
**Use Case:** Display branch hierarchy in UI with nested levels
**Response:**
```json
{
  "success": true,
  "data": [
    {
      "term_id": 1,
      "name": "Head Office",
      "parent": 0,
      "children": [
        {
          "term_id": 5,
          "name": "Regional Office",
          "parent": 1,
          "children": []
        }
      ]
    }
  ]
}
```

#### GET /api/branches/search?q=searchTerm
**Purpose:** Search branches by name
**Authentication:** Required
**Query Parameters:**
- `q`: Search term (minimum 2 characters)

**Response:**
```json
{
  "success": true,
  "data": [
    {
      "term_id": 5,
      "name": "Regional Office",
      "slug": "regional-office",
      "parent": 1,
      "path": "Head Office > Regional Office"
    }
  ]
}
```

#### GET /api/branches/by-parent/:parentId
**Purpose:** Get direct children of a branch
**Authentication:** Required
**Use Case:** Load branches level-by-level for navigation
**Response:**
```json
{
  "success": true,
  "data": [
    {
      "term_id": 5,
      "name": "Regional Office",
      "parent": 1,
      "has_children": true,
      "child_count": 3
    }
  ]
}
```

#### GET /api/branches/:id
**Purpose:** Get single branch with its immediate children
**Authentication:** Required

#### GET /api/branches/:id/path
**Purpose:** Get the full path from root to a branch
**Authentication:** Required
**Use Case:** Show breadcrumb navigation
**Response:**
```json
{
  "success": true,
  "data": {
    "path": "Head Office > Regional Office > Sub Branch",
    "ancestors": [
      {"term_id": 1, "name": "Head Office"},
      {"term_id": 5, "name": "Regional Office"}
    ],
    "depth": 2
  }
}
```

#### GET /api/branches/:id/descendants
**Purpose:** Get all descendant branch IDs (including the branch itself)
**Authentication:** Required
**Use Case:** Filter users/courses by branch and all sub-branches
**Response:**
```json
{
  "success": true,
  "data": {
    "branchId": 1,
    "descendantIds": [1, 5, 12, 15, 20],
    "count": 5
  }
}
```

---

### 5. Report Endpoints

#### GET /api/reports/progress
**Purpose:** Get progress report data for all users and courses
**Authentication:** Required
**Query Parameters:**
- `page` (optional): Page number
- `limit` (optional): Items per page
- `userId` (optional): Filter by user
- `courseId` (optional): Filter by course
- `branchId` (optional): Filter by branch
- `status` (optional): Filter by status (completed, in_progress, registered, failed)

**Response:**
```json
{
  "success": true,
  "data": {
    "records": [
      {
        "user_id": 123,
        "user_name": "John Doe",
        "course_id": 789,
        "course_name": "Fire Safety",
        "status": "completed",
        "score": 85,
        "progress": 100,
        "completed_on": "2026-01-10",
        "branch": "Head Office"
      }
    ],
    "pagination": {
      "total": 500,
      "page": 1,
      "limit": 50
    }
  }
}
```

#### GET /api/reports/certificates
**Purpose:** Get certificate report with expiry tracking
**Authentication:** Required
**Query Parameters:**
- `page`, `limit`: Pagination
- `userId`, `courseId`, `branchId`: Filters
- `expiryStatus`: Filter by expiry (expired, expiring_soon, valid)

**Response:**
```json
{
  "success": true,
  "data": {
    "records": [
      {
        "user_id": 123,
        "user_name": "John Doe",
        "course_id": 789,
        "course_name": "Fire Safety",
        "certificate_id": "CERT-2024-001",
        "awarded": "2024-01-10",
        "expires": "2025-01-10",
        "days_until_expiry": 45,
        "status": "expiring_soon"
      }
    ],
    "pagination": {...}
  }
}
```

#### GET /api/reports/tlm
**Purpose:** Get TLM report data
**Authentication:** Required
**Use Case:** Generate color-coded Excel reports

---

### 6. Certificate Endpoints

#### POST /api/certificates/generate
**Purpose:** Generate a new certificate PDF
**Authentication:** Required
**Request Body:**
```json
{
  "userId": 123,
  "courseId": 789,
  "score": 85
}
```
**Response:**
```json
{
  "success": true,
  "message": "Certificate generated successfully",
  "data": {
    "userId": 123,
    "courseId": 789,
    "filePath": "/certificates/789/123/1705132800/certificate.pdf"
  }
}
```

#### POST /api/certificates/regenerate
**Purpose:** Regenerate an existing certificate
**Authentication:** Required
**Request Body:**
```json
{
  "userId": 123,
  "courseId": 789
}
```

#### POST /api/certificates/batch-generate
**Purpose:** Generate certificates for all users in a course
**Authentication:** Required
**Request Body:**
```json
{
  "courseId": 789,
  "batchSize": 10
}
```

#### GET /api/certificates/download/:userId/:courseId
**Purpose:** Download a certificate PDF file
**Authentication:** Required
**Response:** PDF file download

#### GET /api/certificates/view/:userId/:courseId
**Purpose:** View certificate PDF in browser
**Authentication:** Required
**Response:** PDF displayed inline

#### GET /api/certificates/status/:userId/:courseId
**Purpose:** Check if certificate PDF exists
**Authentication:** Required
**Response:**
```json
{
  "success": true,
  "data": {
    "exists": true,
    "filePath": "/certificates/789/123/1705132800/certificate.pdf",
    "generatedAt": "2026-01-10T14:30:00Z"
  }
}
```

#### POST /api/certificates/bulk-download
**Purpose:** Download multiple certificates as a ZIP file
**Authentication:** Required
**Request Body:**
```json
{
  "certificates": [
    {"userId": 123, "courseId": 789},
    {"userId": 124, "courseId": 789},
    {"userId": 125, "courseId": 790}
  ]
}
```
**Response:** ZIP file download
**Limits:** Maximum 100 certificates per request

---

### 7. Synchronization Endpoints (Admin Only)

#### GET /api/sync/status
**Purpose:** Get current sync status and configuration
**Authentication:** Required (Admin)
**Response:**
```json
{
  "success": true,
  "data": {
    "caretutorApiUrl": "https://pathway.caretutor.org/API/v1.0/",
    "apiKeyConfigured": true,
    "lastSync": {
      "full": "2026-01-13T00:00:00Z",
      "quick": "2026-01-13T04:00:00Z"
    },
    "schedule": {
      "fullSync": "Daily at midnight",
      "quickSync": "Every 4 hours",
      "pdfGeneration": "Every 6 hours"
    }
  }
}
```

#### POST /api/sync/full
**Purpose:** Trigger a full sync from CareTutor API
**Authentication:** Required (Admin)
**Use Case:** Manual sync of all data (users, courses, branches, status, certificates)
**Response:**
```json
{
  "success": true,
  "message": "Full sync completed",
  "results": {
    "users": {"synced": 150, "errors": 0},
    "courses": {"synced": 45, "errors": 0},
    "branches": {"synced": 20, "errors": 0},
    "courseStatus": {"synced": 500, "errors": 0},
    "certificates": {"synced": 200, "errors": 0}
  },
  "duration": "12.5s"
}
```

#### POST /api/sync/users
**Purpose:** Sync only users from CareTutor API
**Authentication:** Required (Admin)

#### POST /api/sync/courses
**Purpose:** Sync only courses and branches
**Authentication:** Required (Admin)

#### POST /api/sync/course-status
**Purpose:** Sync only course completion status
**Authentication:** Required (Admin)

#### POST /api/sync/certificates
**Purpose:** Sync only certificate data
**Authentication:** Required (Admin)

#### POST /api/sync/certificates-full
**Purpose:** Sync certificate data AND generate PDFs
**Authentication:** Required (Admin)
**Request Body:** (optional)
```json
{
  "batchSize": 10,
  "force": false
}
```

#### GET /api/sync/generate-pdfs/status
**Purpose:** Get status of PDF generation
**Authentication:** Required (Admin)

#### POST /api/sync/generate-pdfs
**Purpose:** Generate PDFs for certificates without files
**Authentication:** Required (Admin)
**Request Body:** (optional)
```json
{
  "dryRun": false,
  "force": false,
  "batchSize": 10,
  "courseId": 789
}
```

---

### 8. Webhook Endpoints (Called by CareTutor)

#### POST /api/webhooks/course-status
**Purpose:** Receive course completion updates from CareTutor platform
**Authentication:** Basic Auth (username: tltm, password: provided)
**Request Body:**
```json
{
  "user_id": 123,
  "course_id": 789,
  "status": "completed",
  "score": 85,
  "progress": 100,
  "is_completed": 1,
  "to_timestamp": "2026-01-13 14:30:00"
}
```
**Response:**
```json
{
  "success": true,
  "message": "Course status updated"
}
```

#### POST /api/webhooks/certificate
**Purpose:** Receive certificate issued notifications
**Authentication:** Basic Auth
**Request Body:**
```json
{
  "user_id": 123,
  "course_id": 789,
  "certificate_id": "CERT-2024-001",
  "serial_number": "SN12345678",
  "awarded": "2026-01-13",
  "expires": "2027-01-13"
}
```

---

### 9. Course Group Endpoints

#### GET /api/course-groups
**Purpose:** Get all course groups
**Authentication:** Required

#### GET /api/course-groups/:id
**Purpose:** Get single course group
**Authentication:** Required

---

### 10. Health Check Endpoint

#### GET /health
**Purpose:** Check if the API server is running
**Authentication:** None (public)
**Response:**
```json
{
  "status": "ok",
  "timestamp": "2026-01-13T14:30:00Z"
}
```

---

## 🔐 Authentication System

### JWT Token-Based Authentication

**Login Process:**
1. Admin sends credentials to `POST /api/auth/login`
2. Server validates and returns JWT token
3. Client stores token (localStorage/cookie)
4. Client includes token in all subsequent requests:
   ```
   Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
   ```

**Token Expiry:** 7 days (configurable)

**Admin Account Creation:**
```bash
cd backend
node scripts/create-admin.js email@example.com password123 "Admin Name"
```

---

## 🔄 Data Synchronization Architecture

### Primary Method: Webhooks (Real-time)
- CareTutor platform sends POST requests when events occur
- Instant updates for course completions and certificates
- More efficient than polling

### Backup Method: Scheduled API Sync
- **Full Sync:** Daily at midnight (all data)
- **Quick Sync:** Every 4 hours (status + certificates)
- **PDF Generation:** Every 6 hours (missing PDFs)

### Data Flow
```
CareTutor Platform
    ├── Webhooks (Primary) → Node.js Server → Local MySQL
    └── REST API (Backup) → Node.js Server → Local MySQL
```

---

## 📊 Excel Export Features

### Progress Report Export
- **File Format:** .xlsx with colored cells
- **Color Coding:**
  - 🟢 Green: Completed
  - 🔵 Blue: Registered
  - 🟠 Orange: In Progress
  - 🔴 Red: Failed
- **Features:** Frozen headers, white text on colors

### Certificate Report Export
- **File Format:** .xlsx with colored cells
- **Color Coding (Expiry-based):**
  - 🟢 Green: >60 days until expiry
  - 🟠 Orange: ≤60 days until expiry
  - 🔴 Red: Expired
- **Features:** Days until expiry calculation, frozen columns

---

## 📁 Certificate Management

### PDF Generation
- **Technology:** Puppeteer (Headless Chrome)
- **Templates:** Handlebars (.hbs files)
- **Storage:** `uploads/certificates/{courseId}/{userId}/{timestamp}/`
- **Automatic:** Triggered by webhooks or scheduled job

### Certificate Download Options
1. **Individual:** Download single PDF
2. **View:** Open in browser
3. **Bulk ZIP:** Download multiple certificates as ZIP (max 100)

---

## 📝 Logging System

### Log Files
- **Location:** `backend/logs/`
- **Rotation:** Daily
- **Types:**
  - `app-YYYY-MM-DD.log` - All logs
  - `error-YYYY-MM-DD.log` - Errors only
- **Retention:**
  - Application logs: 14 days
  - Error logs: 30 days

### What's Logged
- HTTP requests (method, URL, status, duration)
- Authentication events (login/logout)
- Sync operations (start/success/failure)
- Certificate operations (generation/download)
- Webhook events (received/processed)
- Errors (stack traces)

---

## 📈 Migration Comparison: PHP vs Node.js

### What Was Migrated Successfully ✅

| Old PHP System | New Node.js System |
|----------------|-------------------|
| WordPress user table | Local users table with meta |
| WordPress posts (courses) | Local courses table with meta |
| WordPress taxonomy (branches) | Local terms/taxonomy tables |
| PHP DOMPDF library | Puppeteer (better quality) |
| WordPress cron jobs | node-cron (more reliable) |
| phpass password hashing | bcrypt (more secure) |
| Manual Excel export | Automated with colors (ExcelJS) |
| Unused webhook endpoints | Active webhook integration |

### Key Improvements

1. **Performance:** Optimized queries with indexes, caching
2. **Real-time:** Webhook-first architecture
3. **Modern Tech:** React UI, JWT auth, RESTful API
4. **Better Reporting:** Color-coded Excel exports
5. **Certificate Quality:** Puppeteer generates higher quality PDFs
6. **Logging:** Comprehensive Winston logging system
7. **Scalability:** Independent from WordPress

---

## 🎯 Success Metrics

### API Endpoints: 40+ endpoints ready
- Authentication: 3 endpoints ✅
- Users: 5 endpoints ✅
- Courses: 6 endpoints ✅
- Branches: 7 endpoints ✅
- Reports: 3 endpoints ✅
- Certificates: 7 endpoints ✅
- Sync: 9 endpoints ✅
- Webhooks: 2 endpoints ✅
- Groups: 2 endpoints ✅
- Health: 1 endpoint ✅

### Code Quality
- Error handling: Comprehensive ✅
- Logging: Winston with rotation ✅
- Validation: Input sanitization ✅
- Security: JWT + Basic Auth ✅
- Documentation: Complete ✅

