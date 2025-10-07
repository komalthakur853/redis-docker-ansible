# Manual Deployment Guide – Build Pipeline

## Overview

This guide explains how to manually trigger builds  for applications using the build pipeline interface.

## Project Info

* **Application:** APP2 (Sample)
* **Project:** ot-demo-ms (Sample)
* **Environment:** DEV-MAIN (Sample)
* **Job Template:** MI-TEMPLATE (1.0) (Sample)

---

## Prerequisites

* Access to the application portal
* Build and deploy permissions for target environment
* Application with configured builds
* Valid job template
* Already build Cluster and services
* Github Repository

---
### Step 1: Navigate to Application
1. Click **Application** from the left sidebar
2. Click **Service Overview**
3. Select your application (e.g., **ot-demo-ms**)
4. Click on the application instance (e.g., **APP2**)

### Step 2: Access Build Details
1. Ensure you're on the **ENV BUILD DETAILS** tab
2. Click on environment (e.g., **DEV-MAIN**) is according to your needs whether DEV or QA

### Step 3: Trigger Build
1. Click the **Build** button (right side of the page) with a Symbol ⚡
2. The **"Trigger a new Build"** dialog opens

### Step 4: Configure Build Settings

#### Docker Cache
- **Yes** (recommended): Faster builds, uses cached layers
- **No**: Clean build, slower but ensures latest dependencies

#### Enter Tag (Optional)
- Leave blank for auto-generated tag
- Or enter custom tag (e.g., `v1.0.0`, `hotfix-123`)
- Click "Provide Custom Tag" link for help

#### Branch Name (Required)
- Select branch from dropdown
- Click "Provide Custom Branch" for custom branch entry

#### Specific Commit ID (Optional)
- Toggle **No** (default): Builds latest commit
- Toggle **Yes**: Enter specific commit SHA to build

#### Secondary Build Override (Optional)
- Toggle **No** (default): Secondary builds use same branch as main
- Toggle **Yes**: Use different branch for secondary builds

### Step 5: Review Environment
- Verify environment: **DEV** → **dev-main**
- Check **Last Builds Details** for reference

### Step 6: Execute Build
Choose one option:

- **TRIGGER BUILD**: Builds only, no deployment
- **Cancel**: Closes dialog without action

### Step 7: Monitor Build
1. Build status updates in real-time
2. Click build number to view logs
3. Check for **SUCCESS** status


## Action Buttons

### Top Action Bar
- **⚡ Lightning**: Quick Build
- **📤 Deploy**: Quick Deploy
- **🔄 Promote**: Promote build to another environment
- **☰ History**: View build/deploy history
- **<img width="30" height="28" alt="image" src="https://github.com/user-attachments/assets/919129b7-d643-4c58-aee8-47b57badbc64" />logs**: View Deployment Status 

---

## Troubleshooting

| Issue                    | Possible Fix                                  |
| ------------------------ | --------------------------------------------- |
| Build button not visible | Check permissions and refresh page            |
| Branch dropdown empty    | Verify repo connection and permissions        |
| Build fails immediately  | Check logs, Dockerfile, and credentials       |
| Long build times         | Enable Docker cache or check system resources |

---

## Best Practices

* Verify correct environment before building.
* Review last successful build for reference.
* Use consistent and meaningful tags.
* Use clean builds (cache off) for troubleshooting.
* Always check logs after triggering builds.

---

## Common Scenarios

| Scenario             | Branch         | Tag          | Action                 |
| -------------------- | -------------- | ------------ | ---------------------- |
| Dev build            | develop        | Auto         | Trigger Build          |
| Release              | main           | v1.0.0       | Trigger Build & Deploy |
| Hotfix               | hotfix/*       | hotfix-issue | Trigger Build & Deploy |
| Rebuild past version | Same as before | rebuild-tag  | Trigger Build          |
| Feature test         | feature/*      | feature-test | Trigger Build & Deploy |

---

## Quick Reference

**Workflow:**

1. Application → Service Overview → Select App
2. ENV BUILD DETAILS → Verify Main Build
3. Click Build → Configure → Trigger
4. Monitor progress and logs

**Key Buttons:**

| Name                   | Action               |
| ---------------------- | -------------------- |
| Build                  | Open build dialog    |
| Trigger Build          | Build only           |
| Trigger Build & Deploy | Build and deploy     |
| Refresh                | Reload build history |

---

## Support

* **Build issues:** Check logs
* **Template issues:** Review job template
* **Permission issues:** Contact admin
* **Environment issues:** Check configuration

