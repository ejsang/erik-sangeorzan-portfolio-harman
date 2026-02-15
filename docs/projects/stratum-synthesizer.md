````markdown
# Stratum Synthesizer (Assembly)

**Summary:** A hand-crafted audio synthesizer implemented largely in assembly with low-level drivers for speaker output, SD card access, SDRAM, and touchscreen I/O - focused on efficiency and driver-level control.

**Problem:** Produce a functional synthesizer on constrained embedded hardware with multiple instrument voices and low-latency control.

**Approach:** Implement synthesis routines and driver code in assembly for tight control over timing and memory; build drivers for SD I/O and speaker output.

**Results:** Full synthesizer with multiple instruments and a touchscreen interface; source demonstrates low-level driver work and audio path implementation.

---

### Skills demonstrated

- Assembly-level optimization and hardware driver development
- Real-time audio signal generation and low-latency control
- Debugging constrained systems and interfacing with peripherals

### Why this is relevant to HARMAN

- Shows deep expertise in low-level embedded audio engineering: driver development for audio hardware (speaker output, peripheral interfaces), real-time constraints, and efficient use of constrained memory.
- Demonstrates understanding of audio signal path from synthesis through hardware interface—critical for automotive audio systems.

### Driver Interface Sketch

```c
// Pseudocode illustrating the driver interface logic implemented in assembly
// See 'speaker_driver.e' for the actual assembly implementation

void Audio_ISR(void) {
    // 1. Acknowledge Interrupt
    Clear_IRQ(AUDIO_IRQ_MASK);
    
    // 2. Check FIFO status
    if (!FIFO_Full(AUDIO_FIFO_ADDR)) {
        // 3. Fetch next sample from synthesis engine
        int16_t sample = Synth_GetNextSample();
        
        // 4. Write to hardware register
        Write_Reg(AUDIO_DATA_REG, sample);
    }
}
```

### How to run / reproduce

- **Target Hardware:** Nios II soft-core processor on DE1-SoC FPGA (Altera).
- **Toolchain:** See `Stratum Written Report.pdf` for details. The project was built and tested on the original target hardware.
- To run on target hardware:
  - Copy `combined.raw` to the root of an SD card used by the target board.
  - Load `test_top.e` (or `test_GUI.e` for interactive tests) as the main program using the course toolchain/toolchain loader.

### Downloads

- [Stratum Written Report (PDF)](../assets/stratum-synthesizer/Stratum Written Report.pdf){:target="_blank"}
- [Presentation (PPTX)](../assets/stratum-synthesizer/Stratum Presentation (download to avoid format issues).pptx){:target="_blank"}
- [Code (zip)](../assets/stratum-synthesizer/stratum-code.zip){:target="_blank"}

### What to inspect

- Read the **Stratum Written Report** for architecture and driver design notes.
- Inspect `speaker_driver.e`, `sd_read_driver.e`, and the `synth` modules inside the code zip to see low-level driver logic and instrument synthesis routines.
````