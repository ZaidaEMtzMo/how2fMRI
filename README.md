# *Introduction to my project*

## **Index**

1. [Who am I?](#who-am-i)

2. [Goals](#goals)

3. [Project draft](#project-draft)

4. [To-do list](#to-do-list)

5. [The dream](#the-dream)

6. More stuff...

## **Who am I?**

Hello everyone! :smiley:

My name is Zaida Escila Martinez Moreno :woman:. I was born in Mexico :mexico: and came to Canada :canada: on 2017 to fulfill my dream of studying Neuroscience abroad :woman_scientist:.

With a background in Biology :panda_face:, I was not familiar with anything, from programming :computer: to psychology, anatomy or behaviour, much less with **neuroimaging techniques** such as **_fMRI, MEG and EEG_**; or with **analysis software** such as Brainstorm for MEG and FSL, SPM, AFNI or Nistats for fMRI. Since then, I have been in the adventure of understanding everything.

I started to work with fMRI when I decided to join a project that consisted in the comparison of the same stimulus in both, fMRI and MEG. Therefore, I needed to create the stimulus on **MatLab** (the preferred language in my lab). Then I developed a code to present the same stimulus first to MEG and afterwards, to fMRI.

Finally, I got the raw data: DICOM and MNC files. However, I didn't know how to begin and what to do, and after looking on the Internet, I got the names of some tools and some steps but not all of them. What I want to do with this project is **to build a webpage that contains as many of these options as it is possible, with comparisons and options on how to analyze the data**. But I also want to create a pipeline that allows you to follow the analysis and let's you understand each of its steps.

## **Goals**

- [x] Create the Github repository. :heavy_check_mark:
- [x] Create the introductory `.md` file. :heavy_check_mark:
- [x] Create the draft of the project :heavy_check_mark:
- [ ] Create the list of to-dos
- [ ] Create the draft of the webpage.
- [ ] Choose the example dataset.
- [ ] :soon:

## **Project draft**

The webpage will have an **Introduction** section where I will share links of websites that include a brief but deep explanation of each technique, their uses in neuroscience and the normal steps that every analysis require.
Then, I will have a tab per technique/software and then, per step of the analysis:

- Introduction

- fMRI
  - Data description and acquisition
  - BIDS formatting
  - FSL
    - [Jupyter Notebook for **PREPROCESSING**](./Preprocessing/preprocessing.ipynb)
        1. [Conversion to NIFTI](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#conversion-to-nifti)
        2. [Onset files](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#onset-files)
        3. [Slice timing](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#)
        4. [Realignment](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#)
        5. [Coregistration](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#)
        6. [Normalisation](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#)
        7. [Smoothing](https://github.com/ZaidaEMtzMo/how2fMRI/blob/master/Preprocessing_pipeline.md#)
    - Analysis
        1. Task-based fMRI
        2. Resting state fMRI
  - SPM
    - Preprocessing
  - AFNI
    - Preprocessing

- MEG
  - Data acquisition
  - BIDS formatting
  - Format styles
  - Available software

- EEG
  - Data acquisition

## **To-Do List**

- [ ] ...
- [ ] Preprocessing pipeline visualization in a Jupyter Notebook.

## **The dream**

Create an online hub with all the resources available for the analysis of fMRI. Per software, have a Jupyter notebook that allows the person to run their own analysis by themselves and to see their results at that same place. As some software require other software to be downloaded (SPM with MatLab), I will find a way to include them in a container where they could run the analysis without any trouble.
