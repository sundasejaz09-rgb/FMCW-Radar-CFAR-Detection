
FMCW Radar Target Detection using CFAR Algorithm
Contents
1. Introduction	1
2. Objectives	1
3. Methodology	1
3.1 FMCW Signal Generation	1
3.2 Signal Mixing	1
3.3 Range Estimation	2
3.4 Doppler Processing	2
3.5 CFAR Detection	2
4. CFAR Algorithm	2
5. Results	2
6. Applications	2
7. Conclusion	3


1. Introduction
Radar systems are widely used in defense, aviation, and autonomous systems for detecting and tracking objects. Frequency Modulated Continuous Wave (FMCW) radar is commonly used due to its high accuracy in range and velocity estimation.
This project focuses on implementing an FMCW radar system and enhancing detection performance using the Constant False Alarm Rate (CFAR) algorithm.

2. Objectives

•	To simulate FMCW radar waveform
•	To estimate target range using FFT
•	To generate Range-Doppler Map
•	To implement CFAR for noise reduction and target detection


3. Methodology
3.1 FMCW Signal Generation
A chirp signal is generated whose frequency increases linearly with time.

3.2 Signal Mixing
The transmitted and received signals are mixed to produce a beat signal.

3.3 Range Estimation
Fast Fourier Transform (FFT) is applied to determine target distance.

3.4 Doppler Processing
2D FFT is used to estimate velocity and generate Range-Doppler Map.

3.5 CFAR Detection
CFAR algorithm is applied to dynamically calculate threshold based on noise.

4. CFAR Algorithm
CFAR uses surrounding cells (training cells) to estimate noise and applies a threshold:
•	Training Cells → Noise estimation
•	Guard Cells → Protect target signal
•	Threshold → Adaptive decision

5. Results
•	Range FFT shows peak at target distance
•	Range-Doppler Map visualizes velocity and distance
•	CFAR removes noise and detects actual target

6. Applications
•	Military radar systems
•	Air traffic control
•	Autonomous driving
•	Surveillance systems



7. Conclusion
The project successfully demonstrates FMCW radar simulation and CFAR-based detection. The system effectively identifies targets while minimizing false alarms, making it suitable for real-world radar applications.
