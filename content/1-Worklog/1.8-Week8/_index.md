---
title: "Worklog Week 8"
date: 2026-08-07
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

- Self-study and practice advanced AWS services: Lambda, API Gateway, ECS (Fargate), WAF
- Combine theory and practice through official AWS workshops/hands-on labs
- Understand when to use each service and how to combine them in a real-world architecture

### Tasks to Complete This Week

| Day | Task | Start Date | End Date | Resources |
| --- | ---- | ---------- | -------- | --------- |
| Mon | **Lambda Workshop - Optimizing EC2 Costs with Lambda** <br> - Follow the 7-step workshop: introduction → preparation → create tags for instances → create IAM role for Lambda → write Lambda function (Python) to auto start/stop EC2 on schedule → test results → clean up resources | August 3, 2026 | August 3, 2026 | [AWS Study Group - Lambda Workshop](https://000022.awsstudygroup.com/) |
| Tue | **API Gateway Workshop - Serverless Front-end with API Gateway** <br> - Follow the 5-step workshop: deploy front-end → configure API Gateway with Lambda + DynamoDB → test APIs via Postman → test APIs with front-end → clean up resources | August 4, 2026 | August 4, 2026 | [AWS Study Group - API Gateway Workshop](https://000135.awsstudygroup.com/) |
| Wed | **ECS Workshop - Deploy Applications on Amazon ECS** <br> - Follow the 10-step workshop: prepare environment → write Dockerfile, push to ECR → create ECS Cluster (Fargate) → create Task Definition → configure ALB → create ECS Service → test results → clean up resources | August 5, 2026 | August 5, 2026 | [AWS Study Group - ECS Workshop](https://000016.awsstudygroup.com/) |
| Thu | **AWS WAF Workshop - AWS Web Application Firewall** <br> - Follow the 4-step workshop: introduction to WAF → prepare environment → hands-on configure Web ACL, rule groups, IP set, rate limiting → clean up resources | August 6, 2026 | August 6, 2026 | [AWS Study Group - WAF Workshop](https://000026.awsstudygroup.com/) |
| Fri | **Applying & Comparing Services** <br> - Summarize knowledge of 4 services: strengths, weaknesses, suitable use cases <br> - Compare deployment models: Serverless (Lambda) vs Container (ECS) vs VM (EC2) – which to choose, when? | August 7, 2026 | August 7, 2026 | |

### Week 8 Results

- Completed 4 workshops: Lambda (auto start/stop EC2), API Gateway (serverless front-end + Lambda + DynamoDB), ECS (Docker → ECR → Fargate), WAF (Web ACL, rate limiting)
- Understood the differences between 3 deployment models – Serverless, Container, VM – and suitable use cases for each service
