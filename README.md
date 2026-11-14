# usb-headphone-amp

Three revisions of a USB headphone amp / soundcard that I made in KiCad.

Each folder has the KiCad files (schematic + PCB). V3 also has the STM32 firmware.

## The versions

**V1** (`v1/NE5532_Headphoneamp`)
- USB to I2S bridge: TI PCM2706
- I2S DAC: TI PCM5102
- Amp stages: TI NE5532
  
**V1** (`v1/Headphoneamp_psu`)
- Separate power board project for V1 amplifier: TI TPS65131 makes +-15V, then linear regulators bring it down to +-12V

**V2** (`v2/`)
- Same digital stage as V1 (PCM2706 + PCM5102)
- New analog stage: TI OPA1656 for gain, TI BUF634 as the output buffer
- Power supply is now TI LM27762, on the same board.
- Much smaller footprint

**V3 (Work in progress)** (`v3/`)
- Same as V2, but some small PCB layout changes and the PCM2706 is gone
- To get higher sample rates / bit depth, an STM32F411 does the USB audio instead (TinyUSB, UAC1.0 device)
- `v3/hardware/` = KiCad, `v3/firmware/` = STM32CubeIDE project
