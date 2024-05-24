# M720q_Hackintosh_oc0.99

All the software used are up-to-date until 2024/5/1

**TO DO**

- Use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate your own SMBIOS
  - Choose type: `Macmini8,1`
  - Get `Serial`, `Board Serial`, `SmUUID`, `ROM` and copy to `config.plist/Generic`
  - More Info see [Desktop Coffee Lake | OpenCore Install Guide (dortania.github.io)](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#platforminfo)

**BIOS Setting**

- **!!!Highly-risk operation!!!** Ensure unlock `CFG Lock` through modifying BIOS
  - If skip, set `AppleCpuPmCfgLock` and `AppleXcpmCfgLock` to **`True`**
- Choose **`Auto`** in `BIOS/Video Setup/Select Active Video` to use `dGPU`

**Software**

| Core Components | Version                   |
| --------------- | ------------------------- |
| Opencore        | 0.99                      |
| MacOS           | Big Sur 11.7.10 (20G1427) |

**Hardware**

| Components     | Used                                                |
| -------------- | --------------------------------------------------- |
| Model          | NEC8(ThinkCentre M720 Tiny)                         |
| CPU            | i7-8700(coffee lake, 65w)                           |
| Graphics Card  | Quadro K420(Kepler, GK107) / Intel UHD Graphics 630 |
| RAM            | 8Gx1 Hynix DDR4 2400 (later update to 8Gx2)         |
| ROM            | KIOXIA RC10 512G                                    |
| WIFI/Bluetooth | Dell DW1707                                         |
| Audio          | Realtek ALC235                                      |
| Ethernet       | Intel I219-V                                        |

**Opencore Kexts**

| Name             | Version |
| ---------------- | ------- |
| WhateverGreen    | 1.6.7   |
| Lilu             | 1.6.8   |
| USBToolBox       | 1.1.1   |
| IntelMausi       | 1.0.8   |
| AppleALC         | 1.9.0   |
| VirtualSMC       | 1.3.2   |
| BrcmPatchRAM     | 2.6.8   |
| NVMeFix          | 1.1.1   |
| AirportBrcmFixup | 2.1.8   |

**Implement Functions**

- Create SSDTs for M720q
- USB mapping
- Fixing Audio
- Fixing DRM
- Fixing iServices
- Fixing power management

**Known Issues**

- Type C not work (maybe just a problem of my M720q)
- HDMI of `iGPU` not fixed (coming soon)
- Sleeping problem (difficult to solve now)

**Notes**

- `AppleCpuPmCfgLock` and `AppleXcpmCfgLock` are **`False`**
- Quadro K420 is natively supported in Big Sur 11.7.x
- DW1707 only supports 2.4G WIFI and Bluetooth 4.0 but it is cheap
- Choose **`Macmini8,1`** as `PlatformInform` for lower power usage
- Use **`alcid=17`** to drive the Realtek ALC235
- Use **`07009B3E`** for `AAPL,ig-platform-id` and **`Shiki=40`** to fix the DRM

**Screenshots**

![1](pic/1.png)

![2](pic/2.png)

![3](pic/3.png)

![4](pic/4.png)

![5](pic/5.png)
