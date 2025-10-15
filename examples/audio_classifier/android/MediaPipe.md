# MediaPipe Overview

## What MediaPipe Is
- Google’s cross-platform framework for composing multimodal ML pipelines using reusable graph components (“calculators”).
- Provides standardized building blocks for input capture, feature extraction, inference, and post-processing across platforms (Android, iOS, web, desktop).
- Powers higher-level libraries such as MediaPipe Tasks, which expose opinionated APIs for common model families (vision, audio, text).

## Why It Simplifies AI Development
- **Prebuilt pipelines**: Ready-made graphs (for example, the YamNet audio classifier) encapsulate DSP steps such as FFTs, spectrogram generation, and label filtering.
- **Cross-platform parity**: Identical task APIs run on multiple operating systems, enabling teams to reuse model logic.
- **Performance focus**: Optimized schedulers, streaming I/O, and delegate integration deliver real-time inference with minimal plumbing.
- **Extensibility**: Developers can author custom calculators or swap models while reusing existing graph infrastructure.
- **Interpreter abstraction**: When using Tasks, MediaPipe manages TensorFlow Lite interpreters, delegates, and pre/post-processing so applications rarely interact with `Interpreter` APIs directly.

## Key Resources
- MediaPipe home: https://developers.google.com/mediapipe
- MediaPipe Tasks overview: https://developers.google.com/mediapipe/solutions
- Audio classifier task documentation: https://developers.google.com/mediapipe/solutions/audio/audio_classifier
- Custom pipeline guidance: https://google.github.io/mediapipe/solutions/customization/python_api
