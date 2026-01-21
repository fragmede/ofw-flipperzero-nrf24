# ofw-flipperzero-nrf24

An [NRF24](https://www.sparkfun.com/datasheets/Components/SMD/nRF24L01Pluss_Preliminary_Product_Specification_v1_0.pdf) driver for the [Flipper Zero](https://flipperzero.one/) device running the unmodified original firmware.
The NRF24 is a popular line of 2.4GHz radio transceivers from Nordic Semiconductors. This library is not currently complete, but functional.

## Building
Navigate to the specifi apps subdirectories and run `ufbt`. For instance:

```shell
cd nrfsniff
ufbt launch
```

Last built with the OFW version `1.4.3` (January 2026).

## Fork Notes
This fork updates the code to compile with the latest official firmware (1.4.3). Changes include:
- Updated `FuriHalSpiBusHandle*` to `const FuriHalSpiBusHandle*` in the NRF24 library to match the new SDK API
- Fixed `input_callback` signature to use `void* context` parameter

## Warning
This repo contains three Flipper Zero apps that utilize the NRF24 driver to sniff for NRF24 addresses and perform mousejack attacks. These apps are for **educational purposes** only. Please use this code responsibly and only use these apps on your own equipment.

## Acknowledgments
The NRF24 sniffing technique was discovered and shared by Travis Goodspeed in [his blog](http://travisgoodspeed.blogspot.com/2011/02/promiscuity-is-nrf24l01s-duty.html).

The mousejack vulnerabilities were discovered and reported by Marc Newlin, see [the blog](https://www.bastille.net/research/vulnerabilities/mousejack/technical-details) for technical details.

Much of the driver code was inspired by [RadioHead's Arduino library](https://www.airspayce.com/mikem/arduino/RadioHead/classRH__NRF24.html).
Much of the mousejack code was inspired by the [Jackit project](https://github.com/insecurityofthings/jackit).

The up-to-date code has been synced from [RogueMaster repo](https://github.com/RogueMaster/flipperzero-firmware-wPlugins).

NRF24 scan app has been ported from [vad7](https://github.com/vad7/nrf24scan). It is licensed under the GPLv3.
