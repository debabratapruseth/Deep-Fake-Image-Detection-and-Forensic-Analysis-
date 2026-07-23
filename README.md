# Deep Fake Image Detection and Forensic Analysis SDK 

## Sample Report 

![Sample Report](https://github.com/debabratapruseth/Deep-Fake-Image-Detection-and-Forensic-Analysis/blob/main/Output%20Report.png)

## What the Pipeline Checks

1. Input Validation

Before any analysis begins, the pipeline verifies that the uploaded image is suitable for processing.

* Supported image format (JPG, JPEG, PNG, WebP)
* File size within limits
* Valid image structure (not a corrupted file)
* Acceptable image dimensions
* EXIF orientation correction
* RGB normalization
* Secure storage with a unique analysis ID

⸻

2. Image Quality Assessment

Poor-quality images can reduce the reliability of every downstream detector.

The pipeline evaluates:

* Blur (Laplacian variance)
* Brightness
* Contrast
* Percentage of very dark pixels
* Percentage of overexposed pixels
* Image resolution
* Overall quality score
* Suitability for further analysis

⸻

3. Face Analysis

Since deepfake models perform best on faces, the pipeline analyzes facial regions separately.

Checks include:

* Number of faces detected
* Face detection confidence
* Face size
* Face sharpness
* Face brightness
* Face contrast
* Face crop quality
* Primary face ranking
* Multiple-face detection
* Missing-face detection

⸻

4. Deepfake Classification

A pretrained vision model estimates whether the image resembles authentic or AI-generated examples.

Outputs include:

* Fake probability
* Real probability
* Prediction confidence
* Face-level predictions
* Full-image prediction
* Consistency across multiple faces
* Label validation

⸻

5. Compression & Image Forensics

Classical forensic techniques look for signs of editing or synthetic generation.

The pipeline performs:

* Error Level Analysis (ELA)
* JPEG recompression analysis
* Noise residual analysis
* Local noise consistency
* JPEG block boundary artifacts
* Compression inconsistency scoring
* Face-level forensic analysis

⸻

6. Frequency-Domain Analysis

The image is analyzed in the frequency domain using a Fast Fourier Transform (FFT).

Features include:

* Low-frequency energy
* Mid-frequency energy
* High-frequency energy
* Radial frequency profile
* Spectral slope
* Spectral entropy
* Directional energy
* Isolated spectral peaks
* Face-level frequency analysis

⸻

7. Metadata & Provenance

Metadata provides contextual clues about how an image was created or modified.

The pipeline checks:

* File hashes
* MIME type
* Image dimensions
* EXIF metadata
* Camera make and model
* Lens information
* Capture timestamps
* Software tags
* Editing software indicators
* Metadata completeness
* Metadata consistency

⸻

8. Evidence Fusion

Instead of trusting one detector, the pipeline combines multiple evidence sources.

It evaluates:

* Deepfake classifier score
* Compression & forensic score
* Frequency-domain score
* Metadata score
* Weighted risk score
* Adaptive weighting
* Evidence availability
* Evidence agreement
* Evidence conflict
* Number of corroborating signals

⸻

9. Decision Rules

The final assessment is based on explicit business rules rather than a single model prediction.

The pipeline determines:

* Manipulation risk score
* Confidence score
* Genuine
* Genuine – Digitally Enhanced
* Suspicious – Manual Review
* High Confidence AI Manipulation
* Missing evidence safeguards
* Manual review triggers

⸻

10. Explainability

Every decision is accompanied by an explanation of the supporting evidence.

The report identifies:

* Primary risk drivers
* Supporting evidence
* Counter evidence
* Informational evidence
* Confidence explanation
* Evidence diversity
* Contribution of each detector
* Analyst recommendations

⸻

11. LLM Report Generation

The LLM does not make the decision. It only converts validated evidence into a structured investigation report.

It is constrained to:

* Use only validated findings
* Preserve scores and decisions
* Avoid speculation
* Add no new evidence
* Produce a standardized analyst report

⸻

Summary

The final decision is based on a combination of independent evidence sources rather than a single AI model:

* ✅ Image validation
* ✅ Image quality assessment
* ✅ Face detection and quality
* ✅ Deepfake classifier predictions
* ✅ Error Level Analysis (ELA)
* ✅ JPEG recompression artifacts
* ✅ Noise consistency
* ✅ Frequency-domain (FFT) analysis
* ✅ Metadata and provenance checks
* ✅ Multi-signal evidence fusion
* ✅ Confidence and agreement scoring
* ✅ Rule-based decision engine
* ✅ Explainability layer
* ✅ LLM-generated analyst report (reporting only)
