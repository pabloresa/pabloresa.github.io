---
layout: project
title: "Digital Marimba"
description: "Taking mallets into the digital world on a budget"
image: /assets/img/mallet/mallet.jpg
permalink: /mallets/
---

## DIY Digital Marimba

![Mallet](/assets/img/mallet/mallet.jpg)

As makers, we are constantly seeking to bridge the gap between physical interaction and digital creativity. This project explores this convergence by envisioning a digital marimba – a hand-crafted wooden instrument that transmits MIDI data and generates its own sounds internally. Using the great `HelloDrum-arduino-Library` for precise strike detection and `esp32_basic_synth` for on-board audio generation, we can get something similar to Xylosynth for a fraction of the price.

### The Sound Heart of the Marimba: ESP32

The choice of wood for the mallet's body is deliberate. Beyond its aesthetic appeal, wood offers excellent acoustic properties and a natural tactile feel, aligning with the organic nature of musical expression. Designing a comfortable yet robust form factor was crucial, ensuring that the mallet feels balanced and responsive in hand.

At its synth core, the mallet houses an **ESP32 microcontroller**. This powerful chip is the ideal choice due to its integrated Wi-Fi and Bluetooth capabilities, robust processing power, and ample GPIO pins. These features are crucial for handling sensor input, managing MIDI communication, and driving an internal audio engine simultaneously. Power is supplied by a rechargeable 18650 battery, making the mallet truly portable and self-contained. However, despite my original intention, I ended using it mainly as a MIDI device.

### Sensing the Strike: Precision with `HelloDrum-arduino-Library` and Teensy 3.2

To translate a physical strike into a digital signal, the marimba uses a piezo for each plate, which is then sensed by the Teensy. This sensor detects impact and measure strike velocity as [**RyoKosaka's `HelloDrum-arduino-Library`**](https://github.com/RyoKosaka/HelloDrum-arduino-Library) describes.

This library is designed to simplify drum hit detection using accelerometers, providing a robust framework for identifying strikes, distinguishing between different intensities (essential for velocity-sensitive MIDI), and filtering out spurious noise.

### Crafting Internal Sound: The `esp32_basic_synth` Integration

While MIDI output offers immense flexibility for connecting to Digital Audio Workstations (DAWs) or external synthesizers, it's interesting to have the ability to produce sound autonomously. This is where **marcel-licence's `esp32_basic_synth` library** comes into play. Although a sampler can be used, in this case I preferred the synth way.

This lightweight yet capable synthesis library allows the ESP32 to generate basic audio waveforms and polyphonic sounds directly. By connecting a small speaker or a headphone jack to the ESP32's audio output (perhaps via a simple DAC or I2S amplifier), the mallet can become a completely self-contained instrument. Check the code [here](https://github.com/pabloresa/ArduinoMIDIDevices/blob/main/MarimbaMuxSerialUSB.ino)

### The Dual Modality: MIDI and Standalone Synthesis

The beauty of this design is its dual functionality. The mallet is capable of:

1.  **MIDI Output:** Transmitting velocity-sensitive MIDI Note On/Off messages via **MIDI-USB** via the Teensy 3.2. This opens up a world of sonic possibilities, allowing the mallet to control any virtual instrument or external sound module.
2.  **Internal Synthesis:** Generating immediate audio feedback through the integrated `esp32_basic_synth`. If you are interested, [Marcel Licence Youtube Channel](https://www.youtube.com/channel/UCwrPhahCO1i1n5MPMDT9T_g) is full of great experiments with his libraries.

### Beyond the Basics: Future Enhancements

Looking ahead, several enhancements could further refine this digital mallet:

* **Double Piezo:** Getting more precision is achievable adding a second piezo to each plate.
* **Haptic Feedback:** Adding a small vibration motor to provide haptic feedback upon strike, enhancing the realism of the physical interaction.
* **Customizable Sounds:** Developing a simple web interface (hosted on the ESP32's Wi-Fi) to allow users to upload or customize basic synth parameters or even short samples.

---
