# NLP Cook Dishes Project

## Project Overview
This project is an in-depth exploration of various NLP models with the purpose of generating text based on a dataset of recipes. The study compares different language modeling techniques to understand their effectiveness in the context of recipe generation. It serves as an educational endeavor to understand the nuances of NLP model architectures and their applications.

## Setup

The run command will start the Jupyter notebook server on port 8888. By specifying ports: 8888, SkyPilot will expose port 8888 on the cluster, making the jupyter server publicly accessible. To launch and access the server, run:

```shell
sky launch -c jupyter jupyter.yaml
```

and look in for the logs for some output like:

```
Jupyter Server 2.7.0 is running at:
    http://127.0.0.1:8888/lab?token=<token>
```

To get the public IP address of the head node of the cluster, run `sky status --ip jupyter`.
In the jupyter server URL, replace `127.0.0.1` with the public IP from `sky status --ip jupyter` and open the URL in your browser.

After a task’s execution, use rsync or scp to download files (e.g., checkpoints):

```shell
rsync -Pavz mycluster:/remote/source /local/dest  # copy from remote VM
```

## Notebooks

### Ngram Language Models
- **Objective**: Study and implementation of N-gram language models for text prediction.
- **Techniques Used**:
  - Estimation of text probability using joint probability of tokens.
  - Implementation of additive smoothing and Kneser-Ney smoothing.
  - Handling of unknown words through smoothing techniques.
- **Model Architecture**:
  - N-gram models with a focus on the effects of additive and Kneser-Ney smoothing.
  - Optimization of the N-gram model parameters to improve prediction accuracy.
  - Analysis of model performance using perplexity as a metric.

### RNN-LSTM and CNN Language Models 
- **Objective**: Development of a character-level RNN for sequence generation in the context of recipes.
- **Techniques Used**:
  - Creation of special tokens (BOS and EOS) for sequence processing.
  - Building and utilizing a char-level vocabulary for the dataset.
  - Encoding strings to integer vectors and handling variable sequence lengths.
- **Model Architecture**:
  - Implementation of a Recurrent Neural Network for language modeling.
  - Exploration of a fixed-window (convolutional) neural network architecture.
  - Utilization of RNNs for the classification of sequences and prediction of subsequent characters.


## Resources:

Data source: https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions?select=PP_recipes.csv