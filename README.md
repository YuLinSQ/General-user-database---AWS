# General-user-database---AWS
This is a general database coded in AWS, easy to integrate into my projects

Could do: Using AWS services Ec2, S3, Lambda, I can design an automated security orchestration and response system that monitors, flags, and alerts on malicious activity.
EC2: Configure your EC2 instance to log authentication attempts or application traffic. Run a script on EC2 that aggregates these access logs (like SSH failure logs or application firewall flags) and periodically ships them to S3 for auditing.
S3: Immutable security log storage, configuring S3 Bucket Policies, forcing Server-Side Encryption (SSE-KMS), and setting up Object Locking to prevent logs from being altered or deleted by an attacker.
Lambda: Every time a new log file drops into S3, Lambda immediately parses the file. It checks the IP addresses against a public threat intelligence feed or looks for suspicious patterns (like 50 failed login attempts in 10 seconds). If it detects a threat, Lambda executes a security action—such as sending an urgent alert notification via Amazon SNS or interacting with the AWS API to dynamically modify the EC2 instance's Security Group to block the malicious IP address entirely.
