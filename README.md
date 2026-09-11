# Siemens MS42

TunerPro RT definition files (XDF) for the **Siemens MS42** engine control unit, software **0110C6**.

📖 Documentation: **[Siemens MS42](https://www.ms4x.net/index.php?title=Siemens_MS42)** · [Pinout](https://www.ms4x.net/index.php?title=Siemens_MS42_Pinout) · [CAN Bus](https://www.ms4x.net/index.php?title=Siemens_MS42_CAN_Bus) · [PCB Components](https://www.ms4x.net/index.php?title=Siemens_MS42_PCB_Components) · [Community Patchlist](https://www.ms4x.net/index.php?title=TunerPro_MS42_Community_Patchlist)

## Definition files

| File | Binary | Base offset |
|---|---|---|
| [`Siemens_MS42_0110C6_ENG_512K_v1.3.xdf`](definitions/Siemens_MS42_0110C6_ENG_512K_v1.3.xdf) | 512 KB full read | 0x48000 |
| [`Siemens_MS42_0110C6_ENG_32K_v1.3.xdf`](definitions/Siemens_MS42_0110C6_ENG_32K_v1.3.xdf) | 32 KB calibration | 0x0 |

> [!IMPORTANT]
> Only for software **0110C6**. Update older software (e.g. 0110AB/0110AD) first – see the wiki.

### What's new in v1.3

- all axes are separate, linked tables (404 axis tables, `ldp_`/`ldpm_`) – edit an axis once, every map using it follows
- data types and conversions verified against the Siemens A2L description:
  - 117 map axes displayed wrong values in v1.2 (wrong element size, 16-bit scaling on 8-bit axes, missing offsets, 10 axes shifted by one point)
  - 115 value conversions corrected (rounding errors and wrong factors, e.g. end-of-injection angle, camshaft offsets)
- axis tables on top, category **Axis**

## Usage

1. Read the DME with a [flashing tool](https://www.ms4x.net/index.php?title=Flashing_Tools) and make sure it runs 0110C6.
2. Open the binary in [TunerPro RT](https://www.tunerpro.net) and load the XDF matching the **binary size**.
3. Optional: load the [Community Patchlist](https://www.ms4x.net/index.php?title=TunerPro_MS42_Community_Patchlist) for extra features.
4. Keep an untouched backup of the original read.

## Changelog

| Version | Date | Changes |
|---|---|---|
| v1.3 | 2026-09-11 | Linked axis tables, A2L-verified axes and conversions, 32K variant rebuilt from 512K |
| v1.2 | 2026-07-06 | Manual adjustments of axis and air mass values |
| v1.1 | 2023 | Initial release directly converted from A2L |

## Contributing

Wrong value, unit or translation? Please [open an issue](https://github.com/ms4x-net/ms42/issues) with table name and what you expected.

## License & disclaimer

Definition files are released under [GPL-3.0](LICENSE).

> [!WARNING]
> For off-road / closed-course use only. No warranty – you modify your ECU at your own risk.
