# yw
Audio Layers

To install:	```pip install yw```

## Overview
The `yw` package provides a comprehensive suite of tools for audio processing and manipulation in Python. It leverages popular libraries such as `numpy`, `librosa`, `soundfile`, and `matplotlib` to offer functionalities like audio file conversion, resampling, waveform manipulation, and audio visualization.

## Features
- **Audio Conversion**: Convert audio files to different formats and sample rates using `convert_to_wav`.
- **Waveform Manipulation**: Functions to ensure mono audio, resample audio, and manipulate waveforms with operations like adding silence.
- **Audio Information Extraction**: Retrieve detailed information from audio files, such as duration, sample rate, and format-specific data.
- **Audio Visualization**: Plot waveforms and spectrograms to visualize audio data.
- **Sound Object**: A `Sound` class that encapsulates audio data along with utility methods for easy manipulation and analysis.

## Usage Examples

### Converting Audio Files to WAV
Convert any audio file format supported by `ffmpeg` to WAV format with a specified sample rate:
```python
from yw import convert_to_wav

convert_to_wav('input.mp3', 'output.wav', sample_rate=44100)
```

### Extracting Audio File Information
Get detailed information from a WAV file:
```python
from yw import sound_file_info_dict

info = sound_file_info_dict('example.wav')
print(info)
```

### Plotting a Waveform
Visualize the waveform of an audio file:
```python
from yw import display_sound

display_sound('path/to/audio.wav')
```

### Working with the Sound Class
Create a `Sound` object from a file, manipulate it, and save the output:
```python
from yw import Sound

sound = Sound.from_file('input.wav')
sound.resample(new_sr=22050)
sound.save_to_wav('output_resampled.wav')
```

### Mixing Audio
Mix two audio files into one by adjusting their relative weights:
```python
from yw import Sound

sound1 = Sound.from_file('audio1.wav')
sound2 = Sound.from_file('audio2.wav')
sound1.mix_in(sound2, weight=0.5)
sound1.save_to_wav('mixed_output.wav')
```

## Documentation
Each function and class in the `yw` package comes with detailed docstrings that provide more information on their usage and parameters. Here are some key functions/classes and their purposes:

- `convert_to_wav(source_file, target_file=None, sample_rate=44100)`: Convert an audio file to WAV format.
- `sound_file_info_dict(filepath)`: Retrieve a dictionary containing information about the audio file.
- `display_sound(filepath)`: Plot and play an audio file.
- `Sound`: A class that represents an audio signal, with methods like `from_file`, `resample`, `mix_in`, and `save_to_wav` for handling audio data.

For more detailed information, refer to the docstrings provided within the code.