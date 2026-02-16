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

- Shows low-level embedded audio engineering and driver development experience (Speaker PWM, SD Card SPI, Touchscreen I2C) important for firmware that directly handles audio devices and peripheral interfaces.

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
