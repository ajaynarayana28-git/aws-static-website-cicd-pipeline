# AWS Static Website Hosting with CI/CD Pipeline Automation

## Project Overview

## Project Overview

Designed and implemented a fully automated AWS CI/CD pipeline for static website hosting using GitHub, CodePipeline, CodeBuild, Amazon S3, and CloudFront. The solution automates code deployment, improves delivery efficiency, and provides fast, globally distributed content through AWS Cloud services.


---

## Architecture Diagram


![AWS Architecture](Architecture-Diagram/AWS-Static-Website-CICD-Architecture.png)


---

## AWS Services Used

* Amazon S3 — Static website hosting
* AWS CodeCommit — Source code repository
* AWS CodeBuild — Automated build service
* AWS CodePipeline — CI/CD pipeline orchestration
* AWS IAM — Roles and permissions


---

## How It Works

```
Developer pushes code to CodeCommit
            ↓
CodePipeline detects the change
            ↓
CodeBuild builds and validates files
            ↓
CodePipeline deploys to S3 automatically
            ↓
CloudFront invalidation clears cache
            ↓
Website updated globally — Zero manual work!
```

---

## Project Architecture Workflow

1. Developer updates website code locally
2. Code pushed to AWS CodeCommit repository
3. CodePipeline automatically detects the change
4. CodeBuild runs buildspec.yml instructions
5. Website files deployed to S3 bucket
6. CloudFront cache invalidated automatically
7. Users worldwide see updated website instantly

---

## Key Features

* Fully Automated CI/CD Pipeline
* Zero Manual Deployment
* Global Content Delivery via CloudFront
* Automatic Cache Invalidation
* S3 Static Website Hosting
* IAM Role Based Security
* CloudWatch Pipeline Monitoring

---

## Project Structure

```
aws-static-website-cicd/
├── Architecture-Diagram/
├── Screenshots/
├── index.html
├── buildspec.yml
├── Documentation/
└── README.md
```

---

## Implementation Summary

### S3 Setup
* Created S3 bucket for static website hosting
* Enabled public access for website
* Configured bucket policy for CloudFront access

### CloudFront Setup
* Created CloudFront distribution
* Connected to S3 bucket origin
* Configured cache behaviors
* Enabled HTTPS

### CI/CD Pipeline Setup
* Created CodeCommit repository
* Configured CodeBuild project with buildspec.yml
* Created CodePipeline with 3 stages:
  - Source — CodeCommit
  - Build — CodeBuild
  - Deploy — S3

### IAM Configuration
* Created IAM roles for CodeBuild and CodePipeline
* Configured least privilege permissions
* Attached necessary policies

## CloudFront Content Delivery Network (CDN)

To improve website performance and global accessibility, Amazon CloudFront was integrated with the S3 static website.

### Implementation Steps

* Created a CloudFront Distribution
* Selected the S3 bucket as the origin
* Disabled AWS WAF for this project
* Configured Default Root Object as `index.html`
* Enabled global content delivery through CloudFront edge locations
* Verified successful website access using the CloudFront domain URL

### Outcome

The website is now delivered through CloudFront, providing faster content delivery, lower latency, and improved user experience worldwide.



## Testing and Validation

* ✅ Pipeline triggered automatically on code push
* ✅ CodeBuild completed successfully
* ✅ Website deployed to S3
* ✅ CloudFront serving content globally
* ✅ Cache invalidation working correctly
* ✅ Website accessible via CloudFront URL

---

## Learning Outcomes

* AWS CI/CD Pipeline implementation
* S3 Static Website Hosting
* CloudFront CDN configuration
* CodeCommit, CodeBuild, CodePipeline integration
* IAM Role and Policy management
* Automated deployment workflows
* DevOps best practices on AWS

---

## Conclusion

This project demonstrates a real-world CI/CD pipeline implementation on AWS that eliminates manual deployment effort. The automated pipeline ensures faster, reliable, and consistent website deployments using native AWS DevOps services.
