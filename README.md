# PENJELASAN PROGRAM 
      
      clc;
      clear;

      T = 1;
      t = 0:0.1:15;
      u = sin(2*pi*0.2*t);
      Kp = 1;
      Ki = 1;
      % Ki = 3;
      % Ki = 5;
      % Ki = 7;
      % Ki = 9;

Program diatas berfungsi untuk membersihkan output command window dan memori ketika di run. Kemudian mendeklarasikan dan menginisialisasi nilai T, t, u, Kp, dan Ki.

      num = [T];
      den = [T T/16 1];
      sys = tf(num,den)

      C = tf([Kp Ki],[1 0]);

Membuat tranfer function dengan numerator dan denominator seperti soal pada eLok. Membuat variabel C sebagai variabel kontrol PI.

      complete = feedback(sys*C,1);

Selanjutnya variabel-variabel tersebut akan dikalikan tanpa feedback dan dimasukan kedalam variabel complete.

Sistem akan diuji dengan input step, impulse, dan ramp dengan memvarasikan nilai dari Ki.

      subplot(311), step(complete);
      subplot(312), impulse(complete);
      subplot(313), lsim(complete,u,t);

      stepinfo(complete)

# UJI SISTEM

Untuk Kp = 1

| Parameter | Ki = 1  | Ki = 3  | Ki = 5  | Ki = 7  | Ki = 9  |
| --- | --- | --- | --- | --- |  ---  |
| Rise time | NaN | NaN | NaN | NaN | NaN | 
| Settling time | NaN | NaN | NaN | NaN | NaN |
| Overshoot | NaN | NaN | NaN | NaN | NaN | NaN |
| SSE | --- | --- | --- | --- | --- |

Untuk Kp = 1 dan Ki = 1

![image](https://user-images.githubusercontent.com/68903409/190057955-12402820-10ab-422a-a082-bf5b7c25c8a1.png)

Untuk Kp = 1 dan Ki = 3

![image](https://user-images.githubusercontent.com/68903409/190058097-e4450244-102f-4546-9c27-dd06291a94af.png)

Untuk Kp = 1 dan Ki = 5

![image](https://user-images.githubusercontent.com/68903409/190058162-3a18a479-8a7a-4004-be8d-dbcf817959ee.png)

Untuk Kp = 1 dan Ki = 7

![image](https://user-images.githubusercontent.com/68903409/190058239-f3c70a65-d734-4242-8dc1-f26709cb4731.png)

Untuk Kp = 1 dan Ki = 9

![image](https://user-images.githubusercontent.com/68903409/190058298-2c5e938d-0241-4266-8a38-0fe37806b004.png)
