# Multi-Resolution Spectral Analysis

This project explores the trade-off between **time** and **frequency resolution** in spectral analysis using the **Short-Time Fourier Transform (STFT)** and introduces a multi-resolution approach for better handling different types of sounds.

---

## About STFT

The **Short-Time Fourier Transform (STFT)** analyzes signals by dividing them into overlapping frames (windows) and applying the Fourier Transform to each frame. It provides a time-varying frequency spectrum but is fundamentally limited by a trade-off:  
- **short windows → good time resolution, poor frequency resolution**  
- **long windows → good frequency resolution, poor time resolution**

---

## Why Temporal and Spectral Resolution Matter

Both **temporal resolution** (ability to detect when a change happens) and **spectral resolution** (ability to distinguish close frequencies) are critical in analyzing real-world sounds.  
A fixed window size in STFT forces a compromise — you can't optimize both at the same time.

---

## STFT Limitation →  My Approach

Since STFT with a single window can't balance both resolutions, this project adopts a **multi-resolution analysis**:  
-> It compute STFTs at **three different window sizes** (small, medium, large) for the same signal.  
-> Each window emphasizes either time or frequency resolution.  
-> The spectra are combined to give a richer representation — capturing **transient** and **sustained** features together.

This approach allows better visualization and partial tracking across sounds with mixed characteristics.

---

## Sounds Used

It was tested on two contrasting audio samples:

1. **Harmony of Peace – Angel Voices** (~88.8 sec)  
   - **Spectral Characteristics:** Clear melodic content with stable harmonic bands (visible horizontal lines).  
   - **Nature:** Tonal, voice-like with sustained frequencies → emphasizes **frequency resolution**.

2. **MD1TRK22** (~59.5 sec)  
   - **Spectral Characteristics:** Broad, short-duration energy bursts spread over time and frequency.  
   - **Nature:** Percussive, transient-rich → emphasizes **time resolution**.

---

## Observations

also the **Constant-Q Transform (CQT)** was tested on these signals.  
➡️ **CQT performed poorly on the percussive sound (MD1TRK22)** — it smeared transients in time.  
➡️ In contrast, **multi-window STFT approach handled both tonal and percussive sounds reasonably well**, maintaining clarity in both sustained harmonics and sharp transients.

---

## Running the Code

Two Jupyter notebooks have been uploaded. Both are the same, except they are applied to different sounds, to avoid cluttering everything into a single notebook file. And the two sounds that were used has also been uploaded.

