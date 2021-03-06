# Project Miles Ahead  
Building off the TensorFlow model [magenta](https://github.com/tensorflow/magenta), Project "Miles Ahead" attempts to expand Deep Learning Jazz Generation by enhancing the recurrent neural network "Lookback RNN".

In addition, through the use of Music21 and matplotlib, Project Miles Ahead will conduct Exploratory Data Analysis and robust Data Visualization to explore the music created by the model.  Utilizing the same comparison on music created by legendary jazz pianist, Bill Evans, this project seeks insight in to the "humanity" of the computer generated music. 

*Project still in progress and will be updated over time.*

###For a high level overview of the project take a look at the "Miles Ahead Presentaion" pdf file.  For a deeper dive, head over to the Exploratory Data Analysis section.

# Take a listen
generated using the modified TensforFlow magenta model using 13,500 steps/epochs.

[![SoundCloud](https://github.com/Mithers/Portfolio/blob/master/Project%20Miles%20Ahead/Assets/button_soundcloud.png)](https://soundcloud.com/chris-shoe-523970434/project_miles_solo)

A sample of the Mile's solo in score form:

![score](https://github.com/Mithers/Portfolio/blob/master/Project%20Miles%20Ahead/Assets/miles_score.png)

### EDA Examples
Graphing the miles solo as keyboard patterns:

![miles_keyboard](https://github.com/Mithers/Portfolio/blob/master/Project%20Miles%20Ahead/Assets/Miles_Keyboard.png)

Miles solo rhythmic patterns as applied to a kmeans clustering:

![miles_kmeans](https://github.com/Mithers/Portfolio/blob/master/Project%20Miles%20Ahead/Assets/miles_Kmeans.png)

### Dependencies

- [magenta](https://github.com/tensorflow/magenta)
- [music21](http://web.mit.edu/music21/doc/installing/index.html)
- [matplotlib](http://matplotlib.org/contents.html)

### Process

Project Miles ahead was conducted in a remote server environment utilizing [Linode](https://www.linode.com/) and an [Ubuntu](http://www.ubuntu.com/) framework.  It is advised if replicating the project to utilize a similar infrastructure due to the processing requirements of the TensorFlow library.

1) Modify built in `melody_encoder_decoder.py` file with `melody_generator.py` contents.

2) Run `midi_db.sh` on remote server:

```
midi_db.sh
```

Note: `midi_db.sh` can be edited to utilize larger batch sizes if your processor can handle it.  Also make sure to adjust `num_training_steps` if you do not want to run 20,000 training steps.

3) Sit back and enjoy a fine beverage with one of your favorite jazz records - it's gonna be a while.

4) Hey! Wake up! Your models are done!

5) Run `melody_creation.sh` to generate melodies.  

Note: `melody_creation.sh` can be edited to change location of midi files by changing `--output_dir`.

From magenta GitHub:

"In addition `--primer_melody` can be edited to specify a primer melody.  The values in the list should be ints that follow the `melodies_lib.Melody` format (-2 = no event, -1 = note-off event, values 0 through 127 = note-on event for that MIDI pitch).  For example `primer_melody="[60, -2, 60, -2, 67, -2, 67, -2]"` would prime the model with the first four notes of Twinkle Twinkle Little Star.  Instead of using `--primer_melody`, we can use `--primer_midi` to prime our model with a melody stored in a MIDI file.  For example, `--primer_midi=<absolute path to magenta/models/shared/primer.mid>` will prime the model with the melody in the melody in that MIDI file.  If neither `--primer_melody` nor `--primer_midi` are specified, a random note from the model's note range will be chosen as the first one, then the remaining notes will be generated by the model."

### About Lookback RNN
From magenta GitHub:
 
"Lookback RNN introduces custom inputs and labels. The custom inputs allow the model to more easily recognize patterns that occur across 1 and 2 bars. They also help the model recognize patterns related to an events position within the measure. The custom labels reduce the amount of information that the RNN’s cell state has to remember by allowing the model to more easily repeat events from 1 and 2 bars ago. This results in melodies that wander less and have a more musical structure."

### Author

[Christopher Shoe](https://github.com/Mithers/Portfolio)  
General Assembly Data Science Immersive  
chris.m.shoe@gmail.com  

### Citations

Code was built while significantly referencing public examples from the Magenta documentation on GitHub: https://github.com/tensorflow/magenta

##### Project is solely for academic purposes and not for sale or distribution of any kind. 


                             