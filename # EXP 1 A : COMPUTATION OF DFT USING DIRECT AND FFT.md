# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
x = [1, 2, 3, 4]; 
N = length(x);
X_dft = zeros(1, N);
for k = 1:N
    for n = 1:N
        WN = exp(-2 * %i * %pi * (k-1) * (n-1) / N);
        X_dft(k) = X_dft(k) + x(n) * WN;
    end
end

disp("DFT Result:");
disp(X_dft);
mag_dft = abs(X_dft);
phase_dft = atan(imag(X_dft), real(X_dft));
X_fft = fft(x, -1);  
mag_fft = abs(X_fft);
phase_fft = atan(imag(X_fft), real(X_fft));

disp("FFT Result:");
disp(X_fft);
clf;
subplot(2,2,1);
plot(mag_dft);
title("DFT Magnitude Spectrum");
xlabel("k"); ylabel("|X[k]|");

subplot(2,2,2);
plot(mag_fft);
title("FFT Magnitude Spectrum");
xlabel("k"); ylabel("|X[k]|");

subplot(2,2,3);
plot(phase_dft);
title("DFT Phase Spectrum");
xlabel("k"); ylabel("Phase (radians)");

subplot(2,2,4);
plot(phase_fft);
title("FFT Phase Spectrum");
xlabel("k"); ylabel("Phase (radians)");
```

# OUTPUT: 
<img width="915" height="697" alt="image" src="https://github.com/user-attachments/assets/245f4736-cbad-42a3-aa1c-0423fd11c5f1" />
<img width="1919" height="1063" alt="image" src="https://github.com/user-attachments/assets/f397e2be-0e74-461e-af78-747307a0962a" />


# RESULT: 
Thus,The DFT and FFT of the given sequence is obtained using SCILAB.
