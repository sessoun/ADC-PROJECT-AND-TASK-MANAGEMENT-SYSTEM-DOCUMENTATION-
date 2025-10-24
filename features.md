## Authentication

### Overview
The authentication feature allows users to securely sign up, log in, log out, and reset their passwords. It ensures that only authorized users can access protected pages such as projects, tasks, comments, and notifications.

### User Stories
- As a new user, I want to sign up so that I can be added to a project then be assigned a task.  
- As a returning user, I want to log in so that I can access projects I have been added to and the tasks available for me.  
- As a user, I want to reset my password so that I can recover access if I forget it.  
- As an admin, I want to manage user accounts so that I can control who has access to the system.  

### User Flow
1. The user opens the application and is directed to the login page.
2. If the user does not have an account, they click "Sign Up" to register.
3. The system verifies the user's details and creates a new account.
4. Upon successful login, the user is redirected to the dashboard.
5. If the user forgets their password, they click "Forgot Password".
6. The system sends a password reset link to the user's registered email.
7. The user opens the link, enters a new password, and confirms it.
8. When the user clicks "Logout", their session is ended, and they are redirected to the login page.
### 

### Data / Model
| Field | Type | Description |
|-------|------|-------------|
| username | String | Unique identifier for each user |
| email | String | Used for user communication and password recovery |
| password | String | Encrypted password for secure login |
| reset_token | String | Temporary token for verifying password reset requests |
| date_joined | DateTime | Records when the user registered |
| last_login | DateTime | Records the user's most recent login |

### Notes
- Passwords must be hashed before storage for security.
- The password reset token should expire after a short period (e.g., 15–30 minutes).
- Only authenticated users can access other features like projects, tasks, comments, and notifications.



## Project
**Description:** Projects are the top-level containers for tasks. Admins can create and manage projects to organize work, assign managers, and track deadlines.

#### Sub-Features and Details
1. **Create Project**
   - **User Story:** As an admin, I want to create a new project so I can organize work and assign staff.
   - **Acceptance Criteria:**
     - Project must include: name, description, deadline, and project manager (from staff list).
     - Form validation: Name and deadline required; deadline must be in the future.
     - Project is created and visible in the dashboard.
   - **Priority:** High (core functionality).
   - **Status:** Pending (build after Authentication).

2. **Edit Project**
   - **User Story:** As an admin, I want to update project details so I can keep information current.
   - **Acceptance Criteria:**
     - Editable fields: description, deadline, overseer (only by admin).
     - Changes trigger notifications to the team.
     - Audit log: Track changes.
   - **Priority:** Medium.
   - **Status:** Pending.

3. **Assign Project Overseer**
   - **User Story:** As an admin, I want to assign an overseer to a project so they can manage tasks and staff.
   - **Acceptance Criteria:**
     - Dropdown of eligible staff.
     - Overseer gets notification and permissions to manage tasks under the project.
     - Only admins can assign; overseer can be reassigned.
   - **Priority:** High.
   - **Status:** Pending.

4. **Set and View Deadline**
   - **User Story:** As an admin, I want to set and view project deadlines so I can prioritize work.
   - **Acceptance Criteria:**
     - Deadline field with date picker.
     - Visual indicators: Color-coded priority (e.g., red for overdue).
     - Dashboard shows deadline status for all projects.
   - **Priority:** High.
   - **Status:** Pending.

5. **View Project Details**
   - **User Story:** As a staff member, I want to view project details so I can understand the scope and my role.
   - **Acceptance Criteria:**
     - Page shows: name, description, deadline, overseer, list of tasks, and progress summary.
     - Access control: Team members only.
   - **Priority:** Medium.
   - **Status:** Pending.

6. **Archive/Close Project**
   - **User Story:** As a manager, I want to archive completed projects so the dashboard stays clean.
   - **Acceptance Criteria:**
     - Mark project as "Archived" or "Closed".
     - Archived projects are hidden from active views but searchable.
     - Confirmation required; notifications sent.
   - **Priority:** Low.
   - **Status:** Planned.

## Task
**Description:** Tasks are the core work items under a project. Users (staff or managers) can create, assign, track, and complete tasks to monitor progress. Tasks should support basic CRUD operations, status tracking, and integration with projects, comments, and notifications.

#### Sub-Features and Details
1. **Create Task**
   - **User Story:** As a project manager, I want to create a new task under a project so I can break down work and assign responsibilities.
   - **Acceptance Criteria:**
     - Task must include: title, description, assignee (from staff list), due date, priority (Low/Medium/High), and status (To Do/In Progress/Done).
     - Task must be linked to a specific project.
     - Form validation: Title required, due date must be in the future.
   - **Priority:** High (core functionality).
   - **Status:** Pending (build after Project creation).

2. **Edit Task**
   - **User Story:** As a staff member, I want to update task details (e.g., description or due date) so I can keep information current.
   - **Acceptance Criteria:**
     - Editable fields: description, due date, priority, assignee (only by project manager or assignee).
     - Changes trigger a notification to the assignee and project manager.
     - Audit log: Track who made changes and when.
   - **Priority:** Medium.
   - **Status:** Pending.

3. **Assign Task**
   - **User Story:** As a project manager, I want to assign tasks to staff so work is distributed fairly.
   - **Acceptance Criteria:**
     - Dropdown of staff under the project (from StaffID).
     - Assignee gets a notification email/SMS.
     - Only project manager can assign; assignee can reassign with approval.
   - **Priority:** High.
   - **Status:** Pending.

4. **Track Task Status and Progress**
   - **User Story:** As a manager, I want to see task status and progress so I can monitor project health.
   - **Acceptance Criteria:**
     - Status options: To Do, In Progress, Done, Blocked.
     - Progress bar or percentage (based on subtasks or time logged).
     - Dashboard view: Filter tasks by status, assignee, or project.
     - Automatic notifications on status changes.
   - **Priority:** High.
   - **Status:** Pending.

5. **Subtasks**
   - **User Story:** As a staff member, I want to break tasks into subtasks so I can manage complex work.
   - **Acceptance Criteria:**
     - Add/remove subtasks under a main task.
     - Each subtask has its own status and due date.
     - Main task status updates based on subtasks (e.g., Done when all subtasks are Done).
   - **Priority:** Medium.
   - **Status:** Planned (after core task features).

6. **Comments on Tasks**
   - **User Story:** As a user(manager/asignee), I want to add comments to tasks so I can discuss progress or issues.
   - **Acceptance Criteria:**
     - Comments are threaded and visible to project team.
     - Mentions (@staff) trigger notifications.
     - Integrates with the Comment feature (from your overview).
   - **Priority:** Medium.
   - **Status:** Pending (depends on Comment feature).

7. **Attachments**
   - **User Story:** As a team member, I want to attach files (docs, images) to tasks so I can share relevant materials.
   - **Acceptance Criteria:**
     - Support common formats (PDF, images, docs).
     - File size limit (e.g., 10MB).
     - Secure storage and access control.
   - **Priority:** Low.
   - **Status:** Planned.

8. **Time Tracking**
   - **User Story:** As a manager, I want to track time spent on tasks so I can estimate effort and costs.
   - **Acceptance Criteria:**
     - Log start/end times or manual entry.
     - Reports: Total time per task/project.
     - Optional: Integrate with deadlines for alerts.
   - **Priority:** Low.
   - **Status:** Planned.

9. **Dependencies**
   - **User Story:** As a project manager, I want to set task dependencies so work flows logically.
   - **Acceptance Criteria:**
     - Link tasks (e.g., Task B can't start until Task A is Done).
     - Visual dependency graph in project view.
     - Alerts if dependencies are violated.
   - **Priority:** Medium.
   - **Status:** Planned.

## Comment
**Description:** Comments enable threaded discussions on tasks and projects, allowing users to collaborate, ask questions, and provide feedback. Comments integrate with notifications to alert mentioned users.

#### Sub-Features and Details
1. **Add Comment**
   - **User Story:** As a user, I want to add a comment to a task or project so I can share updates or ask questions.
   - **Acceptance Criteria:**
     - Text field for comment content.
     - Option to mention users (@username) for notifications.
     - Comments are saved and displayed in chronological order.
   - **Priority:** Medium.
   - **Status:** Pending (build after Task).

2. **View Comments**
   - **User Story:** As a team member, I want to view all comments on a task/project so I can follow discussions.
   - **Acceptance Criteria:**
     - Threaded view with replies.
     - Pagination for long threads.
     - Access control: Only project team members.
   - **Priority:** Medium.
   - **Status:** Pending.

3. **Edit/Delete Comment**
   - **User Story:** As a comment author, I want to edit or delete my comments so I can correct mistakes.
   - **Acceptance Criteria:**
     - Edit within a time limit (e.g., 15 minutes).
     - Delete option with confirmation.
     - Audit log for changes.
   - **Priority:** Low.
   - **Status:** Planned.

4. **Mentions and Notifications**
   - **User Story:** As a mentioned user, I want to be notified when someone mentions me so I can respond quickly.
   - **Acceptance Criteria:**
     - @mentions trigger in-app and email notifications.
     - Integrates with Notification feature.
   - **Priority:** Medium.
   - **Status:** Pending (depends on Notification).

## Notification
**Description:** Notifications inform users about important events like task assignments, project updates, comments, and deadlines. They support multiple channels (in-app, email, SMS) for timely communication.

#### Sub-Features and Details
1. **In-App Notifications**
   - **User Story:** As a user, I want to see notifications in the app so I can stay updated without checking email.
   - **Acceptance Criteria:**
     - Bell icon with unread count.
     - List of notifications with timestamps and links to relevant pages.
     - Mark as read/unread.
   - **Priority:** High.
   - **Status:** Pending.

2. **Email/SMS Notifications**
   - **User Story:** As a user, I want to receive email or SMS alerts for critical updates so I don't miss them.
   - **Acceptance Criteria:**
     - Configurable preferences (email, SMS, or both).
     - Templates for different event types (e.g., task assigned, deadline approaching).
     - Opt-out option.
   - **Priority:** Medium.
   - **Status:** Pending.

3. **Notification Settings**
   - **User Story:** As a user, I want to customize my notification preferences so I control what I receive.
   - **Acceptance Criteria:**
     - Settings page for enabling/disabling types (tasks, comments, projects).
     - Frequency options (immediate, daily digest).
     - Save preferences per user.
   - **Priority:** Low.
   - **Status:** Planned.

4. **Event Triggers**
   - **User Story:** As the system, I want to trigger notifications automatically for key events so users are informed.
   - **Acceptance Criteria:**
     - Triggers: Task assigned, comment added, deadline near, project updated.
     - Queue system for reliable delivery.
   - **Priority:** High.
   - **Status:** Pending.



