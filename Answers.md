# Answers to Part 3

Add your answers to the questions in Part 3, Step 2 below. 

## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?<br>
    I am addressing Pillow version 9.4.0, listed in requirements.txt. Trivy identifies this vulnerability as CRITICAL.

2. Which CVE is linked to this vulnerability?<br>
    CVE-2023-50447. This vulnerability can allow an attacker to execute arbitrary code if they control the environment keys passed to Pillow's PIL.ImageMath.eval() function.

3. What remediation steps do you suggest?<br>
    Update Pillow in requirements.txt to a compatible, maintained version that includes the fix introduced in 10.2.0. Avoid passing untrusted environment keys to ImageMath.eval(). After updating, rebuild the Docker image, test the application, and rerun the scans to confirm this finding is resolved.

### Vulnerability 2:
1. Which vulnerability are you addressing?<br>
    I am addressing an arbitrary code execution vulnerability in PyYAML version 5.1, listed in requirements.txt. Trivy identifies it as CRITICAL.

2. Which CVE is linked to this vulnerability?<br>
    CVE-2020-14343. An attacker could use a specially crafted YAML document to execute Python code when it is processed using the vulnerable FullLoader.

3. What remediation steps do you suggest?<br>
    Update PyYAML in requirements.txt to a compatible, maintained version that includes the fix introduced in 5.4. Use yaml.safe_load() when processing YAML from untrusted sources. After updating, rebuild the Docker image, test the application, and rerun the scans to confirm this finding is resolved.
