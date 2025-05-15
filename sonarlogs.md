## SonarQube Log Files

| Author  | Created on | Version   | Last Edited On | Comment  | Reviewer |
|---------|------------|-----------|----------------|-------------------|---------------|
| Shubham | 14-04-25   |  version1| 14-04-25        | Internal Review    | Siddharth Pawar|
| Shubham | -   |  version1| -       | L0  Review  | Gaurav Singla |
| Shubham | -   |  version1| -      | L1  Review | Rahul Gupta |
| Shubham | -   |  version1| -      | L2  Review  | Mahesh Kumar|

##  Table of Contents
-[`Types Of Logs Files`](#Types-Of-Logs-Files)
- [1. `sonar.log`](#1-sonarlog)
- [2. `web.log`](#2-weblog)
- [3. `ce.log` (Compute Engine log)](#3-celog-compute-engine-log)
- [4. `es.log` (Elasticsearch log)](#4-eslog-elasticsearch-log)
- [5. `access.log` (Optional)](#5-accesslog-optional-if-access-logging-is-enabled)
- [6. `es_access.log` (Newer versions)](#6-es_accesslog-since-newer-versions)
- [`Contacts`](#Contacts)
- [`References `](#References)


## Full Documentation Of Sonarqube 

### 1. `sonar.log`
**Purpose:** Main entry point log; captures messages from SonarQube scripts (like startup and shutdown).

**Contains:**
- Environment details  
- JVM parameters  
- Starting/stopping status of components  

---

### ✅ 2. `web.log`
**Purpose:** Logs related to the Web Server of SonarQube.

**Contains:**
- HTTP request handling  
- Web UI issues  
- Web API errors  
- Session-related logs  

---

### ✅ 3. `ce.log` (Compute Engine log)
**Purpose:** Logs related to background task processing like code analysis reports processing.

**Contains:**
- Background task execution  
- Project analysis  
- Issues and metrics computation  

---

### ✅ 4. `es.log` (Elasticsearch log)
**Purpose:** Logs for Elasticsearch, which powers SonarQube’s search capabilities.

**Contains:**
- Indexing errors  
- Query performance  
- Cluster status  

---

### ✅ 5. `access.log` *(Optional, if access logging is enabled)*
**Purpose:** Records HTTP access requests, like Apache/Nginx access logs.

**Contains:**
- IP addresses  
- Requested URLs  
- Response codes and times  

---

### ✅ 6. `es_access.log` *(Since newer versions)*
**Purpose:** Elasticsearch-specific access log.

**Contains:**
- REST API calls to Elasticsearch  
- Diagnostic request info  


##  Contacts
| Name | Email Address |
|------|---------------|
| Shubham Prasad | [shubham.prasad.snaatak@mygurukulam.co](mailto:shubham.prasad.snaatak@mygurukulam.co) |

##  References

| Reference | Link |
|-----------|------|
| Official SonarQube Documentation – Logs | [View](https://docs.sonarsource.com/sonarqube/latest/instance-administration/logs/) |
