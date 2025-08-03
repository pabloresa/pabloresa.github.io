---
layout: project
title: "Capacitive touch keyboard"
description: "Experimenting with isomorphic keyboards and touch devices"
image: /assets/img/touch/touch.jpg
permalink: /touch/
---

## Crafting Intuitive Interfaces: Building a Touch Isomorphic Instrument with MPR121 and Teensy 3.2

![Touch](/assets/img/touch/touch.jpg)

In my continuous exploration of unconventional musical interfaces, I've embarked on a project to construct a touch-sensitive isomorphic instrument. This endeavor aims to bridge the intuitive consistency of isomorphic keyboard layouts with the immediate responsiveness of capacitive touch sensing, utilizing the MPR121 12-channel capacitive touch sensor and the powerful Teensy 3.2 microcontroller. My inspiration is deeply rooted in the philosophy behind alternative keyboard designs, as extensively documented on [Wikipedia](https://en.wikipedia.org/wiki/Isomorphic_keyboard) and the lost page [AltKeyboards](https://web.archive.org/web/20230330055946/http://www.altkeyboards.com/) , which underscore the pedagogical and performative advantages of isomorphic principles.

### The Isomorphic Imperative: Redefining Musical Interaction

The fundamental appeal of isomorphic layouts, such as the Wicki-Hayden or Janko, lies in their consistent intervallic relationships. Unlike the traditional piano keyboard, an isomorphic layout ensures that a specific musical interval or chord shape maintains the same physical pattern regardless of the key or octave. This geometric consistency significantly simplifies transposition, streamlines the learning of scales and chords, and can unlock new avenues for musical expression. My instrument directly confronts the limitations of standard interfaces by adopting a layout where musical patterns are physically predictable, providing an unparalleled clarity for both learning and advanced performance.

### At the Core: MPR121 and Teensy 3.2

The technical foundation of this instrument is built upon two highly capable components:

  * **MPR121 12-channel Capacitive Touch Sensor:** This dedicated IC is the primary interface for user interaction. Its 12 distinct electrode channels are ideal for creating a compact yet versatile isomorphic grid. The MPR121 excels at detecting human touch through changes in capacitance, offering a responsive and reliable method of input. Each touch plate on the instrument will be wired to a specific channel of the MPR121, providing the necessary resolution for individual note triggering.
  * **Teensy 3.2 Microcontroller:** I selected the Teensy 3.2 as the central processing unit due to its compact footprint, robust ARM Cortex-M4 processor, and critically, its native USB MIDI capabilities. The Teensy's processing speed is more than adequate for reading data from the MPR121 via I2C, mapping touch events to specific MIDI notes, and transmitting these messages with minimal latency. Its integrated USB MIDI functionality ensures seamless, plug-and-play compatibility with Digital Audio Workstations (DAWs) and other MIDI-enabled hardware, eliminating the need for external MIDI interfaces.

### Translating Touch to Tone: Software and MIDI Implementation

The software running on the Teensy 3.2 is responsible for translating the raw touch data from the MPR121 into meaningful musical information. This involves:

1.  **Data Acquisition:** Continuously reading the touch status of all 12 channels from the MPR121 via an I2C communication bus.
2.  **Isomorphic Mapping:** Implementing a precise mapping algorithm that correlates each activated touch electrode to a specific MIDI note number, based on the chosen isomorphic layout (e.g., a 2x6 or 3x4 grid for a 12-key setup). This mapping ensures the inherent musical logic of the isomorphic design is preserved.
3.  **MIDI Message Generation:** Upon detecting a touch (or release), the Teensy generates standard MIDI Note On/Off messages. While the MPR121 itself does not provide pressure sensitivity, I am exploring methods to infer velocity through parameters like touch duration or rate of capacitance change, adding a crucial layer of expressiveness to the output.
4.  **USB MIDI Transmission:** Leveraging the Teensy's built-in USB MIDI, these messages are sent directly to a connected computer or MIDI host, allowing the instrument to control virtual instruments, hardware synthesizers, or even lighting systems.

### Physical Realization: From Concept to Tangible Form

The physical construction of the instrument is as critical as its electronic core. I envision a sleek, durable enclosure, potentially crafted from laser-cut acrylic or meticulously milled wood, providing both protection and an ergonomic interface. The touch plates themselves could be fashioned from conductive materials such as copper tape, conductive paint applied to a non-conductive substrate, or even custom-designed PCBs for a professional finish. An overlaid clear acrylic panel would serve to protect the conductive elements while allowing for visual labeling of the isomorphic layout. The iterative process of prototyping various layouts and enclosure designs is essential to optimize playability and aesthetic appeal.

### Expanding Horizons: Applications and Future Potential

This touch isomorphic instrument serves as a versatile MIDI controller for a wide array of musical applications, from studio production with virtual instruments to live performance with hardware synthesizers. Its unique interface encourages novel playing techniques and can be a powerful tool for musical exploration.

Looking to the future, the design offers significant avenues for expansion:

  * **Larger Layouts:** Integrating multiple MPR121 chips to construct a more expansive isomorphic grid, allowing for a broader range of notes and chords.
  * **Visual Feedback:** Incorporating an OLED display or individual LEDs per key to provide visual feedback on active notes, scales, or selected modes.
  * **Enhanced Control:** Adding physical potentiometers or buttons to the enclosure for on-the-fly control of MIDI CC messages, octave shifts, or patch changes on the connected synthesizer.
  * **Integrated Synthesis:** While currently focused on MIDI output, future iterations could explore integrating a small audio output and a basic internal synthesizer, similar to my previous projects, to create a truly standalone instrument.

This project is not merely about building a device; it is about re-imagining how we interact with music. By meticulously crafting a touch-sensitive isomorphic interface, I aim to provide a more intuitive and musically coherent experience, fostering both technical mastery and creative liberation for musicians and makers alike.

---
