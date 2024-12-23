All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!--
## [Unreleased]
-->

## Upgrading to this release

You can upgrade the GreatFET host tools to the latest release with:

    pip install --upgrade greatfet

After upgrading the host tools, update your GreatFET firmware to the latest release with:

    greatfet_firmware --autoflash

Happy hacking!


## [v2024.0.4] - 2024-12-18
### Fixed
* Serial packets were framed incorrectly when using the GreatFET UART interface with parity set to one of: ODD, EVEN or PARITY_STUCK_AT_ONE
### Changed
* Updated libgreat to [`v2024.0.3`](https://github.com/greatscottgadgets/libgreat/compare/v2024.0.2...v2024.0.3)


## [v2024.0.3] - 2024-10-10
### Fixed
* Permission denied error when using logic analyzer on Windows.


## [v2024.0.2] - 2024-09-19
### Fixed
* The GreatFET shell was unable to access globals inside user defined functions.
* Import errors on some Python distributions.
### Changed
* Updated pyfwup dependency to `0.5.2`
* Updated libgreat to [`v2024.0.2`](https://github.com/greatscottgadgets/libgreat/compare/v2024.0.1...v2024.0.2)
### Added
* Windows support for Cynthion.


## [v2024.0.1] - 2024-06-04
### Added
* Add IPython to the GreatFET installation by default.
### Changed
* Updated udev rules to use uaccess tag rather than the plugdev group.
* Updated the rad1o board file (tx @dos1!)


## [v2024.0.0] - 2024-05-22
### GreatFET
* [gpio: add support for configuring all gpio pin modes](https://github.com/greatscottgadgets/greatfet/pull/418)
* [uart: fix python KeyError when parity argument not specified](https://github.com/greatscottgadgets/greatfet/pull/375)
* [shell: support versions of IPython >= 3.11](https://github.com/greatscottgadgets/greatfet/pull/414)
* [facedancer: fix usb mass storage example](https://github.com/greatscottgadgets/greatfet/pull/425)
* [shell: fix runtime errors when using uart functionality](https://github.com/greatscottgadgets/greatfet/pull/426)
### libgreat
* [Added TX & RX pin definitions for UART1, USART2&3](https://github.com/greatscottgadgets/libgreat/pull/25)
* [Implement NXP's recommended PLL setup sequence](https://github.com/greatscottgadgets/libgreat/pull/30)
* [Add support for configuring all gpio pin modes](https://github.com/greatscottgadgets/libgreat/pull/35)
* [Don't try to claim USB interface on Windows](https://github.com/greatscottgadgets/libgreat/pull/38)
* [Add initial implementation of usb1 bulk transfer backend](https://github.com/greatscottgadgets/libgreat/pull/33)
* [Do not set USB device address to zero](https://github.com/greatscottgadgets/libgreat/pull/26)



## [v2021.2.1] - 2021-02-23

NOTE: We no longer support Python 2. This release targets Python 3.6+.

### Highlights for this release:

* This release adds a new chipcon programmer for Texas Instruments CCxxxx ("SWRA124") devices.
    - In Python: `chipcon = gf.create_programmer('chipcon')`
        - From there you can perform manual operations like `chipcon.run_instruction()` and `read_xdata_memory()`,
        - Or use higher-level interface methods like `program_flash()` and `read_flash()`.
    - Flash operations can also be done from the command line with `greatfet chipcon`.
* This release adds a new programmer for Microchip I2C EEPROM devices: `eeprom = gf.create_programmer('microchipEEPROM', device='24LC128')`.
    - This mainly provides two higher-level methods: `read_bytes(start, end)`, and `write_bytes(start, data)`.

### Major bugfixes:

 - #344: Facedancer with bMaxPacketSize0 < 32 does not work.


[Unreleased]: https://github.com/greatscottgadgets/greatfet/compare/v2024.0.4...HEAD
[v2024.0.4]: https://github.com/greatscottgadgets/greatfet/compare/v2024.0.3...v2024.0.4
[v2024.0.3]: https://github.com/greatscottgadgets/greatfet/compare/v2024.0.2...v2024.0.3
[v2024.0.2]: https://github.com/greatscottgadgets/greatfet/compare/v2024.0.1...v2024.0.2
[v2024.0.1]: https://github.com/greatscottgadgets/greatfet/compare/v2024.0.0...v2024.0.1
[v2024.0.0]: https://github.com/greatscottgadgets/greatfet/compare/v2021.2.1...v2024.0.0
[v2021.2.1]: https://github.com/greatscottgadgets/greatfet/releases/tag/v2021.2.1
