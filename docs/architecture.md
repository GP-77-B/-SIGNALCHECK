# SIGNALCHECK — System Architecture

## Overview

SIGNALCHECK uses two AI agents, specialized media-forensics models and a shared evidence system to investigate digital information.

The platform has two investigation modes:

- **Upload & Investigate:** Analyze images, screenshots, videos, audio, documents and URLs.
- **Live Detection:** Analyze webcam and microphone feeds or supported external livestreams.

Both modes connect to the same investigation engine and generate evidence-backed reports.

## 1. AI Agents

### Gemini — Media Investigator

Our primary multimodal AI agent.

Responsibilities:
- Analyze images, videos and audio.
- Extract claims and important information.
- Understand media context.
- Identify potentially suspicious content.
- Plan and coordinate investigations.
- Process live audio and sampled video frames through Gemini Live.

### Groq — Evidence Reviewer

Our second AI agent, working alongside Gemini.

Responsibilities:
- Independently review extracted claims and transcripts.
- Analyze findings from media-forensics models.
- Identify inconsistencies and potential misinformation.
- Organize collected evidence.
- Generate investigation summaries and structured reports.

Both agents can process independent tasks in parallel. Their findings are combined before the final report is generated.

## 2. Specialized Media-Forensics Models

These models perform specific detection tasks rather than general AI reasoning.

| Model | Purpose |
|---|---|
| XDFDet | Video face-deepfake detection |
| VeriSpoof-Plus | Synthetic speech and voice-cloning analysis |
| Ceendi Deepfake Audio Detector | Alternative lightweight audio detection |

Additional image-manipulation detection capabilities will be evaluated separately using suitable forensic models and services.

**Model selection is provisional.** Performance, hardware requirements and licensing must be evaluated before integration.

## 3. Upload & Investigate

1. User uploads digital content.
2. The backend processes the submitted file.
3. OCR extracts text where necessary.
4. Gemini analyzes the content and extracts claims.
5. Specialized models examine relevant media for manipulation indicators.
6. The investigation agent searches for original and related sources.
7. Browser automation inspects relevant webpages.
8. Groq reviews the extracted claims and investigation findings.
9. The Evidence Engine stores the results.
10. SIGNALCHECK generates the final investigation report.

## 4. Live Detection

### Webcam and Microphone

1. User grants camera and microphone permission.
2. The browser captures live audio and video.
3. Audio segments and sampled video frames are streamed to the backend.
4. Gemini Live analyzes supported incoming media.
5. Specialized detection models examine available audio and video segments.
6. Groq reviews available transcripts and findings.
7. The dashboard displays timestamped analysis results.

### External Livestreams

1. User supplies an accessible and authorized stream.
2. The backend receives the supported stream.
3. FFmpeg extracts audio segments and video frames.
4. Gemini and specialized models analyze the processed media.
5. Groq reviews the findings and relevant claims.
6. Results are stored with timestamps for investigation.

## 5. MCP — Investigation Tools

MCP provides standardized access to the tools used by our investigation agents.

Planned tools:

- `search_sources` — Search for relevant online publications.
- `inspect_webpage` — Open and inspect webpages.
- `extract_evidence` — Collect relevant passages and metadata.
- `compare_content` — Compare documents and content versions.
- `archive_lookup` — Search for available historical webpage versions.
- `save_evidence` — Store investigation findings.

The backend coordinates agent requests and MCP tool execution.

Browser navigation is handled through Playwright.

## 6. Evidence Engine

The Evidence Engine collects and organizes findings from both AI agents and specialized detection models.

It stores:

- Submitted content references.
- Extracted claims and transcripts.
- Source URLs and relevant excerpts.
- Evidence collection timestamps.
- Media-analysis results and detector information.
- Content comparisons.
- Relationships between claims and sources.
- Live-media timestamps and flagged segments.

**Proposed database:** SQLite for the initial MVP, with Supabase as a possible future alternative.

The collected relationships power the Evidence Journey Graph.

## 7. Final Investigation Report

The report brings together:

- Submitted content.
- Extracted claims.
- Image, video and audio analysis.
- Potential manipulation indicators.
- Original and related sources.
- Evidence Journey Graph.
- Publication timeline.
- Claim-level findings.
- Supporting citations.
- Confidence and unresolved questions.

## 8. Proposed Technology Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js / React |
| Backend | Python / FastAPI |
| Primary AI Agent | Gemini API |
| Secondary AI Agent | Groq API |
| Live AI Processing | Gemini Live API |
| Media Forensics | XDFDet / VeriSpoof-Plus candidates |
| OCR | AWS Textract |
| Agent Tool Integration | MCP |
| Browser Automation | Playwright |
| Video and Audio Processing | FFmpeg |
| Device Media Capture | WebRTC / Browser Media APIs |
| Live Communication | WebSockets |
| Evidence Storage | SQLite |
| Voice Summaries | ElevenLabs |

## 9. Reliability and Security

- Every finding must be linked to supporting evidence.
- AI-generated conclusions must not be treated as verified facts.
- Media detection scores are indicators, not definitive proof.
- Confirmed source relationships must be separated from suspected similarities.
- Live media capture requires explicit user permission.
- Raw recordings should not be stored by default.
- API credentials must remain on the backend.
- Uploaded files and external webpages must be treated as untrusted input.

## 10. Implementation Priorities

**Core MVP**
- Screenshot and image uploads.
- OCR and claim extraction.
- Gemini and Groq agent workflow.
- Browser-based source investigation.
- MCP investigation tools.
- Evidence storage and content comparison.
- Evidence Journey Graph and report generation.

**Live MVP Target**
- Webcam and microphone capture.
- Limited live audio and sampled-frame analysis.
- Timestamped investigation events.

**Stretch Goals**
- External livestream ingestion.
- Advanced video deepfake detection.
- Voice-cloning detection.
- Advanced image manipulation detection.
- Spoken report summaries through ElevenLabs.

---

**Project:** SIGNALCHECK  
**Track:** Track 2 — Beyond the Browser  
**Status:** Proposed architecture — wHACKiest 2026

*All technologies and models listed are proposed components. Their actual integration and performance will be evaluated during development.*
