# SIGNALCHECK — Research & Existing Solutions

## 1. Why This Project?

Digital content can be manipulated, generated using AI or shared without its original context.

Google's research with fact-checking organizations reviewed over 130,000 fact-checks dating back to 1995. It found that 80% involved photos or videos, while video accounted for 48% of misinformation claims in the last three years.

Source: https://newsinitiative.withgoogle.com/resources/trainings/fact-check-explorer/

*These figures describe Google's analyzed fact-check dataset, not all misinformation worldwide.*

## 2. Existing Solutions

### InVID / WeVerify
Provides image and video verification tools, including reverse image search, video keyframes, metadata inspection and forensic filters.

https://www.invid-project.eu/tools-and-services/invid-verification-plugin/

### Google Fact Check Explorer
Helps users find existing fact-checks by searching claims and images.

https://toolbox.google.com/factcheck/

### Internet Archive — Wayback Machine
Allows users to inspect available historical versions of webpages and compare publication history.

https://web.archive.org/

### C2PA Content Credentials
A digital provenance standard that helps verify the integrity and origin information associated with digital media.

https://spec.c2pa.org/

Important: Valid provenance does not automatically mean that the content is factually true.

## 3. What We Aim to Add

SIGNALCHECK aims to connect several investigation activities into one guided workflow:

- Upload-based image, video and audio investigation.
- Live webcam, microphone and supported livestream analysis.
- AI-assisted claim extraction and evidence review.
- Original-source discovery and content comparison.
- Connections between media findings and online sources.
- An Evidence Journey Graph.
- A unified investigation report.

Our differentiation is the combination and presentation of these investigations, not the invention of individual forensic techniques.

## 4. Proposed Technical Resources

| Technology | Intended use |
|---|---|
| Gemini | Multimodal analysis and investigation agent |
| Groq | Evidence review and report generation |
| MCP | Shared investigation tools |
| Playwright | Browser-based research |
| FFmpeg | Audio and video processing |
| XDFDet | Candidate video deepfake detector |
| VeriSpoof-Plus | Candidate synthetic speech detector |
| AWS | Cloud and document processing |
| ElevenLabs | Spoken report summaries |

These are proposed technologies. Model performance, licensing, API access and implementation feasibility must be checked before integration.

## 5. Known Limitations

- No deepfake detector can guarantee perfect results.
- Similar images or wording do not prove that one source copied another.
- Historical webpage archives are incomplete.
- C2PA credentials establish provenance information, not factual truth.
- Private WhatsApp forwarding histories cannot be reconstructed without access to the relevant records.
- Live media analysis depends on streaming quality, processing time and model availability.

## 6. Our Research Direction

SIGNALCHECK aims to make digital media investigation more accessible by bringing media analysis, browser-based research and evidence tracking together.

Our goal is to help users understand:

1. What does this content claim?
2. Does the media show signs of manipulation?
3. Where else has this information appeared?
4. Which sources support or contradict it?
5. What can actually be established from the available evidence?

**Project:** SIGNALCHECK  
**Recommended Track:** Track 2 — Beyond the Browser  
**Hackathon:** wHACKiest 2026

*Research and technical decisions are subject to further evaluation during development.*
