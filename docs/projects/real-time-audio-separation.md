````markdown
# Real-Time Audio Separation of Human Voices

**Summary:** Real-time source separation project combining embedded Teensy audio acquisition (I2S), UART streaming, Raspberry Pi multicore processing, and a Python GUI for real-time playback and visualization. Demonstrates embedded audio capture, DSP algorithms, synchronization, and performance engineering.

**Problem:** Build a small-form-factor array to capture and separate human voices in real-time.

**Approach:** Implement low-latency audio capture on Teensy (I2S), transmit via UART to a Raspberry Pi, perform online ICA/FFT-based processing with multiprocessing, and provide a multithreaded Python GUI for playback/visualization.

**Results:** Working demo with real-time playback, written report and poster, performance tradeoffs documented.

---

### Skills demonstrated

- C/C++ on embedded platforms (I2S, UART), Python multiprocessing and multithreading
- Real-time DSP (FFT, ICA), FIR filtering (low-pass)
- Hardware synchronization using GPIO, performance tuning and profiling

### Why this is relevant to HARMAN

- **I2S/TDM Audio Capture**: Direct experience with I2S audio streaming, the core interface for automotive audio systems.
- **Embedded DSP**: Real-time FFT and ICA processing on constrained hardware mirrors work needed for audio processing in in-vehicle infotainment.
- **Real-time Multitasking**: Managed multiprocessing/multithreading with strict latency and synchronization constraints.
- **System Integration**: Integrated multiple embedded platforms with careful timing and interface validation.

### How to run / reproduce

Hardware:

- Teensy boards with Audio Shield (or equivalent), a Raspberry Pi (4 recommended), microphones (or test audio), and a UART connection between Teensy and Pi.

Quick steps:

- Run the self-contained demo: open `src_computer_runnable_demo/` and follow its README.
- On the Raspberry Pi (or laptop):
  - Create a Python virtualenv and install dependencies: `pip install numpy scipy matplotlib pyaudio`
  - Run:

```bash
python3 src/multiproc_cogent.py
python3 src/ui3_1_maxplayback.py
```

- On each Teensy: flash `src/valuecheck.ino` (use Arduino IDE / Teensy Loader) and set I2S/UART parameters as described in `OVERVIEW.txt`.

### What I'd improve next

- **Latency Budget**: Quantify and optimize the end-to-end latency budget (currently limited by UART bandwidth).
- **Buffering Strategy**: Implement circular buffering to reduce jitter and dropouts.
- **Test Strategy**: Add automated regression tests for the DSP blocks.

### Downloads

- [Final report (PDF)](../assets/real-time-audio-separation/2021-Team-2-final.pdf){:target="_blank"}
- [Slide deck (PDF)](../assets/real-time-audio-separation/2021-Team-2-slides.pdf){:target="_blank"}
- [Poster (PDF)](../assets/real-time-audio-separation/2021-Team-2-poster.pdf){:target="_blank"}
- [Demo video (MP4)](../assets/real-time-audio-separation/slide10_video1_final_demo.mp4){:target="_blank"}
- [Runnable demo (zip)](../assets/real-time-audio-separation/real-time-demo.zip){:target="_blank"}

### What to inspect

- See the **Final report** for design decisions, synchronization approach, and performance analysis.
- Play the **Demo video** for the live system behavior and slide commentary.
- Download the **Runnable demo** to run the self-contained demo locally (instructions in `USAGE.txt`).
- Inspect `src/valuecheck.ino` for Teensy I2S/UART firmware and `src/multiproc_cogent.py` for the Python multiprocessing implementation.
````