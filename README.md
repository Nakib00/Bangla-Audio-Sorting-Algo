# Audio Splitting Algorithm

This repository contains code for splitting audio files based on silence using Python and the PyDub library.

## Prerequisites
- Python 3.x
- PyDub library (`pip install pydub`)
- matplotlib (`pip install matplotlib`)
- scipy (`pip install scipy`)

## Usage

### Splitting Audio
1. Import necessary libraries.
2. Provide the source audio file path (`src`).
3. Define the minimum silence length (`minS`) and silence threshold (`silanceT`).
4. Use the `audio_split` function to split the audio based on the specified parameters.
5. Adjust the parameters until desired results are achieved.
6. Specify the destination folder (`des_folder`) where the split audio chunks will be saved.
7. Run the script to split the audio file and export the chunks to the destination folder.

### Testing Split Audio
1. Provide the path to the split audio file for testing.
2. Use the `IPython.display.Audio` function to play the split audio chunk.

## Example
```python
# Import necessary libraries
from pydub import AudioSegment
import numpy as np
from pydub.silence import split_on_silence
from pydub.playback import play
import IPython
from scipy.io.wavfile import read
import matplotlib.pyplot as plt
import IPython.display
import os

# Provide the source audio file path
src='path/to/your/audio/file.wav'

# Define parameters for splitting audio
minS = 250
silanceT = -32

# Split the audio file
audio_chunks = split_on_silence(audio, min_silence_len=minS, silence_thresh=silanceT)

# Specify the destination folder
des_folder = 'path/to/destination/folder'

# Export the chunks to the destination folder
for i, chunk in enumerate(audio_chunks):
    out_file = os.path.join(des_folder, f"chunk{i+1}.wav")
    chunk.export(out_file, format="wav")


## Contributing

Contributions are welcome! For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -am 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request


You can modify and expand this README as needed to provide more information about your project. Let me know if you need further assistance!

