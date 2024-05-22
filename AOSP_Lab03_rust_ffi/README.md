# AOSP rust_ffi 

This repository contains a simple Rust library and binary example for use in Android Open Source Project (AOSP) environments.

## Overview

This project demonstrates the use of `rust_ffi` for Android. 
`rust_ffi` produces all FFI variants ( `rust_ffi_shared`and `rust_ffi_static`).
It consists of a Rust library `libffi_by_ines` that exposes a function and a Rust binary `my_binary_call_ffi` that calls this function. 
The project is structured using `Android.bp` build system.

## Building and Usage

To build the project, ensure you have Rust installed on your system. Then, follow these steps:

1. Clone the repository:
```bash
   git clone https://github.com/Inesbaklouti1/AOSP_trainings_Rust.git
```
2. Navigate to the project directory:
```bash
   cd AOSP_trainings_Rust/AOSP_Lab03_rust_ffi
```
3. Copy the directory in `~/aosp14_gsi/external/`

```bash
   cp AOSP_trainings_Rust/AOSP_Lab03_rust_ffi ~/aosp14_gsi/external/
```
4. Add the following line to `aosp14_gsi/device/google/cuttlefish/vsoc_x86_64/phone/aosp_cf.mk`:

```bash
PRODUCT_PACKAGES += \
    my_binary_call_ffi \
    libffi_by_ines 
    
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
or 
```bash
launch cvd 
```

7. Open adb shell then run the binary
```bash

adb shell
```
```bash
vsoc_x86_64:/ $ my_binary_call_ffi

```
the result : hello from ffi library
