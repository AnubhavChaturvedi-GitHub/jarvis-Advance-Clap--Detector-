# Clap Detection using PyAudio

This Python script utilizes the `pyaudio` library to detect claps from an audio input stream. It employs the RMS (Root Mean Square) amplitude of the audio signal to identify clapping sounds. Adjust the sensitivity parameters and the required number of claps as needed.

## Prerequisites

Make sure you have the required library installed before running the script:

```bash
pip install pyaudio
```

## Usage

```python
from your_script_name import clap_detect

# Start clap detection
clap_detect()
```

## Configuration

Adjust the following constants based on your requirements:

- `INITIAL_TAP_THRESHOLD`: Initial threshold for detecting claps.
- `FORMAT`: Audio format (default is `pyaudio.paInt16`).
- `CHANNELS`: Number of audio channels.
- `RATE`: Sampling rate.
- `INPUT_BLOCK_TIME`: Duration of each audio block.
- `OVERSENSITIVE`: Sensitivity for detecting claps.
- `UNDERSENSITIVE`: Insensitivity threshold.
- `MAX_TAP_BLOCKS`: Maximum number of consecutive tap blocks.
- `REQUIRED_CLAPS`: Number of claps required to trigger detection.

## Code Explanation

1. **Dependencies:**
   - `pyaudio`: Library for audio input/output.

2. **Configuration:**
   - Adjust the constants based on your preferences for sensitivity, audio format, and other parameters.

3. **Class `TapTester`:**
   - Manages the PyAudio stream and handles clap detection.
   - Initializes the PyAudio stream for microphone input.

4. **Functions:**
   - `find_input_device()`: Finds the input device (microphone).
   - `open_mic_stream()`: Opens the microphone stream with the specified configuration.
   - `get_rms(block)`: Calculates the Root Mean Square amplitude of an audio block.
   - `listen()`: Listens to the audio stream and detects claps based on amplitude.

5. **Clap Detection Loop:**
   - The `clap_detect()` function initializes the `TapTester` and continuously listens for claps.
   - When the required number of claps is detected, it prints a message indicating a clap has been detected.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
