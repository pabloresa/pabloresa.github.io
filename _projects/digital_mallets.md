---
layout: project
title: "Digital Mallets"
description: "Taking mallets into the digital world on a budget"
image: /assets/img/mallet/mallet.jpg
permalink: /mallets/
---

# Crafting Digital Rhythms: Building a Standalone Wooden Mallet with ESP32 and Integrated Synthesis

As makers, we are constantly seeking to bridge the gap between physical interaction and digital creativity. My latest conceptual project explores this convergence by envisioning a digital mallet – a beautifully crafted wooden instrument that not only transmits MIDI data but also generates its own sounds internally. This endeavor harnesses the versatile ESP32 microcontroller, leveraging the `HelloDrum-arduino-Library` for precise strike detection and `esp32_basic_synth` for on-board audio generation.

**The Heart of the Mallet: Wood and Wireless Power**

The choice of wood for the mallet's body is deliberate. Beyond its aesthetic appeal, wood offers excellent acoustic properties and a natural tactile feel, aligning with the organic nature of musical expression. Designing a comfortable yet robust form factor would be paramount, ensuring that the mallet feels balanced and responsive in hand.

At its core, the mallet would house an **ESP32 microcontroller**. This powerful chip is the ideal choice due to its integrated Wi-Fi and Bluetooth capabilities, robust processing power, and ample GPIO pins. These features are crucial for handling sensor input, managing MIDI communication, and driving an internal audio engine simultaneously. Power would be supplied by a small, rechargeable LiPo battery, making the mallet truly portable and self-contained.

**Sensing the Strike: Precision with `HelloDrum-arduino-Library`**

To translate a physical strike into a digital signal, the mallet would incorporate an accelerometer (e.g., an MPU6050 or similar) strategically placed within its head. This sensor would detect impact and measure strike velocity. This is where **RyoKosaka's `HelloDrum-arduino-Library`** becomes indispensable.

This library is designed to simplify drum hit detection using accelerometers, providing a robust framework for identifying strikes, distinguishing between different intensities (essential for velocity-sensitive MIDI), and filtering out spurious noise. By integrating `HelloDrum`, I aim to achieve highly responsive and accurate triggering of musical notes, ensuring that every nuance of the performance is captured digitally.

**Crafting Internal Sound: The `esp32_basic_synth` Integration**

While MIDI output offers immense flexibility for connecting to Digital Audio Workstations (DAWs) or external synthesizers, the true magic of this project lies in its ability to produce sound autonomously. This is where **marcel-licence's `esp32_basic_synth` library** comes into play.

This lightweight yet capable synthesis library allows the ESP32 to generate basic audio waveforms and polyphonic sounds directly. By connecting a small speaker or a headphone jack to the ESP32's audio output (perhaps via a simple DAC or I2S amplifier), the mallet can become a completely self-contained instrument. Imagine striking the wooden head and hearing a crisp percussion sound, a synthesized drum, or even a simple melodic tone emanating directly from the mallet itself!

**The Dual Modality: MIDI and Standalone Synthesis**

The beauty of this design is its dual functionality. The mallet would be capable of:

1.  **MIDI Output:** Transmitting velocity-sensitive MIDI Note On/Off messages via **Bluetooth MIDI (BLE MIDI)** to a DAW, a hardware synthesizer, or another MIDI-compatible device. This opens up a world of sonic possibilities, allowing the mallet to control any virtual instrument or external sound module. USB MIDI could also be an option for wired connections and firmware updates.
2.  **Internal Synthesis:** Generating immediate audio feedback through the integrated `esp32_basic_synth`. This mode is perfect for practice, impromptu jamming, or performance where external equipment is not desired or available. I could program different "kits" or patches within the synth – perhaps a basic drum kit, a melodic marimba, or abstract percussive sounds – switchable via a small button on the handle.

### Beyond the Basics: Future Enhancements

Looking ahead, several enhancements could further refine this digital mallet:

* **Parameter Control:** Integrating a small gyroscope or additional buttons to control synth parameters (e.g., decay, pitch bend, filter cutoff) through subtle gestures or direct input.
* **Haptic Feedback:** Adding a small vibration motor to provide haptic feedback upon strike, enhancing the realism of the physical interaction.
* **Customizable Sounds:** Developing a simple web interface (hosted on the ESP32's Wi-Fi) to allow users to upload or customize basic synth parameters or even short samples.

This digital mallet project is more than just a musical instrument; it's an exploration into the tactile and audible possibilities of embedded systems. By combining the natural warmth of wood with the raw power of the ESP32 and clever software libraries, I aim to create a truly unique and inspiring tool for makers and musicians alike. The journey of crafting sounds from physical gestures, all from a self-contained, custom-built device, is incredibly rewarding.

---
