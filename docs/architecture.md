# SIGNALCHECK — System Architecture

## Overview

SIGNALCHECK has two investigation modes: uploaded media analysis and live media analysis. Both connect to a shared AI investigation engine that collects evidence and generates an explainable report.

## 1. Upload & Investigate

1. User uploads an image, video, audio file, document or URL.
2. The backend processes the uploaded content.
3. Gemini extracts claims and analyzes the available media.
4. The investigation agent searches for relevant sources.
5. Browser automation inspects candidate webpages.
6. Evidence is collected and content is compared.
7. The system generates an investigation report.

## 2. Live Detection

### Webcam and Microphone

1. User grants camera and microphone permission.
2. The browser captures live audio and video.
3. Audio chunks and sampled video frames are streamed through WebSockets.
4. The media-processing layer prepares the input for Gemini Live.
5. Analysis events and timestamps are sent to the dashboard.

### External Livestreams

1. User supplies an accessible and authorized stream.
2. The backend ingests the supported stream.
3. FFmpeg extracts audio segments and video frames.
4. Media is sent for analysis.
5. Potentially suspicious segments and relevant spoken claims are recorded for investigation.

## 3. AI Investigation Agent

**Primary model: Gemini 3.8 Flash**

Responsibilities:
- Extract individual claims.
- Identify relevant entities and organizations.
- Plan investigations.
- Request searches and webpage inspections.
- Compare collected evidence.
- Generate structured findings.

**Live model: Gemini 3.8 Live**

Responsible for real-time multimodal interaction with incoming audio and sampled video frames.

## 4. MCP Tool Layer

The backend connects the AI agent to structured investigation tools:

- Search sources.
- Open and inspect webpages.
- Extract supporting evidence.
- Compare documents.
- Retrieve available archived versions.
- Store investigation findings.

MCP provides standardized tool access. Playwright performs the actual browser navigation.

## 5. Evidence and Reporting

Each investigation stores:

- Source URLs.
- Relevant text excerpts.
- Retrieval timestamps.
- Available publication dates.
- Content comparisons.
- Media-analysis results.
- Claim-level assessments.

The Evidence Journey Graph connects the submitted content with discovered evidence and related sources.

## Proposed Technology Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js |
| Backend | Python / FastAPI |
| Main AI Agent | Gemini API |
| Live Analysis | Gemini Live API |
| Tool Integration | MCP |
| Browser Automation | Playwright |
| Media Processing | FFmpeg |
| Live Communication | WebRTC / WebSockets |
| OCR | AWS Textract or equivalent |
| Database | SQLite / Supabase |
| Cloud | AWS |
| Voice Summaries | ElevenLabs |

## Reliability and Security

- Every finding must have traceable supporting evidence.
- Detection scores must not be treated as definitive proof.
- Confirmed relationships must be separated from suspected matches.
- Live capture requires explicit permission.
- Live monitoring must have a visible indicator and stop control.
- Raw live media should not be retained by default.

## Implementation Priorities

**Core MVP:** Screenshot investigation, OCR, claim extraction, source discovery, comparison, evidence storage and reporting.

**Live MVP target:** A limited webcam and microphone analysis workflow.

**Stretch goals:** External livestream ingestion, advanced deepfake analysis and specialized voice-cloning detection.

*This document describes the proposed architecture. Components and integrations remain subject to implementation testing.*
