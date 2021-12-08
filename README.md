# Music_discrimination

This research project focuses on Discriminating between real and machine learning generated music.


###### Command used to replace spaces with _ in file names; cmd into the directory where all the mid/midi files are present; run the following command in powershell:

```
get-childitem *.mid | foreach {rename-item $_ $_.name.replace(" ","_")}
```

All the notebooks have been run on Google Colab Pro. The data file paths will be needed to be changed within all the notebooks. There are comments wherever the changes are needed.


For using the data which is already prepared download from [**here**](https://zenodo.org/record/5715702#.YZhx92BBy3B)



For creating dataset from scratch use the steps mentioned below in the Data Preparation Notebooks section and maintain the given directory structure given below:
```
|-- music_data
    |-- images
        |-- chroma
            |-- adl
            |-- gen
        |-- mfcc
            |-- adl
            |-- gen
        |-- spect
            |-- adl
            |-- gen
    |-- midi
        |-- adl_200_mid
        |-- adl_piano
        |-- gen_200_mid
        |-- generated_midi
    |-- models
    |-- plots
    |-- wav
        |-- adl_wav
        |-- gen_wav
    |-- adl_mid_to_wav.sh
    |-- gen_mid_to_wav.sh
```

ADL refers to the samples from the **ADL piano dataset** which can be found [here](https://github.com/lucasnfe/adl-piano-midi).\
The final leaf node folders have all the data files.\
The images folder contains all the feature folders, each having a different folder for adl and gen, which contain the 200 images for the 200 wav files.\
The midi folder contains 4 folders, the adl_piano folder has around 1600 midi files and the adl_200_mid contains the 200 randomly selected files for audio conversion. The same structure follows for the gen files.\
The wav folder contains two folders adl_wav and gen_wav which contain the wav files of both the classes.


## Data Preparation notebooks

1. The "Generating_Piano_Music_with_Transformer.ipynb" notebook is used to create machine learning generated music.  
2. Use the "convert_midi_to_wav.ipynb" to convert the 200 randomly selected midi files to wav. This notebook uses the shell scripts available in the main music_data directory.
3. Use the "generate_audio_features.ipynb" notebook to create the image features from the 200 wav files.

We have all the data ready for both MIDI and Audio classification.


## MIDI Classification
Use the "midi_classifier.ipynb" notebook for midi classification. 


## AUDIO Classification
Use the "wav_classification.ipynb" notebook for the base models for the audio classification.\
Use the "wav_classification_transfer_learning.ipynb" notebook for the base models for the audio classification. 




