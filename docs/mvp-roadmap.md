# SIGNALCHECK — MVP Roadmap

## Goal

Build a working prototype of SIGNALCHECK within 24 hours, focusing on multimedia investigation, source discovery and evidence-based reporting.

## 1. Core Features

These are the primary features we will prioritize.

### Upload & Investigate
- Upload images and screenshots.
- Extract text and claims using OCR and AI.
- Analyze image content.
- Search for original and related sources.
- Compare submitted content with discovered sources.
- Generate an investigation report.

### AI Investigation
- Gemini acts as the Media Investigator.
- Groq acts as the Evidence Reviewer.
- Both agents examine relevant information and contribute to the investigation.
- Findings are combined before generating the final report.

### Evidence Management
- Store source links and relevant excerpts.
- Record evidence timestamps.
- Connect claims with supporting or contradictory sources.
- Display relationships through the Evidence Journey Graph.

## 2. Live Detection

### Initial Live Target
- Webcam and microphone access with user permission.
- Capture sampled video frames and audio segments.
- Analyze available media using supported AI services.
- Display timestamped analysis events.

### Additional Live Capabilities
- External livestream ingestion.
- Live video deepfake analysis.
- Live voice-cloning detection.

These capabilities depend on available models, infrastructure and processing limits.

## 3. Stretch Goals

- Advanced image manipulation detection.
- Video face-deepfake detection using XDFDet.
- Synthetic speech detection using VeriSpoof-Plus or an alternative.
- External livestream analysis.
- ElevenLabs-powered spoken reports.
- More detailed investigation timelines.

## 4. Development Priorities

| Priority | Component |
|---|---|
| High | Image upload and OCR |
| High | Claim extraction |
| High | Browser-based source discovery |
| High | Evidence collection |
| High | Investigation report |
| High | Evidence Journey Graph |
| Medium | Two-agent investigation workflow |
| Medium | Limited live webcam/microphone analysis |
| Stretch | External livestream processing |
| Stretch | Advanced deepfake and voice detection |

## 5. Reliability

- No unsupported true/false verdicts.
- Every finding should have traceable evidence.
- Detection scores are indicators, not proof.
- Unverified claims must remain unverified.
- Live monitoring requires explicit user permission.

## 6. Demonstration Scenario

A user uploads a suspicious university announcement.

SIGNALCHECK extracts its claims, searches for the official publication, compares the wording, records supporting evidence and produces an investigation report.

The demonstration may also showcase a limited live-media analysis workflow if successfully integrated.

## 7. Success Criteria

The MVP should demonstrate at least one complete investigation from content submission to an evidence-backed report.

The objective is a functional, explainable investigation workflow rather than a collection of disconnected AI features.

**Project:** SIGNALCHECK  
**Hackathon:** wHACKiest 2026  
**Development Window:** 24 hours

*This roadmap describes planned development priorities, not implemented capabilities.*
