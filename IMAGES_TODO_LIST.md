# Workshop Images TODO List

## Overview
This document lists all screenshots and diagrams needed for the Lexi Workshop documentation.

---

## 5.1 Workshop Overview

### Diagrams Needed
1. **Lexi Architecture Diagram**
   - Location: After "Kiến trúc Lexi" section
   - Content: Complete system architecture showing:
     - Frontend (Next.js on Amplify)
     - API Gateway (REST + WebSocket)
     - Lambda Functions (23 functions)
     - DynamoDB (Single-table design)
     - Cognito (Auth)
     - Bedrock, Transcribe, Polly
     - S3 Storage
     - CloudWatch
   - Tool: draw.io, Lucidchart, or AWS Architecture Icons
   - File: `lexi-architecture-diagram.png`

---

## 5.2 Prerequiste (Chuẩn bị Môi trường)

### Screenshots Needed

1. **Terminal - Tool Versions**
   - Location: After "Cài đặt" section
   - Commands to run:
     ```bash
     node --version
     python3 --version
     aws --version
     sam --version
     git --version
     ```
   - File: `prerequiste-tool-versions.png`

2. **AWS CLI - Get Caller Identity**
   - Location: After "Kiểm tra Kết nối" section
   - Command to run:
     ```bash
     aws sts get-caller-identity
     ```
   - Expected output:
     ```json
     {
         "UserId": "AIDA...",
         "Account": "826229823693",
         "Arn": "arn:aws:iam::826229823693:user/NgocTin"
     }
     ```
   - File: `prerequiste-aws-identity.png`

---

## 5.3 Backend (Triển khai Backend)

### Screenshots Needed

1. **CloudFormation Stacks**
   - Location: After "Kiểm tra Stacks Hiện tại" section
   - Where: AWS Console → CloudFormation → Stacks
   - Show: All 4 stacks (lexi-database, lexi-auth-base, lexi-auth-lambdas, lexi-be)
   - File: `backend-cloudformation-stacks.png`

2. **DynamoDB Table Structure**
   - Location: After "Hiểu Single-Table Design" section
   - Where: AWS Console → DynamoDB → Tables → LexiApp
   - Show: Table overview with:
     - Primary key (PK, SK)
     - GSI1-5
     - Item count
     - Table size
   - File: `backend-dynamodb-structure.png`

---

## 5.4 Frontend (Xây dựng Frontend)

### Screenshots Needed

1. **Lexi Frontend Homepage**
   - Location: After "Tổng quan" section
   - Where: Browser showing Lexi homepage
   - Show: Main landing page with:
     - Navigation
     - Hero section
     - Key features
   - File: `frontend-homepage.png`

2. **Amplify Deployment Success**
   - Location: After "Deployment Flow" section
   - Where: AWS Console → Amplify → App → Deployments
   - Show: Successful deployment with:
     - Build status (green checkmark)
     - Deployment URL
     - Build time
   - File: `frontend-amplify-deployment.png`

---

## 5.5 AI & Voice (Tích hợp AI & Voice)

### Diagrams Needed

1. **Speaking Flow Diagram**
   - Location: After "Quy Trình Speaking Flow" section
   - Content: Detailed flow showing:
     - User speaks → Frontend records
     - Audio stream → Lambda
     - Transcribe (STT)
     - Bedrock (AI response)
     - Comprehend (NLP)
     - Polly (TTS)
     - Audio response → Frontend
     - Save to DynamoDB
   - Tool: draw.io or Lucidchart
   - File: `ai-voice-speaking-flow.png`

### Screenshots Needed

2. **Bedrock Model Invocation**
   - Location: After "Amazon Bedrock" section
   - Where: AWS Console → Bedrock → Models
   - Show: Available models with:
     - Model name (Nova Lite)
     - Model ID
     - Pricing
   - File: `ai-voice-bedrock-models.png`

---

## 5.6 CI/CD (CI/CD Pipeline)

### Diagrams Needed

1. **CI/CD Pipeline Diagram**
   - Location: After "CI/CD Architecture" section
   - Content: Complete pipeline showing:
     - Developer → Git Push
     - GitHub/GitLab
     - GitHub Actions (Backend + Frontend workflows)
     - SAM Build & Deploy
     - Amplify Auto-deploy
     - CloudFormation Update
     - Lambda Functions Updated
   - Tool: draw.io or Lucidchart
   - File: `cicd-pipeline-diagram.png`

### Screenshots Needed

2. **GitHub Actions Workflow Success**
   - Location: After "Monitoring Deployments" section
   - Where: GitHub → Actions → Workflow runs
   - Show: Successful workflow with:
     - Green checkmarks
     - Build time
     - Deploy steps
   - File: `cicd-github-actions-success.png`

---

## 5.7 Monitoring (Giám sát & Tối ưu Chi phí)

### Screenshots Needed

1. **CloudWatch Dashboard**
   - Location: After "CloudWatch" section
   - Where: AWS Console → CloudWatch → Dashboards
   - Show: Custom dashboard with:
     - Lambda invocations
     - API Gateway requests
     - DynamoDB read/write capacity
     - Error rates
   - File: `monitoring-cloudwatch-dashboard.png`

2. **Cost Explorer**
   - Location: After "Cost Optimization" section
   - Where: AWS Console → Cost Explorer
   - Show: Cost breakdown by service:
     - Lambda
     - DynamoDB
     - S3
     - Bedrock
     - Transcribe
     - Polly
   - File: `monitoring-cost-explorer.png`

---

## 5.8 Clean-up (Dọn dẹp & Quản lý Tài nguyên)

### Screenshots Needed

1. **CloudFormation Stacks Deleted**
   - Location: After "Xóa CloudFormation Stacks" section
   - Where: AWS Console → CloudFormation → Stacks
   - Show: Stacks with DELETE_COMPLETE status
   - File: `cleanup-stacks-deleted.png`

2. **Cost Explorer After Cleanup**
   - Location: After "Kiểm tra Chi phí" section
   - Where: AWS Console → Cost Explorer
   - Show: Cost trend showing decrease after cleanup
   - File: `cleanup-cost-after.png`

---

## Summary

### Total Images Needed: 16

#### Diagrams (4)
- [ ] Lexi Architecture Diagram
- [ ] Speaking Flow Diagram
- [ ] CI/CD Pipeline Diagram
- [ ] (Optional) DynamoDB Single-Table Design Diagram

#### Screenshots (12)
- [ ] Tool Versions (Terminal)
- [ ] AWS Identity (Terminal)
- [ ] CloudFormation Stacks (AWS Console)
- [ ] DynamoDB Structure (AWS Console)
- [ ] Frontend Homepage (Browser)
- [ ] Amplify Deployment (AWS Console)
- [ ] Bedrock Models (AWS Console)
- [ ] GitHub Actions Success (GitHub)
- [ ] CloudWatch Dashboard (AWS Console)
- [ ] Cost Explorer (AWS Console)
- [ ] Stacks Deleted (AWS Console)
- [ ] Cost After Cleanup (AWS Console)

---

## Image Guidelines

### Format
- **File Format**: PNG (preferred) or JPG
- **Resolution**: Minimum 1920x1080 for screenshots
- **File Size**: Keep under 500KB (compress if needed)

### Naming Convention
```
[section]-[description].png

Examples:
- prerequiste-tool-versions.png
- backend-cloudformation-stacks.png
- frontend-homepage.png
```

### Storage Location
```
docs/worklog-hugo/ngoctin-report/static/images/5-Workshop/
├── 5.1-Workshop-overview/
│   └── lexi-architecture-diagram.png
├── 5.2-Prerequiste/
│   ├── prerequiste-tool-versions.png
│   └── prerequiste-aws-identity.png
├── 5.3-Backend/
│   ├── backend-cloudformation-stacks.png
│   └── backend-dynamodb-structure.png
├── 5.4-Frontend/
│   ├── frontend-homepage.png
│   └── frontend-amplify-deployment.png
├── 5.5-AI-Voice/
│   ├── ai-voice-speaking-flow.png
│   └── ai-voice-bedrock-models.png
├── 5.6-CI-CD/
│   ├── cicd-pipeline-diagram.png
│   └── cicd-github-actions-success.png
├── 5.7-Monitoring/
│   ├── monitoring-cloudwatch-dashboard.png
│   └── monitoring-cost-explorer.png
└── 5.8-Clean-up/
    ├── cleanup-stacks-deleted.png
    └── cleanup-cost-after.png
```

### Markdown Syntax
```markdown
![Alt Text](/images/5-Workshop/[section]/[filename].png)
*Caption: Description of the image*
```

---

## Tools for Creating Diagrams

### Architecture Diagrams
1. **draw.io** (Free, Web-based)
   - URL: https://app.diagrams.net/
   - AWS Architecture Icons: Built-in

2. **Lucidchart** (Free tier available)
   - URL: https://www.lucidchart.com/
   - AWS Architecture Icons: Available

3. **AWS Architecture Icons**
   - Download: https://aws.amazon.com/architecture/icons/
   - Use with: PowerPoint, Keynote, draw.io

### Screenshot Tools
1. **macOS**: Cmd+Shift+4 (region), Cmd+Shift+3 (full screen)
2. **Windows**: Win+Shift+S (Snipping Tool)
3. **Linux**: Flameshot, GNOME Screenshot

### Image Optimization
1. **TinyPNG** - https://tinypng.com/ (compress PNG/JPG)
2. **ImageOptim** (macOS) - https://imageoptim.com/
3. **GIMP** (All platforms) - https://www.gimp.org/

---

**Created**: 2026-05-03
**Status**: ⚠️ Pending - All images need to be created
**Priority**: High - Required for workshop completion
