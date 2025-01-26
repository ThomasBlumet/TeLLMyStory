# TeLLMyStory : LLM for stories generation aiming the reinforcement of the controllability aspect
## BLUMET Thomas HALVICK Thomas LETRUNG Ethan 5A INFO Polytech Lyon - M2IA

# Overview
This project contains :
- a Jupyter Notebook in order to execute locally the code (train and metrics) and display the app as cell output in the notebook
> This notebook require the use of a pc with a CUDA GPU. For simplicity of hardware, he was executed on Azure AI with a Tesla T4 GPU (payment require as 0.66USD/h). Trying on Google Collab with the free GPU cause some troubles because of the important packages and model installation.
- a app.py file containing only the code to run the app
> This file is used on a Docker App Space (named **story-generation-docker**) hosted on our [Hugging Face organization](https://huggingface.co/TeLLMyStory). If you want to run this file directly (without using a docker container) on your own computer, please check if you've a CUDA GPU and execute this command in the terminal of your current folder where you clone the project :


```pip install --no-cache-dir --upgrade -r requirements.txt```

before running the app.py :
``` python app.py ```

Else you can use a Docker container on your own pc under a WSL terminal (check if you've Docker installed else intall it and check the correct installation with ```docker --version```) by following these CLI (after cloning the [Hugging Face Docker space repository](https://huggingface.co/spaces/TeLLMyStory/story-generation-docker/tree/main)) :

- Build the docker image with the name **story-generation-app** : 

    ```docker build -t story-generation-app . ```

- Run the docker launched :

    ```docker run --gpus all -it --rm -p 7860:7860 story-generation-app ```

# The purpose
The goal was to create an app using a LLM model for storytelling, with the will to improve the controllability aspect, i.e. ensure that generated output are closed to the output that user can expected with his prompt.

# How we do that
The following tools and frameworks are :
- a Hugging Face organization hosting a Gradio app space, which allow to test the app on the web.
- use of the following pretrained model :  [TheBloke/zephyr-7B-beta-GPTQ](https://huggingface.co/TheBloke/zephyr-7B-beta-GPTQ) imported from Hugging Face. It's a GPTQ model based on the Mistral-7B-v0.1 model.

# Demonstration video
[![Youtube video presenting the app](https://img.youtube.com/vi/T2vVyhk1OBo/0.jpg)](https://www.youtube.com/embed/T2vVyhk1OBo?si=MYaekO6yJn1hAsor)
