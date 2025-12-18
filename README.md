# 🎵 Audio Noise Removal Project

## 👋 What is this project?

Have you ever listened to an audio recording that was ruined by a loud, high-pitched buzzing sound? This project fixes that!  

I wrote a **Python program** that takes a noisy audio file, identifies the annoying "beeping" tones, and surgically removes them **without ruining the voice recording underneath**. It turns a messy, noisy file into clear, understandable speech.

---

## 🎧 The Problem

I started with a file called `SunShineSquare.wav`. It contains a person speaking, but you can barely hear them because there are **three loud, artificial tones** covering up their voice.  

**Goal:** Find the exact frequencies of these noises and remove them.

---

## ⚙️ How It Works

I used **Digital Signal Processing (DSP)** techniques. Here’s the step-by-step breakdown:

### 1. Seeing the Sound (Spectrogram)

You can't fix what you can't see. First, I converted the audio into a visual graph called a **spectrogram**.  

- **Before:** Three bright horizontal lines appear, these are the annoying noises.  
- **After:** The lines are gone, leaving only the voice.

### 2. Building the Filter

I created a **FIR Notch Filter**, which is like a pair of tweezers designed to grab only specific frequencies.  

The three bad frequencies were approximately:  
0.2857π, 0.5709π, 0.8573π
### 3. The Math Behind It

To remove a specific tone, I used this formula to create the notch filter:  

\[
H(z) = 1 - 2\cos(\omega_0) z^{-1} + z^{-2}
\]

- Built **three filters** (one for each noise)  
- Combined them into a single "super-filter" using **convolution**  
- Applied the filter to the audio to remove all unwanted tones

---

## 💻 How to Run

1. Clone the repository:

```bash
git clone https://github.com/NinaAmini/Tones-Removal-in-Audio-Signals.git
cd Tones-Removal-in-Audio-Signals




