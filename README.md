# OpenInApp_task2
TASK
Create a voice cloning model that can generate a synthetic voice that sounds like a specific person. Here extract
a voice of a speaker from online who is for example giving a speech/ TED talk in (English/Hindi/Telugu) for at
least 1 minute. Clone this speaker’s voice to a different language (English/Hindi/Telugu) with the same pitch, and
audio tone, and it should be able to reproduce the unique vocal characteristics of the target speaker.
Example: (Let's say you have extracted audio of Elon Musk giving a speech in English, your task is to change the
language of Elon Musk’s same speech to another language to Hindi/Telugu. It should be as if Elon Musk himself
is talking in Hindi/Telugu).

This code implements a simplified version of a voice cloning model.
This function, extract_spectrogram, takes an audio signal as input and computes its spectrogram using Short-Time Fourier Transform (STFT). 
The resulting spectrogram is then log-scaled for feature extraction purposes.
The TacotronEncoder class defines an encoder layer. It uses a 1D convolutional neural network to process the input spectrogram and extract 
high-level features from it.
The TacotronDecoder class defines a decoder layer. It uses a dense (fully connected) layer to decode the features extracted by the encoder 
and prepare them for synthesis.
The WaveNet class defines a simplified WaveNet-like architecture. It consists of a series of 1D convolutional layers with dilated convolutions, 
followed by a final convolutional layer for output.
The VoiceCloningModel class integrates the encoder, decoder, and WaveNet layers to create the complete voice cloning model. It takes a dictionary 
inputs containing a key 'source_spectrogram' representing the input spectrogram and processes it through the encoder, decoder, and WaveNet layers to generate the output audio.
