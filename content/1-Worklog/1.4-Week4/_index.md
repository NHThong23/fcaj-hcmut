---
title: "Worklog Week 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives

- Begin Backend development: implement core APIs for the LMS project
- Set up DynamoDB local environment and connect it with the server

### Tasks to Complete This Week

| Day | Task | Start Date | End Date | Resources |
| --- | ---- | ---------- | -------- | --------- |
| Mon | - Clone repository, install dependencies <br> - Configure environment variables (.env) for MySQL and DynamoDB <br> - Run local server, test `/health` endpoint | July 6, 2026 | July 6, 2026 | |
| Tue | - Build login/register API with JWT authentication <br> - Create User model and auth middleware <br> - Test API with Postman: `POST /auth/login`, `POST /users` | July 7, 2026 | July 7, 2026 | |
| Wed | - Develop Classes & Courses APIs: GET, POST, PUT, DELETE <br> - Write Class & Course models, query DynamoDB with GSI <br> - Run `seed_sample_data.sh` to load sample data | July 8, 2026 | July 8, 2026 | |
| Thu | - Develop Schedules & Grades APIs <br> - Design StudentSchedule table schema <br> - Write controller and routes for timetable and grade viewing | July 9, 2026 | July 9, 2026 | |
| Fri | - Code review completed APIs, fix bugs and optimize <br> - Team meeting to check progress and plan for Week 5 | July 10, 2026 | July 10, 2026 | |

### Week 4 Results

- Backend running stably on local environment with DynamoDB and MySQL
- Completed foundational APIs: Auth, Users, Classes, Courses, Schedules, Grades
- Database populated with sample data ready for testing and Frontend development
