---
title: "Worklog Week 4"
date: 2026-03-30
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives: Sprint 1 - Backend & Frontend Foundation (Part 2)

- Implement Profile and Flashcard APIs
- Setup Next.js frontend project
- Create UI components with Shadcn/ui
- Integrate frontend with backend APIs
- Deploy frontend to AWS Amplify

### Weekly Tasks:

| **Day** | **Task** | **Start** | **Complete** | **Reference** |
| ------- | -------- | --------- | ------------ | ------------- |
| Mon | **Implement Profile Use Cases & Handlers:**<br>- `use_cases/profile/get_profile.py`, `update_profile.py`, `complete_onboarding.py`<br>- `handlers/profile/get.py` - GET /profile<br>- `handlers/profile/update.py` - PUT /profile<br>- Deploy and test | 30/03/2026 | 30/03/2026 | [Lambda Handlers](https://docs.aws.amazon.com/lambda/latest/dg/python-handler.html) |
| Tue | **Implement Flashcard Backend:**<br>- Flashcard use cases (CRUD + SRS logic)<br>- `use_cases/flashcard/create_flashcard.py`, `list_flashcards.py`, `review_flashcard.py`<br>- SM-2 algorithm implementation<br>- Lambda handlers for flashcard endpoints | 31/03/2026 | 31/03/2026 | [SM-2 Algorithm](https://www.supermemo.com/en/archives1990-2015/english/ol/sm2) |
| Wed | **Setup Next.js Project & UI Components:**<br>- Create Next.js 16 app with App Router<br>- Configure TypeScript, Tailwind CSS, Shadcn/ui<br>- Layout components (Header, Sidebar, Footer)<br>- Auth components (LoginForm, SignupForm)<br>- Button, Input, Card from Shadcn/ui | 01/04/2026 | 01/04/2026 | [Next.js Documentation](https://nextjs.org/docs) |
| Thu | **Implement Auth Pages & API Client:**<br>- `/app/auth/login/page.tsx`, `/app/auth/signup/page.tsx`<br>- Integrate with Cognito Hosted UI<br>- `lib/api-client.ts` - Axios wrapper<br>- Token management<br>- Protected route middleware | 02/04/2026 | 02/04/2026 | [Next.js Authentication](https://nextjs.org/docs/app/building-your-application/authentication) |
| Fri | **Deploy Frontend:**<br>- Setup AWS Amplify Hosting<br>- Configure build settings<br>- Environment variables<br>- Deploy and test production build | 03/04/2026 | 03/04/2026 | [Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html) |

### Week 4 Results:

**1. Backend APIs:**
- ✅ Profile endpoints working:
  - `GET /profile` - Get user profile
  - `PUT /profile` - Update profile
  - `POST /profile/onboarding` - Complete onboarding
- ✅ Flashcard endpoints working:
  - `POST /flashcards` - Create flashcard
  - `GET /flashcards` - List user's flashcards
  - `GET /flashcards/{id}` - Get flashcard detail
  - `PUT /flashcards/{id}` - Update flashcard
  - `DELETE /flashcards/{id}` - Delete flashcard
  - `POST /flashcards/{id}/review` - Review flashcard (SRS)

**2. SM-2 Algorithm:**
- ✅ Spaced Repetition System implemented
- ✅ Calculate next review date based on performance
- ✅ Track ease factor and interval
- ✅ Unit tests for algorithm logic

**3. Frontend Foundation:**
- ✅ Next.js 16 project with App Router
- ✅ TypeScript configured with strict mode
- ✅ Tailwind CSS + Shadcn/ui setup
- ✅ Responsive layout components
- ✅ Dark mode support

**4. Authentication UI:**
- ✅ Login page with email/password
- ✅ Signup page with validation
- ✅ Google OAuth integration
- ✅ Protected routes middleware
- ✅ Token management

**5. Deployment:**
- ✅ Frontend deployed on AWS Amplify
- ✅ CI/CD pipeline with GitHub
- ✅ Environment variables configured
- ✅ Production build optimized

### Frontend Structure:

```
lexi-fe/
├── app/
│   ├── (auth)/
│   │   ├── login/
│   │   └── signup/
│   ├── (dashboard)/
│   │   ├── layout.tsx
│   │   ├── page.tsx (Dashboard)
│   │   ├── profile/
│   │   └── flashcards/
│   └── layout.tsx
├── components/
│   ├── ui/ (Shadcn components)
│   ├── auth/
│   ├── layout/
│   └── flashcards/
├── lib/
│   ├── api-client.ts
│   ├── auth.ts
│   └── utils.ts
└── types/
    └── api.ts
```

### API Integration Status:

| Feature | Backend | Frontend | Status |
|---------|---------|----------|--------|
| Signup | ✅ | ✅ | Working |
| Login | ✅ | ✅ | Working |
| Get Profile | ✅ | ✅ | Working |
| Update Profile | ✅ | ✅ | Working |
| Create Flashcard | ✅ | ✅ | Working |
| List Flashcards | ✅ | ✅ | Working |
| Review Flashcard | ✅ | 🚧 | In Progress |

### Testing Results:

**Backend:**
- ✅ Unit tests: 89 tests, 100% pass
- ✅ Integration tests: 12 tests, 100% pass
- ✅ Test coverage: 91%

**Frontend:**
- ✅ Component tests: 15 tests
- ✅ E2E tests: 5 critical flows
- ✅ Accessibility tests: WCAG AA compliant

### Performance Metrics:

**Backend:**
| Endpoint | Avg Response Time | P95 | P99 |
|----------|------------------|-----|-----|
| GET /profile | 45ms | 120ms | 180ms |
| PUT /profile | 65ms | 150ms | 220ms |
| POST /flashcards | 55ms | 140ms | 200ms |
| GET /flashcards | 70ms | 180ms | 280ms |

**Frontend:**
- ⚡ Lighthouse Score: 95/100
- 📦 Bundle size: 180KB (gzipped)
- 🎨 First Contentful Paint: 1.2s
- ⚙️ Time to Interactive: 2.1s

### Challenges and Solutions:

**Challenge 1:** CORS issues between frontend and API Gateway
- **Solution:** Configure CORS headers in SAM template, test with OPTIONS requests

**Challenge 2:** Complex token refresh logic
- **Solution:** Implement axios interceptor for auto-refresh expired tokens

**Challenge 3:** Next.js App Router learning curve
- **Solution:** Read docs carefully, reference examples, use Server Components correctly

**Challenge 4:** SM-2 algorithm edge cases
- **Solution:** Write comprehensive unit tests, handle boundary conditions

**Challenge 5:** Some bugs when integrating frontend-backend
- **Solution:** Debug step by step, use browser DevTools and Postman to test API

### Next Week Plan (Sprint 2 - Week 5):

- Integrate Amazon Bedrock for AI Tutor
- Implement conversation use cases
- Create chat UI components
- Implement streaming responses
- Test end-to-end conversation flow
- Team meeting to review and adjust prompt engineering

---
