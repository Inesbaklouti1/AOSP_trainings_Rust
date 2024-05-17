# AOSP Rust Library 

This repository contains a simple Rust library and binary example for use in Android Open Source Project (AOSP) environments.

## Overview

The project consists of two main files:

1. `lib.rs`: This file defines a simple function called `my_function` which prints "hello from ines lib" when called.

2. `librustines.rs`: This file includes a main function that calls `my_function` from the `lib` module.

## Building and Usage

To build the project, ensure you have Rust installed on your system. Then, follow these steps:

1. Clone the repository:
```bash
   git clone https://github.com/Inesbaklouti1/AOSP_trainings_Rust.git
```
2. Navigate to the project directory:
```bash
   cd AOSP_trainings_Rust/AOSP_Lab02_rust_library
```
3. Copy the directory in `~/aosp14_gsi/external/`

```bash
   cp AOSP_trainings_Rust/AOSP_Lab02_rust_library ~/aosp14_gsi/external/
```
4. Add the following line to `aosp14_gsi/device/google/cuttlefish/vsoc_x86_64/phone/aosp_cf.mk`:

```bash
PRODUCT_PACKAGES += \
    librustines \
    binrustines 
```
5. Build 
```bash
m 
```
or 
```bash
m -j(n.cores) 
```
example : m -j12

6. Launch the cuttlefish virtual device
```bash
adb connect 0.0.0.0:6520 --if it is the first instance
cvd start 
```
7. Open adb shell then run the binary
```bash

adb shell
```
```bash
vsoc_x86_64:/ $ binrustines

```
the result : hello from ines lib

