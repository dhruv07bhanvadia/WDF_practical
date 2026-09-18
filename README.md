# ITUE203: Web Development Frameworks
## Semester 3 - Faculty of Technology and Engineering
### Project: StudentHub Portal (Completed till Practical 5)

---

## 📌 Practical 1: Project Initiation, Requirement Analysis, Sitemap, Wireframe, and GitHub Setup

### 1. Problem Definition & Scope
**StudentHub** is a central digital campus web portal designed to streamline communication, course management, student profiles, and administrative tracking for university students, faculty members, and administrators.

#### User Roles & Permissions:
1. **Student**: Access course resources, view academic progress (grades), check announcements, and update profile details.
2. **Faculty**: Manage course syllabus and publish notices/announcements.
3. **Administrator**: Oversee platform user accounts and monitor system performance.

---

### 2. Official StudentHub Sitemap Architecture

```text
                                 [ ROOT: StudentHub Home ]
                                        index.html
                                             │
      ┌──────────────────┬───────────────────┼───────────────────┬──────────────────┐
      │                  │                   │                   │                  │
  [ About Us ]    [ Contact Us ]      [ User Auth Gate ]    [ Auth Gate ]     [ Student Portal ]
  about.html       contact.html          login.html         register.html     pages/dashboard.html
                                                                                    │
                                                                   ┌────────┬───────┼───────┬────────┐
                                                                   │        │       │       │        │
                                                              [Profile] [Courses] [Grades] [Announcements]
