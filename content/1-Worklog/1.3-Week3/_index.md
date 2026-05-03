---
title: "Worklog Week 3"
date: 2026-03-23
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives: Sprint 1 - Backend Foundation (Part 1)

- Implement Authentication with Amazon Cognito
- Build Domain Layer (Entities)
- Implement Repository Layer with DynamoDB
- Create Lambda handlers for Auth endpoints
- Setup API Gateway with Cognito authorizer

### Weekly Tasks:

| **Day** | **Task** | **Start** | **Complete** | **Reference** |
| ------- | -------- | --------- | ------------ | ------------- |
| Mon | **Setup Amazon Cognito:**<br>- Create User Pool with email/password<br>- Configure password policy<br>- Enable Google OAuth provider<br>- Create App Client<br>- Configure hosted UI<br>- Test signup/login flow | 23/03/2026 | 23/03/2026 | [Cognito User Pools](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| Tue | **Implement Domain Layer:**<br>- `entities/user.py` - User entity with validation<br>- `entities/flashcard.py` - Flashcard entity<br>- `entities/session.py` - Session entity<br>- `entities/scenario.py` - Scenario entity<br>- Value objects (Email, UserId, etc.)<br>- Domain exceptions | 24/03/2026 | 24/03/2026 | [Domain-Driven Design](https://martinfowler.com/bliki/DomainDrivenDesign.html) |
| Wed | **Implement Repository Interfaces:**<br>- `repositories/user_repository.py` - Abstract interface<br>- `repositories/flashcard_repository.py`<br>- `repositories/session_repository.py`<br>- Define repository methods (save, find, delete, etc.) | 25/03/2026 | 25/03/2026 | [Repository Pattern](https://martinfowler.com/eaaCatalog/repository.html) |
| Thu | **Implement DynamoDB Repository & Auth Use Cases:**<br>- `infrastructure/dynamodb/user_repository_impl.py`<br>- Implement single-table design, PK/SK mapping<br>- `use_cases/auth/signup_user.py`, `login_user.py`, `refresh_token.py`<br>- Business logic validation<br>- Unit tests | 26/03/2026 | 26/03/2026 | [boto3 DynamoDB](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/dynamodb.html) |
| Fri | **Implement Lambda Handlers & API Gateway:**<br>- `handlers/auth/signup.py`, `login.py`, `refresh.py`<br>- Configure REST API in SAM template<br>- Add Cognito authorizer, CORS<br>- Deploy and test endpoints | 27/03/2026 | 27/03/2026 | [API Gateway with Cognito](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-integrate-with-cognito.html) |

### Week 3 Results:

**1. Authentication System:**
- ✅ Cognito User Pool configured with email/password + Google OAuth
- ✅ Signup flow working: email verification, password validation
- ✅ Login flow returns ID token, access token, refresh token
- ✅ Token refresh mechanism working

**2. Domain Layer:**
- ✅ 4 core entities implemented with full validation
- ✅ Value objects for type safety
- ✅ Domain exceptions for error handling
- ✅ Unit tests coverage > 90%

**3. Repository Layer:**
- ✅ Abstract repository interfaces defined
- ✅ DynamoDB implementation with single-table design
- ✅ CRUD operations working correctly
- ✅ Error handling and retry logic

**4. Use Cases:**
- ✅ Auth use cases implemented with business logic
- ✅ Input validation and sanitization
- ✅ Proper error handling
- ✅ Unit tests with mocked repositories

**5. API Endpoints:**
- ✅ 3 auth endpoints deployed and working:
  - `POST /auth/signup` - User registration
  - `POST /auth/login` - User login
  - `POST /auth/refresh` - Token refresh
- ✅ Cognito authorizer protecting endpoints
- ✅ CORS configured correctly
- ✅ Integration tests passing

### Code Structure:

```
src/
├── domain/
│   ├── entities/
│   │   ├── user.py
│   │   ├── flashcard.py
│   │   ├── session.py
│   │   └── scenario.py
│   ├── value_objects/
│   │   ├── email.py
│   │   └── user_id.py
│   └── exceptions.py
├── use_cases/
│   └── auth/
│       ├── signup_user.py
│       ├── login_user.py
│       └── refresh_token.py
├── repositories/
│   ├── user_repository.py (interface)
│   └── ...
├── infrastructure/
│   ├── dynamodb/
│   │   ├── user_repository_impl.py
│   │   └── connection.py
│   └── cognito/
│       └── auth_service.py
└── handlers/
    └── auth/
        ├── signup.py
        ├── login.py
        └── refresh.py
```

### Testing Results:

**Unit Tests:**
- ✅ Domain entities: 25 tests, 100% pass
- ✅ Use cases: 18 tests, 100% pass
- ✅ Repositories: 15 tests, 100% pass
- **Total:** 58 unit tests, 0 failures

**Integration Tests:**
- ✅ Signup flow: Email verification working
- ✅ Login flow: Tokens returned correctly
- ✅ Protected endpoints: Authorizer working
- ✅ Error cases: Proper error responses

### Challenges and Solutions:

**Challenge 1:** Cognito token validation in Lambda
- **Solution:** Use python-jose library to verify JWT tokens

**Challenge 2:** DynamoDB conditional writes for duplicate prevention
- **Solution:** Use ConditionExpression with attribute_not_exists

**Challenge 3:** Lambda cold start slowing down first request
- **Solution:** Optimize imports, lazy loading for heavy libraries

**Challenge 4:** Type hints with Python dynamic typing
- **Solution:** Use mypy strict mode, Pydantic for validation

**Challenge 5:** Encountered some errors during first deployment
- **Solution:** Debug step by step, reference documentation and ask mentor when needed

### Next Week Plan (Sprint 1 - Week 4):

- Implement Profile management (GET/PUT /profile)
- Implement Flashcard CRUD operations
- Setup frontend project with Next.js
- Create basic UI components
- Integrate frontend with Auth APIs
- Attend regular team meetings to review progress

---
