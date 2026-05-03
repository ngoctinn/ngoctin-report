---
title: "Worklog Tuần 2"
date: 2026-03-16
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2: Serverless Architecture & Frontend Setup

- Tìm hiểu kiến trúc Serverless và lợi ích về chi phí, khả năng mở rộng
- Nghiên cứu các dịch vụ cốt lõi: Lambda, API Gateway, S3, DynamoDB
- Thực hành workshop và triển khai với AWS SAM
- Thiết kế sơ bộ kiến trúc hệ thống
- Thống nhất UI/UX và setup frontend với Next.js + Shadcn/ui
- Nghiên cứu tích hợp AI services vào dự án

### Các công việc cần triển khai trong tuần này:

| **Ngày** | **Nhiệm vụ** | **Bắt đầu** | **Hoàn thành** | **Tài liệu tham khảo** |
| -------- | ------------ | ----------- | -------------- | ---------------------- |
| T2 | **Học Clean Architecture:**<br>- Đọc "Clean Architecture" by Robert C. Martin (chương chính)<br>- Dependency Rule & Layer separation<br>- Entities, Use Cases, Interface Adapters, Frameworks<br>- Áp dụng vào Python với type hints | 16/03/2026 | 16/03/2026 | [Clean Architecture Book](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) |
| T3 | **Thiết kế Clean Architecture cho Lexi:**<br>- **Domain Layer:** Entities (User, Flashcard, Session, Scenario)<br>- **Use Case Layer:** Business logic interfaces<br>- **Infrastructure Layer:** DynamoDB, Bedrock adapters<br>- **Presentation Layer:** Lambda handlers<br>- Vẽ architecture diagram | 17/03/2026 | 17/03/2026 | [Python Clean Architecture](https://github.com/Enforcer/clean-architecture) |
| T4 | **Thiết kế DynamoDB Schema:**<br>- Phân tích access patterns<br>- Thiết kế single-table với PK/SK patterns<br>- Thiết kế GSI cho query phức tạp<br>- Document schema với ví dụ | 18/03/2026 | 18/03/2026 | [DynamoDB Single Table Design](https://www.alexdebrie.com/posts/dynamodb-single-table/) |
| T5 | **Thiết kế API Specification:**<br>- Định nghĩa endpoints (Auth, Profile, Flashcards, Sessions, Scenarios)<br>- Viết OpenAPI 3.0 spec<br>- Request/Response schemas | 19/03/2026 | 19/03/2026 | [OpenAPI Specification](https://swagger.io/specification/) |
| T6 | **Học Amazon Bedrock, Transcribe & Polly:**<br>- Bedrock concepts & Nova Lite model<br>- Transcribe: Speech-to-text streaming<br>- Polly: Text-to-speech với neural voices<br>- **Thực hành:** Test các services | 20/03/2026 | 20/03/2026 | [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html) |
| **T7** | **🎉 Tham gia sự kiện AWS First Cloud AI Journey Community Day 2026:**<br>- **Địa điểm:** Tầng 26 Bitexco Financial Tower, 02 Hải Triều, Q1, TP.HCM<br>- **Thời gian:** 09:00 – 12:00<br>- Kết nối với các chuyên gia Cloud<br>- Khám phá ứng dụng Cloud & Generative AI<br>- Trải nghiệm demo thực tế<br>- Mở rộng networking<br>- Kickoff chính thức FCAJ Bootcamp 2026 | **21/03/2026** | **21/03/2026** | [Event Link](https://luma.com/e8uotauk) |

### Kết quả đạt được tuần 2:

**1. Kiến thức Clean Architecture:**
- ✅ Hiểu rõ Dependency Rule và tầng phân lớp
- ✅ Biết cách áp dụng Clean Architecture vào Python
- ✅ Có architecture diagram cho dự án Lexi
- ✅ Định nghĩa rõ ràng các layer và dependencies
- ✅ Họp nhóm thảo luận và thống nhất cách tổ chức code

**2. Database Design:**
- ✅ DynamoDB schema hoàn chỉnh với single-table design
- ✅ Tất cả access patterns được cover
- ✅ GSI được thiết kế cho query phức tạp
- ✅ Document chi tiết với examples
- ✅ Trao đổi với nhóm về best practices cho DynamoDB

**3. API Design:**
- ✅ OpenAPI specification hoàn chỉnh
- ✅ Tất cả endpoints được định nghĩa rõ ràng
- ✅ Request/Response schemas với validation
- ✅ Error responses được standardize
- ✅ Review và điều chỉnh dựa trên feedback nhóm

**4. AI Services Knowledge:**
- ✅ Hiểu cách sử dụng Amazon Bedrock Nova Lite
- ✅ Biết cách integrate Transcribe cho speech-to-text
- ✅ Biết cách sử dụng Polly cho text-to-speech
- ✅ Đã test thành công các services
- ✅ Gửi ticket support yêu cầu cấp quyền Bedrock (chờ phản hồi)

**5. Networking & Learning:**
- ✅ Tham gia sự kiện "AWS First Cloud AI Journey Community Day 2026" tại Bitexco Financial Tower
- ✅ Tìm hiểu về Platform Engineering và GenAIOps
- ✅ Học về xu hướng xây dựng ứng dụng AI trên AWS
- ✅ Có thêm ý tưởng và kiến thức phục vụ cho dự án từ các chuyên gia
- ✅ Networking với cộng đồng AWS và các mentors
- ✅ Kickoff chính thức FCAJ Bootcamp 2026



### Thách thức và giải pháp:

**Thách thức 1:** Single-table design phức tạp với nhiều entity types
- **Giải pháp:** Họp nhóm thảo luận, tham khảo best practices, sử dụng composite keys pattern

**Thách thức 2:** Bedrock response có thể chậm
- **Giải pháp:** Thiết kế với streaming response và timeout handling

**Thách thức 3:** Clean Architecture có thể làm code phức tạp
- **Giải pháp:** Bắt đầu với simplified version, chỉ 3 layers cốt lõi

**Thách thức 4:** Chưa được cấp quyền sử dụng Bedrock
- **Giải pháp:** Đã gửi ticket support, trong lúc chờ sẽ mock response để phát triển song song



### Kế hoạch tuần tới (Sprint 1 - Week 3):

- Implement Authentication với Cognito
- Tạo User entity và use cases
- Implement DynamoDB repository layer
- Tạo Lambda handlers cho Auth endpoints
- Setup API Gateway với Cognito authorizer
- Họp nhóm review tiến độ và điều chỉnh nếu cần

---
