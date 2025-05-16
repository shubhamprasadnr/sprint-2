# VCS Implementation: GitHub Code Commit Notification Setup

| Author  | Created on | Version   | Last Edited On | Comment  | Reviewer |
|---------|------------|-----------|----------------|-------------------|---------------|
| Shubham | 15-04-25   |  version1| 15-04-25        | Internal Review    | Komal Jaiswal|
| Shubham | -   |  version1| -       | L0  Review  | Gaurav Singla |
| Shubham | -   |  version1| -      | L1  Review | Rahul Gupta |
| Shubham | -   |  version1| -      | L2  Review  | Mahesh Kumar|


## Table of Contents
1. [Introduction](#1-introduction)  
2. [Pre-requisites](#2-pre-requisites)  
3. [Step-by-Step Setup Guide](#3-step-by-step-setup-guide)  
   - [Step 1: Add a New Slack Workspace](#step-1-add-a-new-slack-workspace-if-needed)  
   - [Step 2: Add the GitHub App to Slack](#step-2-add-the-github-app-to-slack)  
   - [Step 3: Connect Slack to GitHub](#step-3-connect-slack-to-github)  
   - [Step 4: Subscribe a GitHub Repository](#step-4-subscribe-a-github-repository)  
   - [Step 5: Test the Integration](#step-5-test-the-integration)  
4. [Conclusion](#4-conclusion)  
5. [Contact Information](#5-contact-information)  
6. [References](#6-references)

---

## 1. Introduction

This document outlines how to set up notifications for GitHub repository activities — such as commits, pull requests, releases, deployments, and issues — directly in a Slack channel. This setup enables better collaboration, real-time updates, and improved transparency across development teams.

---

## 2. Pre-requisites

Ensure you have the following before starting:

- A GitHub account with access to the repository you want to monitor  
- Admin or write access to a Slack workspace  
- Permission to install Slack apps and authorize GitHub integration  
- A Slack channel (private or public) where you want to receive notifications  

---

## 3. Step-by-Step Setup Guide

This section walks you through setting up GitHub-to-Slack notifications using the official GitHub Slack app.

### 🔧 Step 1: Add a New Slack Workspace (if needed)

1. Go to [https://slack.com/get-started](https://slack.com/get-started)  
2. Follow the steps to create a new workspace or join an existing one  

---

### 🔧 Step 2: Add the GitHub App to Slack

1. Visit the GitHub Slack App page:  
   [https://slack.com/apps/A8GBNUWU8-github](https://slack.com/apps/A8GBNUWU8-github)  
2. Click **Add to Slack**  
3. Select your workspace and click **Allow** to authorize the app  

---

### 🔧 Step 3: Connect Slack to GitHub

In a Slack channel (e.g., `#sprint0`), type:

```bash
/github signin
```



## 4. Conclusion

Integrating GitHub with Slack using the official GitHub app provides a seamless way to receive real-time updates for repository events such as commits, PRs, issues, and more. This boosts transparency, speeds up collaboration, and helps teams stay aligned with development activity.

---

## 5. Contact Information

- **Developer Contact**: shuhampd145@example.com  
- **Slack Admin**: slackadmin@example.com  
- **GitHub Admin**: githubadmin@example.com  

---

## 6. References

- [GitHub Slack App](https://slack.com/apps/A8GBNUWU8-github)  
- [GitHub Subscribe Command Guide](https://docs.github.com/en/apps/slack/github-slack-integration)  
- [Slack Slash Command Reference](https://api.slack.com/interactivity/slash-commands)  
- [GitHub Webhooks (Advanced)](https://docs.github.com/en/webhooks)
