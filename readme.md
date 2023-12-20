- (18-Dec-23) pulled everything together into this set of notebooks
- config conda
  - setup git repo in JPD-Research organization  
  - ensure env is setup to store EVERYTHING locally 
    - base xfrmr_tf "transformer with tensorflow" environment 
      - python 3.11 (most recent current for tf)
      - install jupyter, tensorflow 
- config pycharm
  - pointed to the env setup above 
  - setup this file
  - baseline notebook for first project - RNN-text-generation
- test drive the notebook env - hello world
  - first checkin into the repo <**> (<- this is a checkin marker)
- reconfigure to start the RNN work
  - had the recurring issue where the notebook doesn't use the interpreter from the configured python environment
  - "conda install nb_conda_kernels" as per [this link](https://stackoverflow.com/questions/39604271/conda-environments-not-showing-up-in-jupyter-notebook)
  - reconfigured the python interpreter properly in PyCharm as well - required pip install -U charset to remove a chardet module error
  - actually pulled the conda and python environments off of a spinning drive, onto M2 - much faster
- Actual RNN work
  - load and validate the data
  - add utilities to vectorize and sequence the data
  - turn data sequences into training batches for the model
  - (19-Dec-23)
  - <**> checkin - data loaded - prior to model construction 
  - <**> checkin - built the model and started to train
  - after training, write code to use the trained model to generate text
  - <**> checkin 
    - after training, write code to use the trained model to generate text
    - also export the full generator, reload it from disk and show it still works
  - <**> checkin
    - initial work nominally complete
    - added source data to the project folder
    - split the load/save cell to allow a user to load the model directly and run it without training
    - added a "still to do" section at the end of the notebook to point to future learning to be done shortly
- seq2seq work
  - Environment setup
    - requires tensorflow-text, which only supports Python 3.10, so downgraded the env to that
    - also, last version that runs on windows is tf-text 2.10, so...
    - rebuilt conda env with python 3.10, jupyter, tf-text 2.10.0, tf 2.10.1 
  - <**> data prep complete, beginning work on the encoder
  - <**> wrote the decoder and overall model, training and some simple tests
  - (20-Dec-23)
  - <**> finished the seq2seq model, updated the translate() method to use a tensorflow loop - significantly increased performance
      - added next steps to the bottom of the notebook
      - still do to - complete documentation of this notebook
      - small text edit to rnn notebook, placeholder for translator notebook