# AI Security Scanner for AWS S3



## Objective

The objective of this project was to design and deploy a proactive cloud security auditing tool that automates the detection of misconfigurations within Amazon S3 environments. By leveraging the Boto3 SDK and Python, the scanner programmatically evaluates bucket-level security postures—specifically focusing on the identification of public access vulnerabilities and the lack of server-side encryption.
The project aimed to bridge the gap between manual security reviews and continuous automated governance, utilizing Cursor AI for rapid script iteration and IAM (Identity and Access Management) to enforce strict "Least Privilege" access. The ultimate goal was to provide an efficient, scalable solution to mitigate the risk of data exposure caused by human error in complex cloud architectures.


### Skills Learned


- Vulnerability Assessment: Learned to identify critical misconfigurations in S3, specifically focusing on Public Access Block settings and Encryption at Rest.
- Policy Auditing: Gained experience analyzing S3 Bucket Policies and ACLs to detect overly permissive "wildcard" permissions (*).
- Least Privilege Methodology: Applied the Principle of Least Privilege (PoLP) by creating custom IAM Roles and policies that grant only the specific permissions needed for the scanner to function.
- Boto3 (SDK for Python): Learned to use the AWS SDK to move beyond the visual console, programmatically listing buckets, retrieving security configurations, and handling API responses.
- AWS CLI Mastery: Gained proficiency in using the command line to configure security credentials, verify identity (sts get-caller-identity), and manage resources across different AWS Regions.
- Multi-Region Awareness: Learned how to use EC2 Global View and regional parameters to ensure no resources were left running in "hidden" regions.
- PowerShell Scripting: Used PowerShell for environment setup, executing CLI commands, and managing local directory structures for the project.
- Systematic Debugging: Strengthened the ability to debug across layers—from validating AWS credentials and network connectivity to troubleshooting API AuthFailure errors.


### Tools Used


- Cursor AI: Used as the primary IDE to leverage AI-native code generation, real-time debugging of Boto3 logic, and rapid script iteration.
- Python: The core programming language used to build the scanner logic and process AWS API data.
- Boto3 (AWS SDK for Python): The critical library used to programmatically interface with AWS services, enabling the script to "talk" to S3 and IAM.
- Amazon S3: The target service for the security audit; used for testing bucket policies, public access blocks, and encryption configurations.
- Amazon EC2: The compute environment used to host and execute the scanner (including instance, volume, and security group management).
- IAM (Identity & Access Management): Used to create granular security policies and user credentials, ensuring the scanner operated with limited, secure permissions.
- VPC (Virtual Private Cloud): The networking layer used to provide a secure environment for the EC2 instance to communicate with the S3 API.
- AWS CLI (Command Line Interface): Used for initial authentication, credential configuration, and cross-region resource verification.
- PowerShell: The local terminal environment used for script execution, file management, and environment variable configuration.

## Steps

*Ref 1: AI Security Scanner

<img width="890" height="623" alt="Screenshot 2026-01-28 152148" src="https://github.com/user-attachments/assets/a42b7d29-23db-42a3-9467-7538cf09dd7e" />

Initial staging of the Amazon S3 environment within the AWS Management Console. This target bucket was intentionally configured with specific policy variations to test the detection capabilities of the AI Security Scanner. This stage involved setting up the storage infrastructure that the Boto3-based Python script would later crawl and analyze for security vulnerabilities.


*Ref 2: AI Security Scanner


<img width="496" height="123" alt="Screenshot 2026-01-28 151433" src="https://github.com/user-attachments/assets/7aeb365e-41a3-4dde-bf26-2db394991540" />


This screenshot captures the automated staging phase of the project’s security validation workflow. Using a Python virtual environment to ensure isolated dependency management, a test_scanner.py script was executed to programmatically create a target Amazon S3 bucket and intentionally remove its Public Access Block. By orchestrating this "controlled vulnerability," the script simulates a high-risk "naked" bucket state, providing a live misconfiguration for the Boto3-based scanner to detect and flag during the auditing phase.


*Ref 3: AI Security Scanner



<img width="539" height="215" alt="Screenshot 2026-01-28 151516" src="https://github.com/user-attachments/assets/a1ecf850-6f6e-4ac9-b98b-e8d12ec3589d" />

This technical sequence demonstrates the execution and validation of the AI Security Scanner using automated test-case orchestration. Operating within an isolated Python virtual environment (venv), a test_scanner.py script was first utilized to programmatically stage a "controlled vulnerability" by creating the js-security-scan-test-2026-v1 bucket and intentionally removing its Public Access Block. Following this setup, the primary scanner.py engine was executed, leveraging the Boto3 SDK to crawl the live environment and successfully detect the misconfigured bucket. This workflow confirms the scanner's ability to identify "naked" S3 resources in real-time, proving its effectiveness for automated security auditing and risk remediation.








