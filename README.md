# DeepGenerativeMusic

### All code seen here can also be accessed via our shared Google Drive, located at https://drive.google.com/drive/folders/19Ze1XoEjlP1qLx0WrvZHtoPdlStXS7-P?usp=sharing.

This repository contains all the code required to reproduce the preprocessing, training, and music generation of the 5 deep learning models we employed in this study. 
1. Pure_Transfomer contains the self-attention only model
2. Pure_RNN contains the RNN model without self-attention
3. RNN_Transformer contains the single-stacked RNN + self-attention baseline
4. Innovations:
   We employed 2 innovations in this study: a double-stacked RNN and a triple-stacked RNN (both with self-attention layer(s)).  The training files for each of these models can be found in this folder
   
   
   
Each of these model folders contains a similar structure of files.  We will describe the key files below:

### (Note: We used the following GitHub repo as our initial reference for our RNN+self-attention models: https://github.com/haryoa/note_music_generator

### preprocess.midi.ipynb
  - This is the preprocessing file we used to transform the Maestro MIDI files into the NoteTokenizer dictionary format that our model used.  It imports dependencies a text file titled **requirements.txt**. It outputs the saved dictionary in the **pickles** folder 
  
### model_train.ipynb
  - This is the file we used to train each model on the preprocessed data.  It imports dependencies from **requirements.txt**.  It also directly calls and run **preprocess.midi** to create the processed data pickle file and import the NoteTokenizer object.  
  - The model created by this file is saved as **this_model.png**
  - It outputs two pickle files
    1. an .h5 file corresponding to the trained model.  This is saved in the **pickles** folder
    2. a .p file corresponding to the processed NoteTokenizer object from the **preprocessed_midi.ipynb** file
 
 ### model_inference.ipynb
   - This is the file used to generate new music samples using our trained model.  It takes .h5 and .p files as input, and produces .mid files as output in the **output** folder.


The survey we used in our user evaluation can be found at: https://forms.gle/igEDSYmLcgH9Cc2YA 
