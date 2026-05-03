---
title: "Worklog Week 7"
date: 2026-04-20
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives: Sprint 3 - Voice Integration

Integrate voice for speaking practice: streaming transcription (browser → Transcribe WebSocket), AI response generation, and text-to-speech.

### Main Tasks:

| **Day** | **Task** | **Complete** |
| ------- | -------- | ------------ |
| Mon | **Transcribe Streaming:**<br>- Presigned WebSocket URL generator (backend)<br>- Browser → Transcribe direct connection<br>- Real-time transcription handling | ✅ |
| Tue | **Polly TTS:**<br>- Neural voices integration (Joanna, Matthew)<br>- S3 storage + presigned URLs<br>- Audio synthesis endpoint | ✅ |
| Wed | **Voice UI:**<br>- Audio recording (MediaRecorder API)<br>- Streaming transcription integration<br>- Audio playback components<br>- Recording controls (start/stop/preview) | ✅ |
| Thu | **Voice Integration:**<br>- Connect recording → transcription → AI → TTS flow<br>- Error handling for connection issues<br>- Audio format compatibility | ✅ |
| Fri | **Testing:**<br>- Test voice recording flow<br>- Test transcription accuracy<br>- Test audio playback<br>- Cross-browser testing (Chrome, Safari) | ✅ |

### Results:

**1. Streaming Transcription:**
- ✅ Browser → Transcribe WebSocket (direct connection)
- ✅ Presigned URL generator with SigV4 signing
- ✅ Real-time transcription (200-400ms latency)
- ✅ Error handling for connection issues

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
- ✅ Test with Chrome desktop
- ✅ Test with Safari (iOS/macOS)
- ✅ Test transcription accuracy with sample audio
- ✅ Test end-to-end voice turn flow

### Challenges:

1. **iOS Safari WebM format** → Implemented fallback to WAV
2. **Transcribe WebSocket connection** → Added retry logic
3. **Audio format compatibility** → Format detection + conversion
4. **S3 presigned URL expiration** → 1h expiry, regenerate on-demand

**Next:** Sprint 4 - Final testing, deployment, demo

---
