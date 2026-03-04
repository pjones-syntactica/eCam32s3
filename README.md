# eCam32s3 Arduino Support Package

This repository contains **Arduino variant definitions** and **Arduino libraries** for the **eCam32s3** ESP32-S3 development board.

It is intended to be used **alongside** the official ESP32 Arduino core (Espressif) — this repo does *not* include the ESP32 core itself.

---

## Contents

* `variants/eCam32s3/`
  Board variant files (pin mapping, default buses, LED pin, etc.)

* `libraries/`
  Board-specific libraries to simplify use of onboard peripherals (SPI devices, camera helpers, power/control pins, etc.)

---

## Requirements

* Arduino IDE 2.x (or Arduino CLI)
* **ESP32 by Espressif Systems** installed via Boards Manager

---

## Installation

### Option A — Arduino IDE (recommended)

1. Install the ESP32 core:

   * Open **File → Preferences**
   * In **Additional Boards Manager URLs**, add Espressif’s URL (if not already present)
   * Open **Tools → Board → Boards Manager**
   * Install **ESP32 by Espressif Systems**

2. Install this repo as a “hardware override” (variant + libraries):

   * Locate your Arduino sketchbook folder:

     * Arduino IDE: **File → Preferences → Sketchbook location**
   * Create this folder if it does not exist:

     * `<Sketchbook>\hardware\ecam\esp32\`
   * Copy the following into `<Sketchbook>\hardware\ecam\esp32\`:

     * `variants\`
     * `libraries\`
     * `boards.txt` *(if you provide one in this repo)*

3. Restart Arduino IDE.

4. Select the board:

   * **Tools → Board** → look for **eCam32s3**

> Notes:
>
> * Arduino will search the sketchbook `hardware/` folder for additional platforms/boards.
> * If you are not shipping a `boards.txt` in this repo, you must add your board to the ESP32 core you are using (or upstream it to Espressif).

---

### Option B — Git checkout into the sketchbook (developer workflow)

```bash
cd "<Sketchbook>\hardware"
mkdir -p ecam\esp32
cd ecam\esp32
git clone https://github.com/<you>/<repo>.git .
```

Restart Arduino IDE after updates.

---

## Using the libraries

Each library under `libraries/` contains examples. In Arduino IDE:

* **File → Examples → (your library name)**

If you provide a “board helper” library, it’s usually the fastest way to validate your wiring and defaults.

---

## Development

### Layout expectations (Arduino)

* Variant files belong in `variants/<variant_name>/`
* Arduino libraries belong in `libraries/<LibraryName>/` with a `library.properties`

Arduino library format reference:

* https://docs.arduino.cc/arduino-cli/library-specification/

---

## Licensing

This repository contains only original work (variants + libraries).
See `LICENSE.md` for the license terms.

---

## Support / Issues

* Bug reports and feature requests: https://github.com/<you>/<repo>/issues

When filing a bug, include:

* ESP32 core version (Boards Manager)
* Arduino IDE version
* Board revision (if applicable)
* Steps to reproduce
* Serial log output (if relevant)

