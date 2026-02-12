<h1>AI Security Scanner for AWS S3</h1>

<h2>Objective</h2>
<p>
This project builds an automated S3 security scanner that detects common misconfigurations, including:
</p>

<ul>
  <li>Public access exposure</li>
  <li>Missing server-side encryption</li>
</ul>

<p>
The scanner uses Python and Boto3 to evaluate bucket configurations programmatically instead of relying on manual console reviews.
</p>

<p>
The goal was to create a lightweight auditing tool that reduces human error and supports continuous cloud security monitoring. 
IAM roles were configured using the Principle of Least Privilege to restrict access to only required permissions.
</p>

<hr>

<h2>Skills Developed</h2>
<ul>
  <li>Identified S3 misconfigurations (Public Access Block, encryption at rest)</li>
  <li>Audited bucket policies and ACLs for wildcard (<code>*</code>) permissions</li>
  <li>Applied Least Privilege by designing scoped IAM roles</li>
  <li>Used Boto3 to list buckets and retrieve security configurations</li>
  <li>Managed AWS authentication using the CLI (<code>sts get-caller-identity</code>)</li>
  <li>Validated resources across regions</li>
  <li>Debugged API authentication and permission errors</li>
  <li>Built and tested within isolated Python virtual environments</li>
</ul>

<hr>

<h2>Tools</h2>
<ul>
  <li><strong>Python</strong></li>
  <li><strong>Boto3 (AWS SDK)</strong></li>
  <li><strong>Amazon S3</strong></li>
  <li><strong>IAM</strong></li>
  <li><strong>EC2</strong></li>
  <li><strong>AWS CLI</strong></li>
  <li><strong>VPC</strong></li>
  <li><strong>PowerShell</strong></li>
  <li><strong>Cursor</strong> (for code iteration and debugging)</li>
</ul>

<hr>

<h2>Implementation Steps</h2>

<h3>Ref 1 – S3 Environment Setup</h3>
<p>
An S3 bucket was created and intentionally misconfigured to simulate real-world exposure scenarios. 
This provided a controlled environment to validate scanner detection logic.
</p>

<img width="890" height="623" src="https://github.com/user-attachments/assets/a42b7d29-23db-42a3-9467-7538cf09dd7e" />

<br><br>

<h3>Ref 2 – Controlled Vulnerability Creation</h3>
<p>
Using a Python virtual environment, <code>test_scanner.py</code> was executed to:
</p>

<ul>
  <li>Create a test S3 bucket</li>
  <li>Remove its Public Access Block</li>
  <li>Simulate a publicly exposed bucket</li>
</ul>

<p>
This staged vulnerability was used to validate detection accuracy.
</p>

<img width="496" height="123" src="https://github.com/user-attachments/assets/7aeb365e-41a3-4dde-bf26-2db394991540" />

<br><br>

<h3>Ref 3 – Scanner Execution & Detection</h3>
<p>
The main <code>scanner.py</code> script was executed to:
</p>

<ul>
  <li>Crawl S3 buckets via Boto3</li>
  <li>Identify the intentionally misconfigured resource</li>
  <li>Flag the exposure in real time</li>
</ul>

<p>
This confirmed the scanner’s ability to detect public S3 buckets and encryption gaps.
</p>

<img width="539" height="215" src="https://github.com/user-attachments/assets/a1ecf850-6f6e-4ac9-b98b-e8d12ec3589d" />
