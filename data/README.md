# Divvun speech-sme

## ASR 

### Sametinget-north-transcribed-v1

#### About the data set

- The original, untouched sound files that were downloaded from the sametinget website (https://sametinget.kommunetv.no/archive)
- Download date from the source: 30.1.2023
- The folder contains the part of the material that is fully processed to an ASR training data set
- Transcriptions were done in Divvun, UiT between 30.5.-28.12.2023.
- Note that this folder contains only a subset of the material from the website. Of nearly 100 hours of North Sámi speech found from the source, this data set only contains North Sámi utterances of medium length (11-30 seconds long). 
- The transcribed data set consists of 6 batches (sametinget_bX_north and transcriptions_sametinget_bX_north.txt), each with 1500-2500 utterances. The data set is roughly 26,7 hours out of the 100 hours total audio found from the website.

##### How the data set was produced

0) Downloading the material from the website mentioned above. Cut and clean the audio from long silences, noise, music...
1) Convert .mp3 -> .wav
2) Running speaker diarization and VAD (voice activity detection) using pyannote. Each unique speaker in each long audio recording has speaker codes/labels (e.g. s_02)
3) Checking all speech intervals from the resulting Praat TextGrid file. It was important to check that none of the intervals were more than 30 seconds long. If there were such intervals, these were split once more from a suitable/natural place in the speech.
4) Extracting the speech intervals to individual audio files, numbered splits while retaining the original file name from the downloaded file
5) Running the splits through our North Sámi whisper ASR
6) Manual transcription = Manual checking and fixing of the ASR output. This was done by a native North Sámi person working with Divvun.
