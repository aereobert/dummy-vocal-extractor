# dummy-vocal-extractor

This is a tool to extract instrumental track from your songs.
Some code are from tsurumeso/vocal-remover, which is a deep-learning-based tool.
This dummy code is intented for generating deep-learning dataset.

It takes 
1. music with vocal
2. music without vocal

and generates vocal

by 

1. Upsample the audio file for more precise alignment (with cubic interpolating)
2. Calculate alignment point for beginning and end of the audio file
3. Cut audio, and align the audio by resampling
4. Downsampling

Advantages:
1. Performs better than deep-learning-based system. (of course)
2. Fixes sample alignment issues caused by software used by studios. (typically 1-50 samples for 44100HZ audio music file)

Known issues (pull requests are welcomed!):
1. Can only work with original flac/wav file, otherwise may perform bad.
2. Audio file must already be well-aligned at head and tail, otherwise the software will not find align points.
3. Slight gliches with high-frequency voice.
4. Still little BGM not filtered.
5. Takes astonishing time to process
