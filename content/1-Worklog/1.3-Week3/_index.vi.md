---
title: "Worklog Tuần 3"
date: 2026-03-23
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3: Sprint 1 - Backend Foundation (Part 1)

- Implement Authentication với Amazon Cognito
- Xây dựng Domain Layer (Entities)
- Implement Repository Layer với DynamoDB
- Tạo Lambda handlers cho Auth endpoints
- Setup API Gateway với Cognito authorizer

### Các công việc cần triển khai trong tuần này:

| **Ngày** | **Nhiệm vụ** | **Bắt đầu** | **Hoàn thành** | **Tài liệu tham khảo** |
| -------- | ------------ | ----------- | -------------- | ---------------------- |
| T2 | **Setup Amazon Cognito:**<br>- Tạo User Pool với email/password<br>- Cấu hình password policy<br>- Enable Google OAuth provider<br>- Tạo App Client<br>- Configure hosted UI<br>- Test signup/login flow | 23/03/2026 | 23/03/2026 | [Cognito User Pools](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| T3 | **Implement Domain Layer:**<br>- `entities/user.py` - User entity với validation<br>- `entities/flashcard.py` - Flashcard entity<br>- `entities/session.py` - Session entity<br>- `entities/scenario.py` - Scenario entity<br>- Value objects (Email, UserId, etc.)<br>- Domain exceptions | 24/03/2026 | 24/03/2026 | [Domain-Driven Design](https://martinfowler.com/bliki/DomainDrivenDesign.html) |
| T4 | **Implement Repository Interfaces:**<br>- `repositories/user_repository.py` - Abstract interface<br>- `repositories/flashcard_repository.py`<br>- `repositories/session_repository.py`<br>- Define repository methods (save, find, delete, etc.) | 25/03/2026 | 25/03/2026 | [Repository Pattern](https://martinfowler.com/eaaCatalog/repository.html) |
| T5 | **Implement DynamoDB Repository & Auth Use Cases:**<br>- `infrastructure/dynamodb/user_repository_impl.py`<br>- Implement single-table design, PK/SK mapping<br>- `use_cases/auth/signup_user.py`, `login_user.py`, `refresh_token.py`<br>- Business logic validation<br>- Unit tests | 26/03/2026 | 26/03/2026 | [boto3 DynamoDB](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/dynamodb.html) |
| T6 | **Implement Lambda Handlers & API Gateway:**<br>- `handlers/auth/signup.py`, `login.py`, `refresh.py`<br>- Configure REST API trong SAM template<br>- Add Cognito authorizer, CORS<br>- Deploy và test endpoints | 27/03/2026 | 27/03/2026 | [API Gateway with Cognito](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-integrate-with-cognito.html) |

### Kết quả đạt được tuần 3:

**1. Authentication System:**
- ✅ Cognito User Pool configured với email/password + Google OAuth
- ✅ Signup flow hoạt động: email verification, password validation
- ✅ Login flow trả về ID token, access token, refresh token
- ✅ Token refresh mechanism working

**2. Domain Layer:**
- ✅ 4 core entities implemented với full validation
- ✅ Value objects cho type safety
- ✅ Domain exceptions cho error handling
- ✅ Unit tests coverage > 90%

**3. Repository Layer:**
- ✅ Abstract repository interfaces defined
- ✅ DynamoDB implementation với single-table design
- ✅ CRUD operations working correctly
- ✅ Error handling và retry logic

**4. Use Cases:**
- ✅ Auth use cases implemented với business logic
- ✅ Input validation và sanitization
- ✅ Proper error handling
- ✅ Unit tests với mocked repositories

**5. API Endpoints:**
- ✅ 3 auth endpoints deployed và working:
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

### Thách thức và giải pháp:

**Thách thức 1:** Cognito token validation trong Lambda
- **Giải pháp:** Sử dụng python-jose library để verify JWT tokens

**Thách thức 2:** DynamoDB conditional writes cho duplicate prevention
- **Giải pháp:** Sử dụng ConditionExpression với attribute_not_exists

**Thách thức 3:** Lambda cold start làm chậm first request
- **Giải pháp:** Optimize imports, lazy loading cho heavy libraries

**Thách thức 4:** Type hints với Python dynamic typing
- **Giải pháp:** Sử dụng mypy strict mode, Pydantic cho validation

**Thách thức 5:** Gặp một số lỗi khi deploy lần đầu
- **Giải pháp:** Debug từng bước, tham khảo documentation và hỏi mentor khi cần



### Kế hoạch tuần tới (Sprint 1 - Week 4):

- Implement Profile management (GET/PUT /profile)
- Implement Flashcard CRUD operations
- Setup frontend project với Next.js
- Create basic UI components
- Integrate frontend với Auth APIs
- Tham gia họp nhóm định kỳ để review tiến độ

---
