# AIG
Artifical Intelligence Group - project - investigation trigger word detector 
Alex Wormald - 14/06/2023

# Possible extensions:
Consider applying architecture from: https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43969.pdf
OR changing the input data set.


# Data set
Data set from Tensorflow speech_commands:
http://download.tensorflow.org/data/speech_commands_v0.01.tar.gz

# to dos 

* Re run for more training data (currently only using 20 total) 
Changed to 200 total - works for recognisign the location of a word but not for the word itself - change examples to accomodate this .

* Change initial training data to include 0-4 words random (non overlapping) with some trigger words and some not.  - should improve the utility of the tw detector
Done

* run for new data set
Done

* Change model to input batches of audio - i.e. add a 4th batch dimension
Optional - doesn't add much more.

# Run streamlit app
terminal:
streamlit run streamlit_app.py

# Launch MLflow tracker
terminal:
mlflow server



#  Using the Code 
### Python version
3.10.11

### Docker
# You can build the docker file using (note you will still need to downloaded the raw tensor flow dataset and then build train/test data from it)
docker build -t docker_test .
docker run -it -p 8000:8000 916ac3d8bcf1 cmd
type exit to leave the docker window


### Download Data
Download the tensorflow audio recordings http://download.tensorflow.org/data/speech_commands_v0.01.tar.gz


### Data Creation
Adjust the example in generate_training_data for the required number of training/test data sets.

# Packages
Can install via requirements.txt but it has become quite bloated so it's better just to individually install.

### Training 
Run the train_func.py - may need to change file paths + paramters etc
jupyter notebook:
%run train_func.py
or in terminal:
python -m train_func.py

### Inferencing
Load streamlit app - point app at the torch saved model - record your own audios
terminal:
streamlit run streamlit_app.py

# Useful Thesis - found post code creation:
https://ntnuopen.ntnu.no/ntnu-xmlui/bitstream/handle/11250/2564171/19711_FULLTEXT.pdf?sequence=1