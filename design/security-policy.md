# AWS Security Policy for Scalable & Secure Web Application

## 1. Identity & Access Management (IAM)
- Implement IAM Roles for EC2 instances to avoid embedding credentials in code.
- Apply Least Privilege Principle: each user/service has only necessary permissions.
- Use IAM Policies to control access to S3, RDS, and other resources.
- Enable MFA (Multi-Factor Authentication) for all IAM users.
- Rotate access keys regularly for enhanced security.

## 2. Data Protection
- Enable Encryption at Rest:
  - RDS: Use KMS-managed encryption keys.
  - S3: Use server-side encryption (SSE-S3 or SSE-KMS) for all stored objects.
- Enable Encryption in Transit using TLS/HTTPS for all communications.
- Apply S3 Bucket Policies to restrict public access.
- Use RDS security groups to restrict database access only to application EC2 instances.

## 3. Network Security
- Deploy EC2 instances in private subnets for sensitive workloads.
- Use Security Groups and Network ACLs to control inbound/outbound traffic.
- Allow access only from trusted IPs or application load balancer.
- Restrict SSH access with key pairs; avoid password-based logins.

## 4. Monitoring & Logging
- Enable CloudWatch monitoring for EC2, RDS, and S3 metrics.
- Create CloudWatch Alarms for CPU, memory, disk space, and unusual activity.
- Enable AWS CloudTrail for logging all API calls.
- Integrate SNS notifications for security events and alerts.

## 5. Application Security
- Keep EC2 instances patched and updated regularly.
- Use security groups to restrict access to application ports.
- Implement HTTPS with SSL/TLS for web traffic.
- Regularly audit application logs for unauthorized access attempts.

## 6. Backup & Disaster Recovery
- Enable RDS automated backups and snapshots.
- Enable S3 versioning to prevent accidental deletion.
- Store backups in different AWS regions for disaster recovery.
- Test backup restoration periodically.

## 7. Compliance & Best Practices
- Follow AWS Well-Architected Framework – Security Pillar.
- Periodically review IAM roles, policies, and access logs.
- Implement security audits and vulnerability assessments.
