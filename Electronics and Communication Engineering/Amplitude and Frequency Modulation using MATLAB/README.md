# Amplitude and Frequency Modulation using MATLAB  

## Project Overview  
This project demonstrates the generation of Amplitude Modulated (AM) and Frequency Modulated (FM) signals using MATLAB. Modulation is a fundamental technique in communication systems to transmit information efficiently over long distances by superimposing a message signal onto a high-frequency carrier wave.  

## Key Features  
- **Amplitude Modulation (AM)**: Varies the amplitude of the carrier signal based on the message signal.  
- **Frequency Modulation (FM)**: Varies the frequency of the carrier signal based on the message signal.  
- **Interactive Inputs**: Allows users to specify message frequency, carrier frequency, and modulation index.  
- **Visualization**: Plots the message signal, carrier signal, AM signal, and FM signal for comparison.  

## MATLAB Script  
```matlab  
clear all;  
close all;  
clc;  

% Time vector  
t = 0:0.001:1;  
set(0, 'defaultlinelinewidth', 2);  

% Input parameters  
A = 5;                          % Amplitude of signal  
fm = input('Message frequency = ');  % Message frequency  
fc = input('Carrier frequency = ');  % Carrier frequency (fc > fm)  
mi = input('Modulation Index = ');   % Modulation Index (≤1)  

% Message Signal  
Sm = A * sin(2 * pi * fm * t);  
subplot(4, 1, 1);  
plot(t, Sm);  
xlabel('Time');  
ylabel('Amplitude');  
title('Message Signal');  
grid on;  

% Carrier Signal  
Sc = A * sin(2 * pi * fc * t);  
subplot(4, 1, 2);  
plot(t, Sc);  
xlabel('Time');  
ylabel('Amplitude');  
title('Carrier Signal');  
grid on;  

% AM Signal  
Sfm = (A + mi * Sm) .* sin(2 * pi * fc * t);  
subplot(4, 1, 3);  
plot(t, Sfm);  
xlabel('Time');  
ylabel('Amplitude');  
title('AM Signal');  
grid on;  

% FM Signal  
F = cos(2 * pi * fc * t + (mi * sin(2 * pi * fm * t)));  
subplot(4, 1, 4);  
plot(t, F);  
xlabel('Time');  
ylabel('Amplitude');  
title('FM Signal');  
grid on;  
```  

## Input Parameters  
1. **Message Frequency (`fm`)**: Frequency of the baseband signal (e.g., 5 Hz).  
2. **Carrier Frequency (`fc`)**: Frequency of the high-frequency carrier signal (e.g., 10 Hz, must be > `fm`).  
3. **Modulation Index (`mi`)**: Determines the extent of modulation (must be ≤1 to avoid distortion).  

## Output Visualization  
The script generates four subplots:  
1. **Message Signal**: Original low-frequency signal carrying information.  
2. **Carrier Signal**: High-frequency signal used to transmit the message.  
3. **AM Signal**: Carrier signal with amplitude varying according to the message.  
4. **FM Signal**: Carrier signal with frequency varying according to the message.  

## Applications  
- **Broadcasting**: AM for radio, FM for high-fidelity audio.  
- **Telecommunications**: Mobile networks, satellite communication.  
- **Space Communication**: Transmitting signals between ground stations and spacecraft.  

## Getting Started  
1. **Run the Script**: Copy the provided MATLAB code into a script file (e.g., `modulation.m`).  
2. **Input Parameters**: Enter values for `fm`, `fc`, and `mi` when prompted.  
3. **Analyze Results**: Observe the generated signals in the MATLAB figure window.  

## Acknowledgments  
- **Amrita Vishwa Vidyapeetham, Chennai** for academic support.  
- **Dr. Manikandan A** faculty.
