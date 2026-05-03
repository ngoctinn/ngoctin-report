---
title: "Worklog Week 2"
date: 2026-03-16
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives: Serverless Architecture & Frontend Setup

- Understand Serverless architecture and benefits (cost, scalability)
- Research core services: Lambda, API Gateway, S3, DynamoDB
- Practice workshops and deployment with AWS SAM
- Design preliminary system architecture
- Align on UI/UX and setup frontend with Next.js + Shadcn/ui
- Research AI services integration

### Weekly Tasks:

| **Day** | **Task** | **Start** | **Complete** | **Reference** |
| ------- | -------- | --------- | ------------ | ------------- |
| Mon | **Learn Clean Architecture:**<br>- Read "Clean Architecture" by Robert C. Martin (main chapters)<br>- Dependency Rule & Layer separation<br>- Entities, Use Cases, Interface Adapters, Frameworks<br>- Apply to Python with type hints | 16/03/2026 | 16/03/2026 | [Clean Architecture Blog](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) |
| Tue | **Design Clean Architecture for Lexi:**<br>- **Domain Layer:** Entities (User, Flashcard, Session, Scenario)<br>- **Use Case Layer:** Business logic interfaces<br>- **Infrastructure Layer:** DynamoDB, Bedrock adapters<br>- **Presentation Layer:** Lambda handlers<br>- Draw architecture diagram | 17/03/2026 | 17/03/2026 | [Python Clean Architecture](https://github.com/Enforcer/clean-architecture) |
| Wed | **Design DynamoDB Schema:**<br>- Analyze access patterns<br>- Design single-table with PK/SK patterns<br>- Design GSI for complex queries<br>- Document schema with examples | 18/03/2026 | 18/03/2026 | [DynamoDB Single Table Design](https://www.alexdebrie.com/posts/dynamodb-single-table/) |
| Thu | **Design API Specification:**<br>- Define endpoints (Auth, Profile, Flashcards, Sessions, Scenarios)<br>- Write OpenAPI 3.0 spec<br>- Request/Response schemas | 19/03/2026 | 19/03/2026 | [OpenAPI Specification](https://swagger.io/specification/) |
| Fri | **Learn Amazon Bedrock, Transcribe & Polly:**<br>- Bedrock concepts & Nova Lite model<br>- Transcribe: Speech-to-text streaming<br>- Polly: Text-to-speech with neural voices<br>- **Practice:** Test the services | 20/03/2026 | 20/03/2026 | [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html) |
| **Sat** | **🎉 Participate in AWS First Cloud AI Journey Community Day 2026:**<br>- **Location:** Floor 26 Bitexco Financial Tower, 02 Hai Trieu, D1, HCMC<br>- **Time:** 09:00 – 12:00<br>- Connect with Cloud experts<br>- Explore Cloud & Generative AI applications<br>- Experience live demos<br>- Expand networking<br>- Official FCAJ Bootcamp 2026 Kickoff | **21/03/2026** | **21/03/2026** | [Event Link](https://luma.com/e8uotauk) |

### Week 2 Results:

**1. Clean Architecture Knowledge:**
- ✅ Understood Dependency Rule and layer separation
- ✅ Learned how to apply Clean Architecture to Python
- ✅ Created architecture diagram for Lexi project
- ✅ Clearly defined layers and dependencies
- ✅ Team meeting to discuss and align on code organization

**2. Database Design:**
- ✅ Complete DynamoDB schema with single-table design
- ✅ All access patterns covered
- ✅ GSI designed for complex queries
- ✅ Detailed documentation with examples
- ✅ Team discussion on DynamoDB best practices

**3. API Design:**
- ✅ Complete OpenAPI specification
- ✅ All endpoints clearly defined
- ✅ Request/Response schemas with validation
- ✅ Standardized error responses
- ✅ Review and adjustments based on team feedback

**4. AI Services Knowledge:**
- ✅ Understood how to use Amazon Bedrock Nova Lite
- ✅ Learned Transcribe for speech-to-text
- ✅ Learned Polly for text-to-speech
- ✅ Successfully tested the services
- ✅ Submitted support ticket for Bedrock permissions (awaiting response)

**5. Networking & Learning:**
- ✅ Participated in "AWS First Cloud AI Journey Community Day 2026" at Bitexco Financial Tower
- ✅ Learned about Platform Engineering and GenAIOps
- ✅ Explored trends in building AI applications on AWS
- ✅ Gained additional ideas and knowledge from experts
- ✅ Networked with AWS community and mentors
- ✅ Official FCAJ Bootcamp 2026 Kickoff

### Challenges and Solutions:

**Challenge 1:** Single-table design complexity with many entity types
- **Solution:** Team discussion, reference best practices, use composite keys pattern

**Challenge 2:** Bedrock responses may be slow
- **Solution:** Design with streaming response and timeout handling

**Challenge 3:** Clean Architecture may make code complex
- **Solution:** Start with simplified version, only 3 core layers

**Challenge 4:** Not yet granted Bedrock permissions
- **Solution:** Submitted support ticket, will mock responses for parallel development

### Next Week Plan (Sprint 1 - Week 3):

- Implement Authentication with Cognito
- Create User entity and use cases
- Implement DynamoDB repository layer
- Create Lambda handlers for Auth endpoints
- Setup API Gateway with Cognito authorizer
- Team meeting to review progress and adjust if needed

---
