---
title: "Worklog Week 6"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives

- Deploy the entire application to AWS infrastructure
- Configure CI/CD to automate the deployment process

### Tasks to Complete This Week

| Day | Task | Start Date | End Date | Resources |
| --- | ---- | ---------- | -------- | --------- |
| Mon | - Deploy Backend to EC2: install Node.js, PM2, clone repo <br> - Configure environment variables (.env) for production <br> - Verify Backend is running via public IP | 20/07/2026 | 20/07/2026 | |
| Tue | - Build Frontend with Vite: `npm run build` <br> - Upload build output to S3 bucket <br> - Configure S3 static website hosting | 21/07/2026 | 21/07/2026 | |
| Wed | - Set up CloudFront distribution pointing to S3 bucket <br> - Configure CORS between Frontend (CloudFront) and Backend (EC2) <br> - Verify full application running in production environment | 22/07/2026 | 22/07/2026 | |
| Thu | - Configure DynamoDB on AWS (replacing local) <br> - Run setup_dynamodb.sh and seed_sample_data.sh on production <br> - Verify Backend → DynamoDB AWS connection | 23/07/2026 | 23/07/2026 | |
| Fri | - Set up basic CI/CD with GitHub Actions: auto-deploy on code push <br> - End-to-end testing: login, view courses, take quiz, submit assignment <br> - Log and fix any production issues | 24/07/2026 | 24/07/2026 | |

### Week 6 Results

- LMS application fully running on AWS: Frontend via CloudFront, Backend on EC2, data on DynamoDB
- CI/CD pipeline operational, auto-deploying on code changes
- All features functioning stably in production environment
