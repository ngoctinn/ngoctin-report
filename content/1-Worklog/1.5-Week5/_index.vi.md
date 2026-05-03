---
title: "Worklog Tuần 5"
date: 2026-04-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5: Sprint 2 - AI Tutor Integration

Tích hợp Amazon Bedrock Nova Micro cho AI conversation, implement session/turn management, và build chat UI.

### Công việc chính:

| **Ngày** | **Nhiệm vụ** | **Hoàn thành** |
| -------- | ------------ | -------------- |
| T2 | **Bedrock Service:**<br>- Nova Micro integration<br>- Converse API (non-streaming)<br>- Error handling + retries | ✅ |
| T3 | **Prompt Engineering:**<br>- System prompt design<br>- Level-specific prompts (A1-C2)<br>- Token optimization | ✅ |
| T4 | **Session & Turn Entities:**<br>- Session/Turn domain models<br>- Use cases (Create, Submit, Get, List)<br>- DynamoDB repositories | ✅ |
| T5 | **API Handlers:**<br>- POST /speaking/sessions<br>- POST /speaking/sessions/{id}/turns<br>- GET endpoints<br>- WebSocket support | ✅ |
| T6 | **Chat UI:**<br>- Chat interface (Shadcn/ui)<br>- Turn bubbles (user/AI)<br>- Loading states<br>- Mobile responsive | ✅ |

### Kết quả:

**1. Bedrock Integration:**
- ✅ Model: `apac.amazon.nova-micro-v1:0` (inference profile)
- ✅ Converse API (synchronous, non-streaming)
- ✅ Retry: AWS SDK adaptive mode (exponential backoff + jitter)
- ✅ Cost tracking per turn

**2. Prompt Engineering:**
- ✅ Level-specific prompts (A1-C2)
- ✅ OptimizedPromptBuilder
- ✅ Token optimization: ~150 tokens/response
- ✅ Context window: sliding window (last 10 turns)

**3. Session & Turn Management:**
- ✅ Entities: Session, Turn (not Conversation/Message)
- ✅ Use cases: Create, Submit, Get, List
- ✅ DynamoDB storage
- ✅ Sliding window context (10 turns)

**4. API Endpoints:**
- ✅ POST /speaking/sessions - Create session
- ✅ POST /speaking/sessions/{id}/turns - Submit turn
- ✅ GET /speaking/sessions/{id} - Get detail
- ✅ GET /speaking/sessions - List sessions
- ✅ WebSocket for real-time updates

**5. Chat UI:**
- ✅ Clean interface (Shadcn/ui)
- ✅ Turn bubbles (user vs AI)
- ✅ Loading indicators
- ✅ Mobile responsive

### Performance:

| Metric | Value |
|--------|-------|
| Bedrock latency | 800ms - 1.5s |
| API response | 125ms (non-voice) |
| Chat page load | 1.8s |
| Cost per turn | ~$0.0003 |



### User Feedback:

> "AI responses feel natural and contextual!" - Tester 1

> "Responses are fast enough, no lag." - Tester 2

> "Love the clean interface." - Tester 3

**Next:** Sprint 2 Part 2 - Flashcards, Scenarios, Stats

---
