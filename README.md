<a name="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

<br />
<div align="center">

  <h3 align="center">apex_dma_kvm_pub</h3>

  <p align="center">
    Apex Legends QEMU/KVM hack
    <br />
    <br />
    <br />
    <a href="https://www.unknowncheats.me/forum/apex-legends/406426-kvm-vmread-apex-esp-aimbot.html">UnknownCheats thread</a>
    ·
    <a href="https://github.com/chettoy/apex_dma_kvm_pub/issues">Report Bug</a>
    ·
    <a href="https://github.com/chettoy/apex_dma_kvm_pub/issues">Request Feature</a>
  </p>
</div>

<br />

<img src="Pictures/MainGameView.jpg" alt="Main View" width="960" height="540">

<br />



## About The Project
Apex Legends QEMU/KVM hack

UnknownCheats thread: https://www.unknowncheats.me/forum/apex-legends/406426-kvm-vmread-apex-esp-aimbot.html

Bone IDs reference: https://www.unknowncheats.me/wiki/Apex_Legends_Bones_and_Hitboxes

Game version (Steam Only right now): v3.0.51.45




 **Features**

1. KrackerCo Fork's no-overlay features.

    > This is the No Client(Windows) Branch, nothing is needed on the windows side.
    >
    > ESP Glow color picker for knocked and alive, visable or not visable.
    >
    > Item Glow with item filter.
    >
    > Weapon Glow with Weapon filter.
    >
    > Firing Range dummp targeting debug testing.
    >
    > TDM Aimbot/Glow so you only target the other team.
    >
    > Left/Right or both mouse buttons to aim.

2. KrackerCo Fork's Client features.

    > ESP Glow color picker for knocked and alive, visable or not visable.
    >
    > Item Glow with item filter.
    >
    > Weapon Glow with Weapon filter.
    >
    > Mini-Map radar*1.
    >
    > Full map radar*2.
    >
    > Firing Range dummp targeting debug testing.
    >
    > TDM Aimbot/Glow so you only target the other team.
    >
    > Custom aiming distance.
    >
    > Left/Right or both mouse buttons to aim.
    >
    > Custom Predition speed and Gravity to use with Headshot Mode*3.
    >
    > Save and Load config buttons and at s

3. chettoy Fork's features

    * KrackerCo Fork's no-overlay features.
    * KrackerCo Fork's Client features.
    * Optional glow box to replace the player glow (If you want to prevent screenshot detection or want to broadcast live)
    * Show player nickname next to health shield bars
    * Sky Grenade
    * Improved target locking
    * Automatic target bone selection



Please star if you like it.
Look forward to your testing and feedback.



## Getting Started

Click on *Actions* to download the auto-built artifacts.



```shell
sudo ./apex_dma
```

1. Please put the overlay window on the top of the VM screen after start. For example, on top of the looking-glass window.
2. The window can't get the focus at the same time with the VM screen,  please passthrough some keyboard, mouse or joystick into the VM,  otherwise you can't operate the game.



## Build from source

**Requirements:**

* C++ toolchain
* Rust toolchain
* CMake
* Git

**Dependencies:**

For Ubuntu

```bash
sudo apt install libglfw3-dev libfreetype6-dev libvulkan-dev libxrandr-dev libxinerama-dev libxcursor-dev libxi-dev libxext-dev wayland-protocols libwayland-dev libxkbcommon-dev
```

**Build:**

```shell
git clone --recurse https://github.com/chettoy/apex_dma_kvm_pub -b external-overlay
cd apex_dma_kvm_pub/apex_dma
./build.sh
```



## FAQ

1. Many people are using a single GPU

    > If there is only one GPU and the linux host can't be displayed after  starting the VM, you can still use features other than the overlay in  such a case.
    > You can even turn off the overlay and use it as a no-overlay version.
    > In this case you will not be able to use only the overlay-dependent  features such as the mini-map radar, health shield bars, GUI menus,  spectator display, etc. But all the original features of the no-overlay  branch such as the player glow, text menu in terminal, and the new sky  grenade will still work.

2. It seems that the client is still reading the values required for the esp stuff. If AC is looking for access on those specific memory locations, then IDK if just removing the implementation of the overlay will work in  terms of preventing detection. Or is AC simply detecting the presence of the overlay/client itself, and banning due to that?

    > First of all, everything related to game state is realized by *access on those specific memory locations*. So we need to use DMA or VM techniques to access memory covertly.
    > AC detects the overlay client, so we re-implement the overlay outside the VM and remove the client.



## Acknowledgments


* [MisterY52/apex_dma_kvm_pub](https://github.com/MisterY52/apex_dma_kvm_pub)
* [KrackerCo/apex_dma_kvm_pub](https://github.com/KrackerCo/apex_dma_kvm_pub)
* [CasualX/apexdream](https://github.com/CasualX/apexdream)
* [Nexilist/xap-client](https://github.com/Nexilist/xap-client)


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/chettoy/apex_dma_kvm_pub.svg?style=for-the-badge
[contributors-url]: https://github.com/chettoy/apex_dma_kvm_pub/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/chettoy/apex_dma_kvm_pub.svg?style=for-the-badge
[forks-url]: https://github.com/chettoy/apex_dma_kvm_pub/network/members
[stars-shield]: https://img.shields.io/github/starschettoy/apex_dma_kvm_pub.svg?style=for-the-badge
[stars-url]: https://github.com/chettoy/apex_dma_kvm_pub/stargazers
[issues-shield]: https://img.shields.io/github/issues/chettoy/apex_dma_kvm_pub.svg?style=for-the-badge
[issues-url]: https://github.com/chettoy/apex_dma_kvm_pub/issues
[license-shield]: https://img.shields.io/github/license/chettoy/apex_dma_kvm_pub.svg?style=for-the-badge
[license-url]: https://github.com/chettoy/apex_dma_kvm_pub/blob/main/LICENSE.txt
