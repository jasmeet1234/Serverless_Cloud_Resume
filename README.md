
# Serverless Cloud Resume

A fully serverless, cloud-based resume website built as part of the Cloud Resume Challenge. Hosted at [https://resume.jasmeetsingh.site/](https://resume.jasmeetsingh.site/), this project leverages AWS services to deliver a secure, scalable, and high-performance resume experience.

## Overview

This project demonstrates a modern, serverless approach to hosting a personal resume website using AWS. Key components include:

- **Amazon S3** for static file hosting
- **CloudFront** as a global CDN for secure content delivery
- **Route 53 / Namecheap** for DNS management
- **AWS Certificate Manager (ACM)** for SSL/TLS provisioning
- **AWS Lambda** for serverless computing (optional dynamic features)
- **Amazon DynamoDB** for lightweight, scalable data storage

## Architecture & Key Components

### Amazon S3
- **Bucket Types**: Utilized General-Purpose Buckets for broad feature support and cost-effectiveness.
- **Best Practices**: Disabled ACLs in favor of bucket policies and enabled versioning for data integrity.

### CloudFront
- **Configuration**: Set up using the S3 bucket's REST API endpoint to serve content securely over HTTPS.
- **Security & Performance**: Enforced HTTPS through Viewer Protocol Policies, applied optimized caching, and followed industry best practices.

### DNS & SSL
- **DNS Management**: Configured with Route 53 and Namecheap by correctly setting NS and SOA records.
- **SSL Certification**: Provisioned via ACM (in the `us-east-1` region) to secure custom domains and enable HTTPS.

### AWS Lambda & DynamoDB
- **Lambda**: Deployed functions with the necessary execution roles to handle serverless tasks.
- **DynamoDB**: Employed for scalable data tracking (e.g., resume views or user interactions) with a flexible schema.

## Deployment Process

1. **S3 Bucket Creation & File Upload**
   - Create a unique, public S3 bucket.
   - Upload static assets such as `index.html`, `styles.css`, etc.

2. **CloudFront Distribution Setup**
   - Configure CloudFront using the S3 bucket's REST endpoint.
   - Enforce HTTPS and set optimal caching and security settings.

3. **DNS Configuration**
   - Update DNS records (NS, SOA, CNAME) via Namecheap/Route 53.
   - Point your custom domain to the CloudFront distribution.

4. **SSL Certificate Provisioning**
   - Request an SSL certificate from ACM.
   - Validate the certificate via DNS (Route 53 integration recommended).

5. **Serverless Enhancements (Optional)**
   - Deploy Lambda functions with appropriate IAM roles.
   - Integrate DynamoDB for dynamic data tracking and scalability.

## Research Insights

The project was informed by a deep dive into:
- The nuances of Amazon S3 bucket types and best practices for static website hosting.
- Optimization techniques for CloudFront distributions to ensure HTTPS delivery.
- Detailed DNS setup and SSL certification processes.
- Serverless architecture using Lambda and DynamoDB for additional functionality.

## Live Demo

Experience the live resume here: [https://resume.jasmeetsingh.site/](https://resume.jasmeetsingh.site/)
