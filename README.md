Project Briefing: ESP32-C3 Real-Time Audio Visualizer
Project Name: "AudioSpectrum 8" or "SoundPulse EQ"
(Choose your favorite or mix: AudioLoom, WaveEyes, MicViz, EchoBars, SonicScope)

What It Does
A compact real-time audio visualizer that reads sound from a microphone sensor and displays 8 independent vertical bars on an LCD1602 screen. Each bar responds to different frequency bands (bass to treble), creating a live equalizer effect that moves with your music or ambient sound.

Hardware Requirements
Component	Specification
Microcontroller	ESP32-C3 (XIAO or any variant)
Display	LCD1602 with I2C backpack
Sound Sensor	Analog microphone module (MAX4466, KY-038, or LM393)
Wiring	SDA→GPIO7, SCL→GPIO6, Sound OUT→GPIO0
How It Works (The Logic)
Sample Audio → Reads analog values from microphone (100+ samples per cycle)

Detect Frequency → Measures zero-crossings to estimate pitch (20Hz - 6kHz)

Map to 8 Bars → Each bar targets a specific frequency range:

Bars 0-2: Bass (drums, bass guitar)

Bars 3-4: Mids (vocals, guitar)

Bars 5-7: Treble (cymbals, hi-hats, whistles)

Apply Envelope → Fast attack (bars rise instantly), slower release (bars fall gracefully)

Display on LCD → 8 custom characters show bar height (0-7 levels) + frequency readout

Key Features
Real-time frequency detection - bars respond to pitch, not just volume
Attack/Release smoothing - natural, LED-like VU meter feel
Auto-ranging - adapts to quiet and loud environments
Peak hold indicator - shows strongest recent signal
Low latency - 30-50ms display refresh
