---
title: "Worklog Tuần 7"
date: 2026-04-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7: Sprint 3 - Voice Integration

Tích hợp voice cho speaking practice: streaming transcription (browser → Transcribe WebSocket), AI response generation, và text-to-speech.

### Công việc chính:

| **Ngày** | **Nhiệm vụ** | **Hoàn thành** |
| -------- | ------------ | -------------- |
| T2 | **Transcribe Streaming:**<br>- Presigned WebSocket URL generator (backend)<br>- Browser → Transcribe direct connection<br>- Real-time transcription handling | ✅ |
| T3 | **Polly TTS:**<br>- Neural voices integration (Joanna, Matthew)<br>- S3 storage + presigned URLs<br>- Audio synthesis endpoint | ✅ |
| T4 | **Voice UI:**<br>- Audio recording (MediaRecorder API)<br>- Streaming transcription integration<br>- Audio playback components<br>- Recording controls (start/stop/preview) | ✅ |
| T5 | **Voice Integration:**<br>- Connect recording → transcription → AI → TTS flow<br>- Error handling cho connection issues<br>- Audio format compatibility | ✅ |
| T6 | **Testing:**<br>- Test voice recording flow<br>- Test transcription accuracy<br>- Test audio playback<br>- Cross-browser testing (Chrome, Safari) | ✅ |

### Kết quả:

**1. Streaming Transcription:**
- ✅ Browser → Transcribe WebSocket (direct connection)
- ✅ Presigned URL generator với SigV4 signing
- ✅ Real-time transcription (200-400ms latency)
- ✅ Error handling cho connection issues

**2. Text-to-Speech:**
- ✅ Polly neural voices (Joanna, Matthew)
- ✅ S3 storage + presigned URLs (1h expiry)
- ✅ MP3 format, 24kHz
- ✅ Synchronous synthesis (500-800ms)

**3. Voice UI:**
- ✅ Recording controls (start/stop/preview)
- ✅ Audio visualization (waveform)
- ✅ Playback controls
- ✅ Mobile responsive

**4. Testing:**
- ✅ Test với Chrome desktop
- ✅ Test với Safari (iOS/macOS)
- ✅ Test transcription accuracy với sample audio
- ✅ Test end-to-end voice turn flow

### Thách thức:

1. **iOS Safari WebM format** → Implemented fallback to WAV
2. **Transcribe WebSocket connection** → Added retry logic
3. **Audio format compatibility** → Format detection + conversion
4. **S3 presigned URL expiration** → 1h expiry, regenerate on-demand



**Next:** Sprint 4 - Final testing, deployment, demo

---
