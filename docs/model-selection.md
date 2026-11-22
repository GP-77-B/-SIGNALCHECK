# SIGNALCHECK — AI Model Selection

## Main AI Agents

**Gemini API — Media Investigator**
- Multimodal content understanding
- Claim extraction
- Investigation planning
- Live media interaction

**Groq API — Evidence Reviewer**
- Independent claim analysis
- Transcript analysis
- Evidence review
- Investigation report generation

## Specialized Forensic Models

### 1. XDFDet
Purpose: Video face-deepfake detection.

- EfficientNet-B4
- Grad-CAM visual explanations
- Candidate for recorded video analysis
- Research/noncommercial license

Model: https://huggingface.co/mertkayacs/xdfdet

### 2. VeriSpoof-Plus
Purpose: Synthetic speech and voice-cloning detection.

- Speech authenticity analysis
- Synthetic speech localization
- Potential source comparison between recordings
- Requires GPU resources
- Noncommercial license

Model: https://huggingface.co/AustinXiao/VeriSpoof-Plus

### Alternative: Ceendi Audio Detector

A lighter ONNX-based audio detection option for comparison and experimentation.

Model: https://huggingface.co/Ceendi/deepfake-audio-detector

Research and education use only.

## Investigation Infrastructure

**MCP:** Shared access to search, webpage inspection, evidence extraction and document comparison tools.

**Evidence Engine:** SQLite-based evidence storage and relationship management.

## Important Limitations

- Deepfake models do not detect every form of media manipulation.
- Detection results are indicators, not definitive proof.
- Model performance must be evaluated on independent test samples.
- Model licenses must be reviewed before commercial use.
- Real-time detection requires separate latency and streaming tests.

*All listed models are proposed candidates. Final selection depends on testing, available hardware and integration feasibility.*
