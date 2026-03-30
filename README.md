# EXPT 2B:CIRCULAR-CONVOLUTION-USING-DFT
## AIM
To perform and verify circular convolution operation of two given sequences using SCILAB.
## APPARATUS REQUIRED
PC installed with SCILAB
## PROGRAM:
## CIRCULAR CONVOLUTION
```
clc;
clear;
x = [1 1 1 1];
n1 = 0:1:length(x)-1;
subplot(3,1,1);
plot2d3(n1,x);
xlabel('time');
ylabel('amplitude');
title('input sequence');
h = [1 2 3];
n2 = 0:1:length(h)-1;
subplot(3,1,2);
plot2d3(n2,h);
xlabel('time');
ylabel('amplitude');
title('impulse sequence');
N1 = length(x);
N2 = length(h);
N = max(N1,N2);
N3 = N1 - N2;
if (N3 > 0) then
    h = [h, zeros(1,N3)];
else
    x = [x, zeros(1,abs(N3))];
end
disp(x)
disp(h)
for n = 1:N
    y(n) = 0;
    for i = 1:N
        j = n - i + 1;
        if (j <= 0) then
            j = N + j;
        end
        y(n) = y(n) + x(i) * h(j);
    end
end
disp(y)
n = 0:N-1;
subplot(3,1,3);
plot2d3(n,y);
xlabel('time');
ylabel('amplitude');
title('circular convolution');
```
### CALCULATIONS:
<img width="1391" height="853" alt="image" src="https://github.com/user-attachments/assets/78ff7d0b-d006-4a4d-a7ea-d25581de1237" />

### SAMPLE OUTPUT:
<img width="1920" height="1200" alt="Screenshot 2026-02-09 091120" src="https://github.com/user-attachments/assets/535fedf9-7ebc-42e2-a42b-ad1f42eecd5f" />


## RESULT:
Thus, the circular convolution of the two given sequences were performed and its result was verified.
