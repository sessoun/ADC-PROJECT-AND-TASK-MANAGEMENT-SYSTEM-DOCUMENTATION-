
## User Roles and Permissions

**Description:** Defines the roles in the system (Admin, Team Manager, Project Member) and their permissions, actions, and typical workflows. This ensures role-based access control and clear responsibilities.

### Roles Overview
- **Admin:** System-wide managers with full access to create/manage projects, users, and settings.
- **Team Manager (Project Overseer):** Oversees specific projects, manages tasks and team members within their projects.
- **Project Member (Staff):** Individual contributors who work on assigned tasks.

### Admin Actions and Flow
**Permissions:** Full system access, including user management, project creation, and global settings.
- **Typical Flow:**
  1. Log in as Admin.
  2. Dashboard: View all projects, users, and system stats.
  3. Create/Edit Projects: Add new projects, assign managers.
  4. Manage Users: Add/remove users, assign roles.
  5. Monitor: View reports on project progress, deadlines.
- **Key Actions:**
  - Create/Delete Projects.
  - Assign/Remove Project Managers.
  - Reset user passwords, manage accounts*.
  - Access all notifications and comments.
  - Archive projects system-wide.

### Team Manager Actions and Flow
**Permissions:** Manage assigned projects, create/assign tasks, oversee team progress.
- **Typical Flow:**
  1. Log in as Staff/Team member.
  2. Dashboard: View assigned projects and tasks.
  3. Create Tasks: Under projects, assign to staff.
  4. Monitor Progress: Update task statuses, view comments.
  5. Communicate: Add comments, send notifications.
- **Key Actions:**
  - Create/Edit/Delete Tasks in their projects.
  - Assign/Reassign Tasks to project members.
  - View/Edit Project details (name, deadline).
  - Approve task updates or reassignments.
  - Receive notifications for project/team changes.

### Project Member Actions and Flow
**Permissions:** View and update assigned tasks, participate in discussions.
- **Typical Flow:**
  1. Log in as Project Member.
  2. Dashboard: View assigned tasks and projects.
  3. Update Tasks: Change status, add comments, attach files.
  4. Collaborate: Reply to comments, mention team members.
  5. Track Progress: View deadlines, subtasks.
- **Key Actions:**
  - Update task status (To Do → In Progress → Done).
  - Edit task details (if allowed by manager).
  - Add comments and attachments to tasks.
  - View project overviews and team notifications.
  - Request reassignments or extensions (via comments).

### Notes
- Roles are assigned during signup or by Admins.
- Permissions are enforced at the UI and API levels.
- Flows can overlap (e.g., Managers can also act as Members on tasks)*.



