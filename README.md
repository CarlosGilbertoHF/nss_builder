# Qualcommax_NSS_Builder

This project automates OpenWRT builds for the Xiaomi AX3600, focusing on comprehensive NSS support with a minimalistic approach to additional packages. It is based on the `qualcommax-6.1-nss-wifi` branch from [qosmio/openwrt-ipq](https://github.com/qosmio/openwrt-ipq/tree/qualcommax-6.1-nss-wifi) and draws inspiration from [rodriguezst/ipq807x-openwrt-builder](https://github.com/rodriguezst/ipq807x-openwrt-builder).

## Features

The build features:
- **Full NSS (Network Subsystem) support** for enhanced networking performance.
- **NSS info patch** for the Luci status page by @qosmio
- **Security and Network Management Tools**:
  - `luci-app-banip` for IP-based banning.
  - `luci-ssl` to secure the LuCI web interface with SSL/TLS.
- **Hardened OpenSSH configuration** using recommendations from [ssh-audit](https://github.com/jtesta/ssh-audit)
- **Comprehensive Wireless Protocol Support** with `wpad-mbedtls` (Full).
- **Build with** `CONFIG_TARGET_OPTIMIZATION="-O3 -pipe -mcpu=cortex-a53+crc+crypto"; CONFIG_USE_LTO=y; CONFIG_USE_MOLD=y; CONFIG_ZLIB_OPTIMIZE_SPEED=y` for higher Performance.

## Recommended Configuration
- Packet Steering: Disabled.
- Software / Hardware flow offloading: Disabled.
- Set your specific country code for WIFI.
- Set `pbuf.opt.memory_profile=off` unless you have more than 65 clients connecting over wifi or are experiencing hangups while torrenting.

## Contributing

Contributions are highly appreciated! If you have suggestions for additional packages, essential features that are missing, or improvements to the existing setup, please feel free to submit a pull request or open an issue. Your input helps make Qualcommax_NSS_Builder even better for everyone.
