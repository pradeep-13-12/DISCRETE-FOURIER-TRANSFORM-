# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
To Obtain DFT using Direct and FFT of a given sequence in SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
DISCRETE FOURIER TRANSFORM USING DIRECT METHOD
```
clc;
clear;

N = input("Length of the sequence N: ");
x = input("Input sequence x(n): ");

if length(x) <> N then
   error("Length of x(n) must be equal to N");
end

X_direct = zeros(1, N);

for k = 0:N-1
   sum_val = 0;
   for n = 0:N-1
       sum_val = sum_val + x(n+1)*exp(-%i*2*%pi*k*n/N);
   end
   X_direct(k+1) = sum_val;
end

X_direct = clean(X_direct);

disp("DFT using Direct Method:");
disp(X_direct);

mag = abs(X_direct);
phase = atan(imag(X_direct), real(X_direct));

disp("Magnitude Spectrum:");
disp(mag);

disp("Phase Spectrum (radians):");
disp(phase);

k = 0:N-1;
clf;

subplot(2,1,1);
plot2d3(k, mag);
title("Magnitude Spectrum of DFT");
xlabel("k");
ylabel("|X(k)|");

subplot(2,1,2);
plot2d3(k, phase);
title("Phase Spectrum of DFT");
xlabel("k");
ylabel("∠X(k) (rad)");
```
DISCRETE FOURIER TRANSFORM USING FFT ALGORITHM
```
clc;
clear;

N = input("Length of the sequence N: ");
x = input("Enter input sequence x(n): ");
if length(x) <> N then
    error("Length of x(n) must be equal to N");
end

X_fft = fft(x);

disp("DFT using FFT:");
disp(X_fft);

mag = abs(X_fft);
phase = atan(imag(X_fft), real(X_fft));

disp("Magnitude Spectrum:");
disp(mag);

disp("Phase Spectrum (radians):");
disp(phase);

k = 0:N-1;
clf;

subplot(3,1,1);
plot2d3(0:N-1, x);
title("Input Sequence x(n)");
xlabel("n");
ylabel("Amplitude");

subplot(3,1,2);
plot2d3(k, mag);
title("Magnitude Spectrum");
xlabel("k");
ylabel("|X(k)|");

subplot(3,1,3);
plot2d3(k, phase);
title("Phase Spectrum");
xlabel("k");
ylabel("∠X(k) (rad)");
```

# OUTPUT: 
DISCRETE FOURIER TRANSFORM USING DIRECT METHOD

<img width="543" height="514" alt="image" src="https://github.com/user-attachments/assets/1f6838f5-4fd1-42b2-96ff-b212932ec0f7" /> 

<img width="510" height="514" alt="image" src="https://github.com/user-attachments/assets/788385fc-f7af-4721-abe5-893b88e82ce3" />

DISCRETE FOURIER TRANSFORM USING FFT ALGORITHM

<img width="465" height="353" alt="image" src="https://github.com/user-attachments/assets/9bc4910b-6155-481a-bf4d-712cd59c0415" />

<img width="474" height="435" alt="image" src="https://github.com/user-attachments/assets/4374da2f-abad-4966-96bc-1f24da0d1bb4" />

# RESULT: 
Thus, the Discrete Fourier Transform using Direct and Fast Fourier Transform of the given sequence were obtained and its magnitude and phase spectrum were plotted.
