# Speech Emotion Recognition (SER) using the RAVDESS dataset

## Dataset Link: https://www.kaggle.com/datasets/uwrfkaggler/ravdess-emotional-speech-audio

## Kaggle Notebook: https://www.kaggle.com/code/shasan7/ser-transformers

![Abstract_mini: ](Abstract_mini.png)

The dataset was **downsampled to 16 kHz** for quicker processing and speech samples were kept into certain subfolders according to their emotional category.
Right now, the dataset is **kept private as its a part of my M. Sc. (Engg) Thesis**. After completion of the program, the dataset can be made **available upon request**.

An **starting offset of 0.6 seconds** and total **audio length of 2.5 seconds** was used, to **avoid initial and ending noises** and maintain an acceptable **audio length**. The raw audios were fed to the **Wav2Vec 2.0 pretrained audio transformer**.
The model was fine-tuned on the **RAVDESS** dataset, using a learning rate of **1e-5**, weight decay of **0.01**, batch size of **16** and the training was conducted for **20 epochs**.
**It led us to get an accuracy of 99.65%, which can be considered SOTA for this dataset**.



Following, the training summary is shown here:

    Epoch	Training Loss	Validation Loss	  Accuracy	Precision	Recall	        F1
    1	    1.977600	    1.785000	     0.447917	0.434311	0.447917	0.372670
    2	    1.639300	    1.422904	     0.729167	0.788503	0.729167	0.703925
    3	    1.314900	    1.098097	     0.847222	0.902571	0.847222	0.840370
    4	    1.045200	    0.898471	     0.888889	0.896052	0.888889	0.888523
    5	    0.840500	    0.683515	     0.944444	0.949736	0.944444	0.942531
    6	    0.602500	    0.470580	     0.982639	0.984180	0.982639	0.982644
    7	    0.431300	    0.322353	     0.989583	0.990942	0.989583	0.989733
    8	    0.303800	    0.249568	     0.982639	0.983885	0.982639	0.982719
    9	    0.223000	    0.182425	     0.993056	0.993687	0.993056	0.993127
    10	    0.174200	    0.135963	     1.000000	1.000000	1.000000	1.000000
    11	    0.143300	    0.113453	     0.996528	0.996693	0.996528	0.996547
    12	    0.119600	    0.102878	     0.996528	0.996693	0.996528	0.996547
    13	    0.105000	    0.088256	     0.996528	0.996693	0.996528	0.996547
    14	    0.092500	    0.108288	     0.986111	0.987544	0.986111	0.986252
    15	    0.084300	    0.069476	     1.000000	1.000000	1.000000	1.000000
    16	    0.078400	    0.069363	     0.996528	0.996693	0.996528	0.996547
    17	    0.073900	    0.081074	     0.993056	0.993687	0.993056	0.993127
    18	    0.070700	    0.078962	     0.993056	0.993687	0.993056	0.993127
    19	    0.068800	    0.082105	     0.989583	0.990942	0.989583	0.989733
    20	    0.067700	    0.068906	     0.996528	0.996693	0.996528	0.996547



And we obtained the result as below:

                precision    recall  f1-score   support

       Anger       1.00      1.00      1.00        31
        Calm       1.00      1.00      1.00        46
     Disgust       1.00      1.00      1.00        33
        Fear       1.00      1.00      1.00        43
       Happy       1.00      1.00      1.00        42
     Neutral       0.95      1.00      0.98        20
         Sad       1.00      1.00      1.00        35
    Surprise       1.00      0.97      0.99        38

    accuracy                           1.00       288
    macro avg      0.99      1.00      1.00       288
    weighted avg   1.00      1.00      1.00       288



The Confusion Matrix is provided as-
    
![Confusion Matrix: ](Conf_Mat.png)


The validation accuracy and loss curves also show convergence-

![Validation Accuracy: ](Acc.png)

![Validation Loss: ](Loss.png)
