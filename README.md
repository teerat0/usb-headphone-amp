# usb-headphone-amp

Three revisions of a USB headphone amp / soundcard that I made in KiCad. Each one is basically an upgrade of the last.

Each folder has the KiCad files (schematic + PCB). V3 also has the STM32 firmware.

## The versions

**V1** (`v1/`)
- USB to I2S: PCM2706
- DAC: PCM5102
- Amp: NE5532
- Separate power board: TPS65131 makes +-15V, then linear regulators bring it down to +-12V

**V2** (`v2/`)
- Same digital stage as V1 (PCM2706 + PCM5102)
- New analog stage: OPA1656 for gain, BUF634 as the output buffer
- Power supply is now LM27762, on the same board.

**V3** (`v3/`)
- Same as V2, but the PCM2706 is gone
- An STM32F411 does the USB audio instead (TinyUSB, acts as a USB to I2S device)
- `v3/hardware/` = KiCad, `v3/firmware/` = STM32CubeIDE project

## Quick comparison

| | USB to I2S | DAC | Analog stage | Status |
|---|---|---|---|---|
| V1 | PCM2706 | PCM5102 | NE5532 | TODO |
| V2 | PCM2706 | PCM5102 | OPA1656 + BUF634 | TODO |
| V3 | STM32F411 | PCM5102 | OPA1656 + BUF634 | WIP |

## Notes

- This is a hobby project, nothing here is guaranteed to work. Check the schematics before you order boards.
- No gerbers in the repo, just the KiCad source files.