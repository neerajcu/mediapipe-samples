# TensorFlow Lite Integration Notes

## What TensorFlow Lite Provides
- Google’s lightweight inference engine for running trained TensorFlow models directly on mobile and edge hardware.
- Optimized kernels for device CPUs and optional delegates (GPU, NNAPI, Hexagon) to keep inference on-device and low latency.
- Basis for MediaPipe Tasks and other high-level runtimes; even when not referenced directly, it often powers the underlying interpreters.

## Adding TensorFlow Lite to an Android App
- **Dependencies**: Include the runtime in `build.gradle`, for example `implementation "org.tensorflow:tensorflow-lite:<version>"`. Optional companions:
  - `tensorflow-lite-support` for metadata-aware preprocessing/post-processing helpers.
  - Delegate packages such as `tensorflow-lite-gpu`, `tensorflow-lite-select-tf-ops`, or `tensorflow-lite-hexagon` if the model requires them.
- **Model packaging**: Store `.tflite` files under `src/main/assets/` or download them during the build so they ship inside the APK/AAB. Large binaries can also be delivered through Play Feature Delivery.
- **Interpreter setup**: Create an `Interpreter` (or `InterpreterApi`) with appropriate `Options`. Configure delegates, threads, and `useNNAPI` flags to match target hardware and verify that tensor metadata aligns with the model’s requirements.
- **Alternatives**: Frameworks such as MediaPipe Tasks can wrap TensorFlow Lite, handling interpreter lifecycle, delegates, and pre/post-processing. In those cases, TensorFlow Lite remains an indirect dependency managed by the wrapper library.

## Official Documentation and Samples
- TensorFlow Lite guide: https://www.tensorflow.org/lite/guide
- TensorFlow Lite example gallery: https://www.tensorflow.org/lite/examples
- TensorFlow Lite Android quickstart: https://www.tensorflow.org/lite/android
