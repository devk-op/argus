<div align="center">

# Argus

**An openpilot fork with multi-sensor fusion, audio-based driver monitoring, and GM Bolt EV LT support.**

*Named after Argus Panoptes — the all-seeing giant of Greek mythology.*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Based on openpilot](https://img.shields.io/badge/based%20on-openpilot-blue)](https://github.com/commaai/openpilot)

</div>

---

## What is Argus?

Argus is a fork of [comma.ai's openpilot](https://github.com/commaai/openpilot) that extends the base platform with additional sensor inputs, audio-based driver monitoring, and support for the Bolt EV LT (2017–2023) without factory ACC using a pedal interceptor.

openpilot already handles camera-based perception and vehicle control well. Argus adds what it leaves out: blind spot awareness from CAN signals already present in the car, microphone-based driver alertness detection using DSP, and longitudinal control for non-ACC GM vehicles.

---

## Key Differences from openpilot

| Feature | openpilot | Argus |
|---|---|---|
| Bolt EV LT (no ACC) | Not supported | Supported via pedal interceptor |
| Blind spot monitoring | Not used | Reads existing vehicle CAN signals |
| Driver monitoring | Camera-only (DMS) | Camera + audio (DSP-based) |
| Sensor fusion | Front cameras + radar | + blind spot CAN + microphone |

---

## Roadmap

- [ ] Bolt EV LT longitudinal support (pedal interceptor)
- [ ] Blind spot CAN signal integration for non-ACC vehicles
- [ ] Audio-based driver alertness detection (DSP + microphone)
- [ ] Side camera support via USB input
- [ ] Upstream contributions back to openpilot / opendbc

---

## Hardware

- **comma three** — required (same as openpilot)
- **comma pedal / TinyBear pedal interceptor** — required for Bolt EV LT longitudinal control
- **USB microphone** — optional, for audio driver monitoring

---

## Getting Started

Argus tracks openpilot's master branch. Setup is identical to openpilot:

```bash
git clone https://github.com/devk-op/argus.git
cd argus
# Follow openpilot's setup instructions for your platform
```

For Bolt EV LT setup, see [docs/bolt_ev_lt.md](docs/bolt_ev_lt.md) *(coming soon)*.

---

## Contributing

Pull requests welcome. If you drive a GM vehicle without ACC and want longitudinal support, open an issue with your CAN fingerprint data.

---

## Credits

Built on top of [openpilot](https://github.com/commaai/openpilot) by comma.ai (MIT License).
Bolt pedal interceptor work originally by [@firestar5683](https://github.com/firestar5683) in [sunnypilot](https://github.com/sunnypilot/sunnypilot).
