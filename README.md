# x570sAeroG
# Gigabyte X570S Aero G Hackintosh

This repository contains OpenCore configuration files and documentation for running macOS on the Gigabyte X570S Aero G motherboard. This build has been tested with macOS Sonoma 14.7 and Windows 10 in a dual-boot configuration.

## Hardware Specifications

| Component | Model |
|-----------|-------|
| Motherboard | Gigabyte X570S Aero G |
| CPU | AMD Ryzen 7 5700X3D |
| RAM | Corsair DOMINATOR PLATINUM RGB 16GB (2 x 8GB) DDR4-3600MHz |
| Storage | Crucial MX500 250GB SSD |
| Graphics | Radeon RX 6800 GAMING OC 16G |
| Ethernet | Intel i225-V 2.5GbE |
| Wi-Fi | Intel® Wi-Fi 6 AX200 |

### Additional Storage Note
- SK Hynix PC711 NVMe drive is present but disabled in OpenCore config to avoid conflicts

## Software Specifications

- OpenCore Version: 1.0.2
- macOS Version: Sonoma 14.7
- Windows Version: Windows 10

## Current Status

### Working
- ✅ Ethernet (Intel i225-V)
- ✅ Sleep/Wake functionality (under testing)
- ✅ GPU Acceleration
- ✅ AMD CPU Patches

### Not Working
- ❌ Wi-Fi functionality
- ❌ SK Hynix NVMe (intentionally disabled)

## Installation Notes

### AMD CPU Patches
- Implemented using patches from [AMD-OSX/AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- Patches have been adjusted according to CPU core count

### Ethernet (Intel i225-V) Configuration
Two approaches were tested:

1. **Initial Approach (Unstable)**
   - Used AppleIGC.kext
   - Successfully detected in IORegistryExplorer
   - Experienced stability issues with random connection drops
   - Required manual service deletion and re-addition to restore connectivity

2. **Current Solution (Stable)**
   - Implemented using [Option 2 from the Gigabyte Z490 Vision G guide](https://github.com/5T33Z0/Gigabyte-Z490-Vision-G-Hackintosh-OpenCore/blob/main/I225-V_FIX.md#option-1-using-a-ssdt-with-corrected-header-description)
   - Provides better stability and reliability

## Known Issues

### Previous macOS Installation
- Initial installation on macOS Sequoia experienced ethernet stability issues when using AppleIGC.kext
- Issue manifested as random internet disconnections
- Temporary fix required removing and re-adding network service in System Settings

## Contributing

Feel free to open issues or submit pull requests if you have improvements or fixes to suggest.

## Credits

- [AMD-OSX/AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla) for AMD CPU patches
- [5T33Z0's Gigabyte Z490 Vision G Guide](https://github.com/5T33Z0/Gigabyte-Z490-Vision-G-Hackintosh-OpenCore/) for I225-V ethernet fixes

## Disclaimer

This configuration is provided as-is. Use at your own risk. Success in running macOS on your hardware may vary.
