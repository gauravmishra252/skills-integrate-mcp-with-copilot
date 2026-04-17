# Feature Issues for Mergington High School Activities API

Copy the issues below into your GitHub repository. Create each as a new GitHub issue.

---

## HIGH PRIORITY

### Issue 1: User Authentication & Authorization System
**Title:** Implement user authentication and role-based access control

**Description:**
Add authentication system with multiple user roles (admin, teacher, student, guest). Users should be able to log in with email/password and have different permission levels based on their role.

**Acceptance Criteria:**
- [ ] JWT or session-based authentication implemented
- [ ] Three user roles defined: Admin, Teacher, Student
- [ ] Login endpoint returns authentication token
- [ ] Protected endpoints require valid authentication
- [ ] Role-based access control enforced
- [ ] Password hashing implemented (bcrypt or similar)

**Labels:** authentication, backend, enhancement

---

### Issue 2: Database Integration & Persistence
**Title:** Replace in-memory storage with persistent database

**Description:**
Currently, all data is stored in memory and lost on server restart. Implement database persistence using SQLAlchemy and a relational database (SQLite for dev, PostgreSQL for production).

**Acceptance Criteria:**
- [ ] SQLAlchemy ORM models created for Activities, Students, Signups
- [ ] Database migrations setup (Alembic)
- [ ] All existing endpoints work with database backend
- [ ] Data persists across server restarts
- [ ] Database schema documented

**Labels:** database, backend, enhancement

---

### Issue 3: Admin Dashboard with Statistics
**Title:** Create admin dashboard with activity analytics

**Description:**
Build an admin dashboard that shows key metrics like number of participants per activity, signup trends, capacity utilization, and other statistics.

**Acceptance Criteria:**
- [ ] Dashboard endpoint returns aggregated statistics
- [ ] Shows participant count per activity
- [ ] Shows capacity utilization percentages
- [ ] Shows signup trends over time
- [ ] Only accessible to admin users
- [ ] HTML dashboard page created

**Labels:** dashboard, admin, frontend, enhancement

---

### Issue 4: Email Notifications for Signups
**Title:** Send email notifications on signup/unregister events

**Description:**
Implement email notifications to send confirmations when students sign up or unregister from activities.

**Acceptance Criteria:**
- [ ] Email service integration (SMTP or SendGrid)
- [ ] Signup confirmation email sent automatically
- [ ] Unregister confirmation email sent automatically
- [ ] Email templates created
- [ ] Configurable email settings

**Labels:** notifications, email, backend, enhancement

---

## MEDIUM PRIORITY

### Issue 5: Activity Categories and Filtering
**Title:** Add activity categories and filtering capabilities

**Description:**
Categorize activities (Sports, Arts, Academic, etc.) and allow users to filter activities by category, schedule, or availability.

**Acceptance Criteria:**
- [ ] Activity model includes category field
- [ ] Categories endpoint returns all available categories
- [ ] Filter endpoint supports filtering by category
- [ ] Filter endpoint supports filtering by name/search
- [ ] Frontend updated to show categories

**Labels:** feature, backend, frontend, enhancement

---

### Issue 6: Activity Change History/Audit Trail
**Title:** Track and log all changes to activities

**Description:**
Log all modifications to activities including who made the change, when, and what changed (creation, capacity updates, schedule changes, etc.).

**Acceptance Criteria:**
- [ ] Audit log model created
- [ ] All activity modifications logged
- [ ] Logs include: timestamp, user, activity, change type, old value, new value
- [ ] Endpoint to retrieve audit logs for an activity
- [ ] Admin view to see all system changes

**Labels:** audit-trail, backend, admin, enhancement

---

### Issue 7: User Roles & Permissions Management
**Title:** Implement granular role-based permissions

**Description:**
Create a permission system where admins can define fine-grained permissions for each role (e.g., can_create_activity, can_edit_activity, can_view_participants).

**Acceptance Criteria:**
- [ ] Permission model created
- [ ] Role-permission associations defined
- [ ] Admin endpoint to assign/revoke permissions
- [ ] Permission checks enforced across all endpoints
- [ ] Default roles with preset permissions

**Labels:** permissions, rbac, backend, admin

---

### Issue 8: Activity Comments & Discussion
**Title:** Add comment system to activities

**Description:**
Allow students and teachers to leave comments on activities for discussions, questions, or coordination.

**Acceptance Criteria:**
- [ ] Comments model created
- [ ] POST endpoint to create comment
- [ ] GET endpoint to retrieve comments for activity
- [ ] DELETE endpoint to remove comments
- [ ] Comments include author, timestamp, content

**Labels:** feature, backend, frontend, enhancement

---

### Issue 9: Calendar View Implementation
**Title:** Add calendar view for activities

**Description:**
Implement a visual calendar display showing activities scheduled for each day, replacing the simple text schedule format.

**Acceptance Criteria:**
- [ ] Calendar endpoint returns activities organized by date
- [ ] Frontend displays calendar view (month/week/day)
- [ ] Click on date shows activities for that day
- [ ] Mobile-responsive calendar
- [ ] Color-coding for different activity types

**Labels:** feature, frontend, ui-ux, enhancement

---

### Issue 10: Admin Panel for Activity Management
**Title:** Create admin panel for managing activities and users

**Description:**
Build a comprehensive admin interface for creating, editing, and deleting activities, managing user accounts, and viewing system statistics.

**Acceptance Criteria:**
- [ ] Admin page to create new activities
- [ ] Admin page to edit existing activities
- [ ] Admin page to delete activities (with confirmation)
- [ ] Admin page to manage user accounts
- [ ] Admin page to view participant lists
- [ ] Restricted to admin users only

**Labels:** admin, frontend, feature, enhancement

---

## NICE TO HAVE

### Issue 11: iCalendar Feed Export
**Title:** Export activities as iCalendar format

**Description:**
Allow users to export their signed-up activities as an iCalendar feed that can be imported into external calendar applications (Google Calendar, Outlook, etc.).

**Acceptance Criteria:**
- [ ] Endpoint to generate iCal feed for user
- [ ] Proper iCalendar format (.ics)
- [ ] Compatible with Google Calendar, Outlook
- [ ] Include activity details (title, time, description, location)

**Labels:** integrations, feature, enhancement

---

### Issue 12: Multi-Language Support
**Title:** Implement internationalization (i18n)

**Description:**
Add support for multiple languages (English, Spanish, French, etc.) to make the application accessible to diverse user bases.

**Acceptance Criteria:**
- [ ] i18n framework integrated (gettext or similar)
- [ ] All UI strings extracted to translation files
- [ ] At least 2 languages supported
- [ ] Language selector in UI
- [ ] API returns localized responses

**Labels:** i18n, frontend, enhancement

---

### Issue 13: Dark Mode & Theme Support
**Title:** Add dark mode and theme customization

**Description:**
Implement dark mode and allow users to choose between different UI themes (light, dark, high contrast, etc.).

**Acceptance Criteria:**
- [ ] Dark mode CSS created
- [ ] Theme toggle in user settings
- [ ] Theme preference saved to database
- [ ] Smooth theme transition
- [ ] Applied to all pages

**Labels:** ui-ux, frontend, enhancement

---

### Issue 14: Activity Reminders & Notifications
**Title:** Send reminders before activity start times

**Description:**
Implement a notification system to send reminders to registered participants before activities start (24 hours, 1 hour, 15 minutes before).

**Acceptance Criteria:**
- [ ] Background job scheduler setup (Celery or APScheduler)
- [ ] Reminder configuration (time before event)
- [ ] Email reminders sent at specified times
- [ ] Optional SMS reminders
- [ ] User can disable reminders

**Labels:** notifications, feature, backend

---

### Issue 15: Data Export for Users
**Title:** Allow users to export their personal data

**Description:**
Implement GDPR-compliant data export feature that allows users to download all their personal data (signups, profile, activity history).

**Acceptance Criteria:**
- [ ] Endpoint to generate user data export
- [ ] Data exported in CSV/JSON format
- [ ] Includes all signups, profile info, timestamps
- [ ] Download as ZIP file
- [ ] Accessible only to the user

**Labels:** privacy, gdpr, feature, backend

---

### Issue 16: Mobile App (Optional)
**Title:** Create mobile-friendly responsive design

**Description:**
Optimize the frontend for mobile devices with responsive design and mobile-specific features.

**Acceptance Criteria:**
- [ ] All pages responsive on mobile
- [ ] Mobile navigation menu
- [ ] Touch-optimized buttons
- [ ] Mobile-optimized forms
- [ ] Tested on iOS and Android browsers

**Labels:** mobile, frontend, ui-ux, enhancement

---

### Issue 17: Student Search and Bulk Signup Management
**Title:** Add bulk user import and activity management

**Description:**
Allow admins to import student CSV files and perform bulk operations like assigning students to activities or updating their information.

**Acceptance Criteria:**
- [ ] CSV import endpoint for students
- [ ] Bulk activity assignment
- [ ] CSV export for participants
- [ ] Validation for import data
- [ ] Transaction rollback on errors

**Labels:** admin, bulk-operations, backend, feature

---

### Issue 18: Performance Tracking & Statistics
**Title:** Track student participation and engagement metrics

**Description:**
Collect and display student participation statistics including total signups, participation trends, most popular activities.

**Acceptance Criteria:**
- [ ] Participation metrics endpoint
- [ ] Student activity history
- [ ] Participation trends over time
- [ ] Most/least popular activities
- [ ] Student dashboard with their stats

**Labels:** analytics, feature, backend

---

### Issue 19: Help Desk & Support System
**Title:** Implement help desk for student support

**Description:**
Create a support ticket system for students to report issues or ask questions about activities.

**Acceptance Criteria:**
- [ ] Support ticket model created
- [ ] Endpoint to create support ticket
- [ ] Support tickets tracked with status
- [ ] Admin dashboard for tickets
- [ ] Email notifications for new tickets

**Labels:** support, feature, backend

---

### Issue 20: Activity Survey & Feedback
**Title:** Create survey system for activity feedback

**Description:**
Allow creation of surveys/polls for activities to gather feedback from participants about their experience.

**Acceptance Criteria:**
- [ ] Survey model with questions
- [ ] Poll/voting functionality
- [ ] Survey results aggregation
- [ ] Endpoint to retrieve survey results
- [ ] Survey templates for quick creation

**Labels:** feedback, feature, backend

---

## EPIC: Payment & Billing System (Future)
**Title:** Payment processing for paid activities

**Description:**
Add payment processing capabilities for activities that charge fees. This is a future epic that encompasses multiple related issues.

**Potential Issues:**
- [ ] Integrate Stripe payment processor
- [ ] Payment model and transaction logging
- [ ] Invoice generation
- [ ] Refund processing

**Labels:** payment, billing, epic

---

## Labels Reference
Use these labels when creating issues:
- `authentication` - Auth related
- `backend` - Backend/API work
- `frontend` - Frontend/UI work
- `database` - Database related
- `feature` - New feature
- `enhancement` - Improvement to existing feature
- `admin` - Admin-only features
- `mobile` - Mobile optimization
- `ui-ux` - User interface/experience
- `api` - API changes
- `bug` - Bug fix
- `documentation` - Docs updates
- `testing` - Test coverage
- `performance` - Performance optimization
- `security` - Security related
- `epic` - Epic/large project
- `help wanted` - Looking for contributors
