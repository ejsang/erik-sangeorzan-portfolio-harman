```markdown
# Analyzing Tennis Matches Based on Audio (MATLAB)

**Summary:** A signal processing project using MATLAB to analyze audio from tennis matches to detect ball hits, identify "out" calls vs. applause, and track game score automatically.

**Problem:** Automate the tracking of tennis match events and scoring using only audio cues.

**Approach:** Developed MATLAB algorithms to detect transients (ball hits), spectral features for applause vs. net hits, and implemented a state machine to track scoring.

**Results:** Successfully detected ball hits and applause in test clips; identified limitations in net hit detection for specific rallies.

---

### Skills demonstrated

- Audio Signal Processing (MATLAB)
- Algorithm Development (transient detection, spectral analysis)
- State Machine Logic for scoring

### Why this is relevant to HARMAN

- Demonstrates core DSP algorithm development: transient detection, spectral analysis, and feature extraction—skills directly transferable to automotive audio processing systems.
- Shows experience in prototyping audio signal processing algorithms before implementation.

### Project website

For a detailed breakdown of the methodology and results, visit the **[project website](https://ejsang.wixsite.com/eecs351project){:target="_blank"}**.

### Limitations & Fix Plan

- **Limitation:** The current algorithm misses a net hit in Rally 4, causing a scoring drift in subsequent events.
- **Fix Plan:** Implement a stricter spectral template match for "net hits" to distinguish them from similar short-duration transients.
- **Verification:** Add unit tests with synthetic "net hit" audio clips to verify detection thresholding.

### How to run / reproduce

- Requirements: MATLAB.
- Run `main.m` in MATLAB.
- The script analyzes the audio, prints the game score to the console, and generates plots for detected events.

### Downloads

- [Code (zip)](../assets/tennis-audio-analysis/tennis-audio-code.zip){:target="_blank"}

### What to inspect

- Check `findBallHit.m` to see the transient detection logic.
- See `main.m` for the integration of detection algorithms into the game loop.

```