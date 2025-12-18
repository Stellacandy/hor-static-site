
Static Website Hosting on AWS (S3 + CloudFront)

Project Overview
This project demonstrates how to deploy a secure, scalable, and cost-effective static website using Amazon S3 for storage and Amazon CloudFront for global content delivery.

The solution eliminates the need for servers, reduces operational overhead, and improves performance by caching content at edge locations worldwide. The project is designed to showcase foundational cloud architecture skills, documentation quality, and project coordination capability.



Objectives
- Host a static website using Amazon S3
- Distribute content globally using Amazon CloudFront
- Enforce HTTPS for secure access
- Restrict direct public access to the S3 bucket
- Deliver a low-cost, highly available solution using AWS managed services



 Architecture Overview

### High-Level Flow
1. End users request the website via a browser
2. CloudFront receives the request and serves cached content if available
3. If content is not cached, CloudFront fetches it securely from the S3 bucket
4. S3 stores and returns static website files (HTML, CSS, JS, images)
5. Access is controlled so only CloudFront can read objects from S3


Architecture Diagram 

User
|
CloudFront (CDN)
|
Amazon S3 (Static Website Files)



Technologies Used
Amazon S3: Stores static website files |
Amazon CloudFront: Global content delivery and HTTPS enforcement 

No compute services, databases, or server-side frameworks were used.

Functional Requirements
- The system must host static web files (HTML, CSS, JS) in Amazon S3
- The website must be accessible through CloudFront
- All user traffic must be served over HTTPS
- The S3 bucket must not allow public access directly
- CloudFront must be the only service allowed to retrieve objects from S3



 Non-Functional Requirements
- Availability: High availability using AWS managed services  
- Scalability: Automatic scaling with no infrastructure management  
- Performance:Low latency via CloudFront edge caching  
- Security:Private S3 bucket with controlled access  
- Cost Efficiency: Operates within AWS free tier limits  


 Implementation Steps 
1. I Created a private Amazon S3 bucket called "hor-static-site"
2. Then I uploaded the objects which are the static website files to S3
3. I went to perpissions tab and created an S3 bucket policy
4. After creating the bucket policy, i navigated to CloudFront to create a distribution
5. I configured CloudFront to use S3 as its origin
7. Also restricted S3 bucket access to CloudFront only
8. The index.html file was set as the default root object
9. I tested the website access via CloudFront URL



Security Configuration
- S3 Block Public Access enabled
- CloudFront configured as the only allowed reader of S3 objects
- No public object ACLs used



Testing Strategy

Functional Tests:
Access CloudFront URL: Website loads successfully 
Load assets (CSS/JS/images): Assets load correctly 
Refresh page: Cached content loads faster 
Access S3 object directly  Access denied 



Security Tests
- Confirm S3 bucket is not publicly accessible
- Verify CloudFront serves content securely over HTTPS
- Validate that direct S3 URLs are blocked



Cost Estimate

Amazon S3: Free (within 5GB free tier) 
Amazon CloudFront: Free (within free tier usage plan) 
Total: $0 – $1/month



Risks and Mitigations
 Risk                                        Mitigation 
Misconfigured S3 permissions    |    Apply least-privilege bucket policy 
Cached outdated content         |    Use CloudFront cache invalidation 
Incorrect root object           |    Set index.html explicitly 




Deliverables
- Architecture diagram
- S3 bucket configuration
- CloudFront distribution
- Security configuration
- Test plan
- Cost estimate
- Documentation (this README)



Project Outcome
The project successfully delivers a secure, globally distributed static website using only AWS S3 and CloudFront. The solution is production-ready, cost-efficient, and requires minimal ongoing maintenance.


Skills Demonstrated
- Cloud architecture fundamentals
- Content delivery network (CDN) concepts
- Secure storage configuration
- Technical documentation
- Cloud project coordination
- Cost-aware cloud design



Future Improvements
- Add custom domain with SSL certificate
- Enable CloudFront access logging
- Implement CI/CD for automated deployments
- Add monitoring and alerts


Author: Stella Ojiuba
Cloud Project Coordinator | Junior Solutions Architect  
