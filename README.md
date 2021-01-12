# EmoDJ Music Player

<a href="https://www.buymeacoffee.com/peggypytang" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a> Buy me a ☕️ if you like and want to support my projects. :)

## TL;DR

EmoDJ is a brand-new offline music player desktop application that focuses on improving listeners' emotional wellness. 

This application is designed based on psychology theories. It is powered by state-of-the-art AI technology to automatically identify music emotion of your songs. 

## Key Features

* AI-powered music emotion recognition - identify music emotions automatically for songs in your music library.
* Innovative music retrieval panel - organise songs based on psychology theories and retrieve songs from your music library by music emotion.
* Playlist recommendation - keep on playing songs with similar music emotion.
* No fee, no ad, no tracking. Completely offline.

## Motivation

Psychology researches show that music could change and support our mood. The power of mood regulation is the main reason why so many of us like to listen to music. We listen to music in our daily life, and we have different preferences for music in different emotional situations.

Often, we picked songs out of habit because we do not know what fits our mood. Sometimes, we relied on music streaming applications to feed us the pieces they think are "the best" for us. When we get songs that don't feel fit, for now, we can only keep clicking next and next, until we reach one that feels right. 

The existing music experience is yet to ideal. EmoDJ is designed to offer listeners to get the most out of the benefits of listening to music - enjoy music that can best improve our emotional wellness at our preference.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/russellcircumplexmodel.jpg" width="400px">
</p>
<p>
  <em> Russell's circumplex model - Jonathan Posner, James A. Russell, and Bradley S. Peterson. The circumplex model
of affect: An integrative approach to affective neuroscience, cognitive development, and psychopathology". In: Development and Psychopathology (2005) </em>
</p>

## Demo Video on Youtube

[![EmoDJ Demo](https://img.youtube.com/vi/TAzIjXN378Y/hqdefault.jpg)](https://www.youtube.com/watch?v=TAzIjXN378Y "Click to Watch the Demo Video")


## Design

#### Music Emotion Recognition Engine

The recognition engine would be used to annotate music emotion for music stored in the user library. Arousal-valence dimensional model was used. Music emotion, represented by arousal and valence values, is recognised and annotated both for the whole song and also for each 5 second timeframe. This music emotion information is used as a search index for retrieval and music visualisation.

#### Music Retrieval Panel

Four quadrants in arousal-valence space are represented by four colours correspondingly. 

💛 Quadrant with positive arousal and valence value (associates with **happiness**) is presented in green-yellow. 

💚 Quadrant with negative arousal and positive valence value (associated with **relaxation**) is presented in green-blue.

💙 Quadrant with negative arousal and valence value (associated with **sadness**) is presented in blue. 

❤️ Quadrant with positive arousal and negative valence value (associated with **anger**) is presented in red. 

#### Music Player and Recommendation Engine

In addition to standard functions including next, pause, resume, it provides recommendation function. Upon listener selected a piece of music, this engine would generate a playlist of recommended music based on music emotion similarity with the selected music piece, calculated by Euclidean distance. It would automatically play continuously, starting from the most similar one, until the playlist exhausts.

#### Music Visualisation Engine

This engine processes music data to generate music visualisation effects for each music. While playing music, colourful dynamic effect is generated simultaneously. Loudness and frequency, obtained by Fast Fourier Transform, controls magnitude of the effect. Time-varying music emotion controls colour, which has the same colour association as the music retrieval panel.

## System Configuration

EmoDJ is a desktop application based on Python 3 with GUI. Programs and resources required, including application codes, music emotion recognition models, index files, music files, are under 'EmoDJ Music Player' folder.

It has below folder structure:
```
EmoDJ Music Player
    ├── index                          # Folder with music emotion index files
    ├── model                          # Folder with music emotion recognition model
    ├── musics                         # Place your music files under this folder. The supported music file format is .wav.
    └── EmoDJ Music Player Code.ipynb  # Run this Jupyter notebook to start EmoDJ Music Player
```

Users are provided with a GUI to interact with the application, including browsing music information, retrieving music, pausing and resuming music. The screen would display live music visualisation.

For smooth execution of EmoDJ, ensure below packages are installed before execution is attempted. EmoDJ was tested under macOS Big Sur 11.1 with below package versions.
* tkinter (version 8.6)
* librosa (version 0.6.3)
* pygame (version 1.9.6)

## Getting Started

**User should copy whole 'EmoDJ Music Player' folder and store in their local device.**

**1. Import Music:**

Music files should be placed under 'EmoDJ Music Player/musics' folder. The supported music file format is .wav. Sample music files in the folder are from Free Music Archive.

Upon launching EmoDJ, unprocessed new music files will be recognised automatically to obtain their music emotion values. It may take a while to complete the music emotion recognition.

**2. Main Interface:**

To execute EmoDJ Music Player, the user should open the 'EmoDJ Music Player Code.ipynb' under 'EmoDJ Music Player' folder. To start EmoDJ for the first time, click 'Cell - Run All' in Jupyter notebook. To restart after quit, click 'Kernel - Restart and Run All' in Jupyter notebook.

Upon launching the application, users are presented with the main interface. Users perform operations via GUI by using a pointing device, such as a mouse and touchpad.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/1launch.jpg" width="600px">
</p>

**3. Browse Music Emotion Information:**

Upon hovering on markers in Music Retrieval Panel, song name, valence and arousal value of that piece of music is displayed.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/2browse.jpg" width="600px">
</p>

**4. Start Playing Music:**

Upon clicking on markers in Music Retrieval Panel, that selected piece of music will start playing. Live music visualisation is shown.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/3play.jpg" width="600px">
</p>

**5. Playlist Recommendation:**

Recommended music playlist based on music emotion similarity is generated upon select music to play, starting from the most similar one. Music currently playing is shown by the yellow marker. Music played are indicated by grey markers. It will play continuously until playlist exhausts. Notification will show when playlist reaches the end.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/4recommend.jpg" width="600px">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/5end.jpg" width="600px">
</p>

**6. Play Next Music in Playlist:**

To play next music in the playlist, click the 'Next' button.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/6next.jpg" width="600px">
</p>

**7. Resume/Pause Playing:**

To resume or pause the playing of music, click the 'Resume/Pause' button.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/7resume.jpg" width="600px">
</p>

**8. Quit EmoDJ:**

To quit EmoDJ, click 'Quit' button. To restart after quit, click 'Kernel - Restart and Run All' in Jupyter notebook.

<p align="center">
  <img src="https://github.com/peggypytang/EmoDJ/blob/main/manual_screenshot/8quit.jpg" width="600px">
</p>

## Troubleshooting

* **Unsychronisation of music visualisation and sound:**

The unsychronisation is due to the difference in system specifications. It could be solved by adjusting the 'SYNC' parameter under 'GUI Engine' section in "EmoDJ Music Player Code.ipynb".

* **Distorted GUI at a relaunch:**

The proper way to relaunch after quitting is by clicking 'Kernel - Restart and Run All' in Jupyter notebook. At this case, relaunch EmoDJ by clicking 'Kernel - Restart and Run All' in Jupyter notebook.

* **Music still playing after closing EmoDJ window:**

The proper way to exit EmoDJ is by clicking the 'Quit' button, this would stop the music and close EmoDJ window. At this case, it could be solved by clicking 'Kernel - Shutdown' in Jupyter notebook.
