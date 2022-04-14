## Trinity: Desirable Mobile Emulation through Graphics Projection

![version](https://img.shields.io/badge/Version-Beta-yellow "Beta")
![license](https://img.shields.io/badge/GuestOS-Androidx86-green "Android")
![license](https://img.shields.io/badge/Licence-GPLv2-blue.svg "Apache")
![status](https://github.com/TrinityEmulator/TrinityEmulator/actions/workflows/main.yml/badge.svg)

### Table of Content

* [Introduction](#introduction)
* [Codebase](#codebase--build)
* [Install and Run](#install-and-run)
  * [Prerequisites](#prerequisites)
  * [Running](#running)
* [Measurement Data](#measurement-data)

### Introduction

Trinity is the first mobile emulator that simultaneously achieves excellent compatibility, efficiency and security. 

Trinity is built on our novel concept of a *graphics projection space* that resides in the guest memory, where we selectively maintain a “projected” subset of control contexts and resource handlers that are actually required by the host GPU during its rendering, so as to minimize
the coupling between the guest-side and host-side graphics processing and thus keep the guest-host control/data flows *concise, smooth, and straight*.

This repository contains code and binary of Trinity, as well as measurement data involved in our study.

### Codebase & Build

Currently we have released all the emulator's source [here](https://github.com/TrinityEmulator/TrinityEmulator) and provide detailed guides on building Trinity. Our guest-side implementation is proprietary for now but the OS images can be found [here](https://github.com/TrinityEmulator/TrinityEmulator/releases/tag/Trinity-Release). 

### Install and Run

We have released Trinity's binary for you to check out on your own PC [here](https://github.com/TrinityEmulator/TrinityEmulator/releases/tag/Trinity-Release) (Window+Intel version, other versions such as Mac and AMD are coming soon as we are doing minor bug fixes). Some prerequisites and instructions are listed below.

#### Prerequisites

1. Ensure that you have turned on Intel VT in the BIOS settings.
2. Install Intel HAXM (recommended version is v7.6.5, instructions [here](https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows)).

And then you are good to go!

#### Running

We provide an executable for running Trinity. Therefore, all you need to do is download the ZIP file above, extract the files, and double-click on the executable `Trinity.exe` to execute Trinity.

During booting, you may see an option to run without installation or to install provided by the Android-x86 system we host. The former allows you to quickly enjoy the journey but makes the virtual storage volatile (i.e., the next boot will erase all data), while the latter may involve more complex configurations (you can find them [here](https://github.com/TrinityEmulator/TrinityEmulator/wiki/Guest-OS-Installation-Guide)).

### Measurement Data

The measurement data involved in our evaluation are hosted [here](https://github.com/TrinityEmulator/EvaluationScript).
