# NVIDia Jetson Nano hashcat

This fork has a patch so it gets around the CUDA 10.0 that comes with the
Jetson Nano OS image.

Sample benchmark results

```
# ./hashcat -b
hashcat (v5.1.0-1340-ge6d69eba+) starting in benchmark mode...

Benchmarking uses hand-optimized kernel code by default.
You can use it in your cracking session by setting the -O option.
Note: Using optimized kernel code limits the maximum supported password length.
To disable the optimized kernel code in benchmark mode, use the -w option.

clGetPlatformIDs(): CL_PLATFORM_NOT_FOUND_KHR

* Device #1: WARNING! Kernel exec timeout is not disabled.
             This may cause "CL_OUT_OF_RESOURCES" or related errors.
             To disable the timeout, see: https://hashcat.net/q/timeoutpatch
CUDA API (CUDA 10.0)
====================
* Device #1: NVIDIA Tegra X1, 3964 MB, 1MCU

Benchmark relevant options:
===========================
* --optimized-kernel-enable

Hashmode: 0 - MD5

Speed.#1.........:   561.9 MH/s (56.24ms) @ Accel:512 Loops:64 Thr:1024 Vec:8

Hashmode: 100 - SHA1

Speed.#1.........:   196.7 MH/s (81.98ms) @ Accel:128 Loops:128 Thr:1024 Vec:1

Hashmode: 1400 - SHA2-256

Speed.#1.........: 69562.9 kH/s (56.74ms) @ Accel:32 Loops:128 Thr:1024 Vec:1

Hashmode: 1700 - SHA2-512

Speed.#1.........: 24661.3 kH/s (81.80ms) @ Accel:32 Loops:64 Thr:1024 Vec:1

Hashmode: 2500 - WPA-EAPOL-PBKDF2 (Iterations: 4095)

Speed.#1.........:     9788 H/s (50.62ms) @ Accel:8 Loops:256 Thr:1024 Vec:1

Hashmode: 1000 - NTLM

Speed.#1.........:  1006.9 MH/s (62.83ms) @ Accel:64 Loops:1024 Thr:1024 Vec:8

Hashmode: 3000 - LM

Speed.#1.........:   482.3 MH/s (63.67ms) @ Accel:512 Loops:1024 Thr:64 Vec:1

Hashmode: 5500 - NetNTLMv1 / NetNTLMv1+ESS

Speed.#1.........:   500.8 MH/s (63.23ms) @ Accel:256 Loops:128 Thr:1024 Vec:2

Hashmode: 5600 - NetNTLMv2

Speed.#1.........: 38192.0 kH/s (51.40ms) @ Accel:64 Loops:32 Thr:1024 Vec:1

Hashmode: 1500 - descrypt, DES (Unix), Traditional DES

Speed.#1.........: 22786.0 kH/s (86.45ms) @ Accel:2 Loops:1024 Thr:1024 Vec:1

Hashmode: 500 - md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5) (Iterations: 1000)

Speed.#1.........:   245.6 kH/s (60.28ms) @ Accel:256 Loops:62 Thr:1024 Vec:1

Hashmode: 3200 - bcrypt $2*$, Blowfish (Unix) (Iterations: 32)

Speed.#1.........:      263 H/s (40.72ms) @ Accel:1 Loops:32 Thr:12 Vec:1

Hashmode: 1800 - sha512crypt $6$, SHA512 (Unix) (Iterations: 5000)

Speed.#1.........:     3896 H/s (51.93ms) @ Accel:16 Loops:64 Thr:1024 Vec:1

Hashmode: 7500 - Kerberos 5, etype 23, AS-REQ Pre-Auth

Speed.#1.........:  4620.4 kH/s (53.18ms) @ Accel:128 Loops:32 Thr:64 Vec:1

Hashmode: 13100 - Kerberos 5, etype 23, TGS-REP

Speed.#1.........:  4221.2 kH/s (58.42ms) @ Accel:8 Loops:512 Thr:64 Vec:1

 Hashmode: 15300 - DPAPI masterkey file v1 (Iterations: 23999)

Speed.#1.........:     1680 H/s (50.51ms) @ Accel:8 Loops:256 Thr:1024 Vec:1

Hashmode: 15900 - DPAPI masterkey file v2 (Iterations: 12899)

* Device #1: ATTENTION! CUDA kernel self-test failed.

Your device driver installation is probably broken.
See also: https://hashcat.net/faq/wrongdriver

Speed.#1.........:      846 H/s (94.03ms) @ Accel:16 Loops:64 Thr:1024 Vec:1

Hashmode: 7100 - macOS v10.8+ (PBKDF2-SHA512) (Iterations: 1023)

Speed.#1.........:    10329 H/s (90.79ms) @ Accel:64 Loops:15 Thr:1024 Vec:1

Hashmode: 11600 - 7-Zip (Iterations: 16384)

Speed.#1.........:     7842 H/s (63.63ms) @ Accel:32 Loops:256 Thr:1024 Vec:1

Hashmode: 12500 - RAR3-hp (Iterations: 262144)

Speed.#1.........:     1450 H/s (42.15ms) @ Accel:1 Loops:16384 Thr:1024 Vec:1

Hashmode: 13000 - RAR5 (Iterations: 32799)

Speed.#1.........:      848 H/s (73.81ms) @ Accel:16 Loops:128 Thr:1024 Vec:1

Hashmode: 6211 - TrueCrypt RIPEMD160 + XTS 512 bit (Iterations: 1999)

Speed.#1.........:     6831 H/s (70.22ms) @ Accel:8 Loops:128 Thr:1024 Vec:1

Hashmode: 13400 - KeePass 1 (AES/Twofish) and KeePass 2 (AES) (Iterations: 24569)

Speed.#1.........:      837 H/s (202.43ms) @ Accel:8 Loops:512 Thr:1024 Vec:1

Hashmode: 6800 - LastPass + LastPass sniffed (Iterations: 499)

Speed.#1.........:    54104 H/s (64.21ms) @ Accel:32 Loops:62 Thr:1024 Vec:1

Hashmode: 11300 - Bitcoin/Litecoin wallet.dat (Iterations: 200459)

Speed.#1.........:      104 H/s (48.72ms) @ Accel:4 Loops:256 Thr:1024 Vec:1
   
```
