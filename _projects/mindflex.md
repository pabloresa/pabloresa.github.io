---
layout: project
title: "Controlling music with your mind"
description: "Fun concept of touchless digital instrument"
image: /assets/img/mindflex/cube.png
permalink: /mindflex/
---

## Capactive cube with MindFlex musical instrument

This project, “Cuerpo y mente - Un hecho tangible” (Body and Mind - A Tangible Fact), represents my endeavor to create a novel wireless musical instrument that integrates human bio-signals with interactive sound generation. My objective was to explore advanced forms of musical interaction beyond conventional interfaces, drawing inspiration from non-contact systems such as the Theremin. The conceptual foundation for this instrument emerged from studying the Mattel Mindflex toy, which demonstrated the practical application of EEG brainwave technology for control. Recognizing the accessibility and potential of its EEG sensor , I initiated this project to repurpose such technology for a sophisticated musical application. The resulting instrument is a complex technological integration , centrally featuring a truncated icosahedron, which I refer to as the “CUBE”. The system comprises several key components: 

-***Mindflex Headband***: This component is responsible for acquiring brainwave data, specifically measuring levels of relaxation and attention.

![Mindflex](/assets/img/mindflex/mindflex.png)

-***CUBE Unit***: Designed as a physical structure, the CUBE integrates capacitive sensors for touchless interaction and an embedded LED lighting system.

![Cube](/assets/img/mindflex/cube.png)

-***Arduino Pro Micro Boards***: Multiple Arduino units are interconnected to manage sensor inputs, process data, and control the LED outputs.

-***Raspberry Pi 3B+***: This serves as the primary processing unit for audio synthesis, executing the PureData software environment.

-***Communication Protocols***: Bluetooth (HC05 modules) , MIDI , and UART protocols facilitate robust communication across all integrated components.

![All together](/assets/img/mindflex/music_with_your_mind.png)

### Operational Modality:

The instrument functions by translating physical proximity and mental states into ambient musical output. As one approaches the CUBE, capacitive sensors trigger the generation of musical chords. Concurrently, my internal mental state directly influences the musical parameters: the level of relaxation derived from the Mindflex dictates the rhythmic pulsation , while the degree of attention shapes the underlying melodic line within a Lydian mode.

### Development Challenges and Resolutions:

The execution of this project presented several significant technical challenges. A primary hurdle involved establishing reliable Bluetooth communication; I ultimately settled on HC05 modules due to stability issues encountered with HC06 modules. Serial communication also required iterative problem-solving as I progressively integrated additional functionalities into the CUBE. To manage multiple sensor data streams efficiently, I implemented a two-message communication system where the first message identifies the sensor and the second conveys its value, preserving data resolution. Furthermore, managing the inherent instability of capacitive sensor readings necessitated the implementation of an exponential weighted moving average for signal smoothing, ensuring consistent performance. This project stands as a testament to the successful integration of diverse hardware and software components to create a profoundly interactive and personalized artistic experience. It underscores the transformative potential of interdisciplinary approaches in the realm of maker projects and technological innovation.
