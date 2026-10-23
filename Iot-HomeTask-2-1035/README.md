The ESP32 LEDC has timers, and each PWM channel is tied to a timer. Channels sharing a timer share the same frequency and resolution.
So two LEDs with different frequencies must use different timers.
Arduino-ESP32 core 2.x: channels map to timers in pairs (0 and 1 share timer 0, 2 and 3 share timer 1, and so on). I use channel 0 and channel 2 so they land on different timers.
Core 3.x: ledcAttach(pin, freq, res) allocates timers automatically, so different frequencies get different timers.
Resolution limit: freq × 2^resolution ≤ 80 MHz. At 5000 Hz, the maximum is 13 bits. I use 10 bits (0–1023) for both, which is valid at 1 kHz and 5 kHz.
The original ESP32 has 8 timers and 16 channels. S2/S3/C3 variants have fewer (low-speed only), but 2 timers is still fine.
The code below works with both core 2.x and 3.x.