#Intro
Code to reproduce experiments from the following paper:

Michal Lukasik, Trevor Cohn and Kalina Bontcheva. Classifying Tweet Level Judgements of Rumours in Social Media. 
In Proceedings of Empirical Methods of Natural Language Processing, EMNLP 2015. 

http://www.emnlp2015.org/proceedings/EMNLP/pdf/EMNLP311.pdf

#Dataset
The dataset that the experiments were run on are Twitter rumours from the England riots 2011 
(Procter et al. 2013, Reading the riots: What were the police doing on twitter?).
Here we provide a processed data file used for experiments: 
*data/londonriots_BOW_BROWN_ANONYMIZED_EMNLP2015.csv* in an anonymized form 
(words and Brown cluster ids are represented in the header by meaningless integers). 

If you would like to access the England riots dataset please contact Procter et al.

#Dependencies
You need to install a number of Python libraries, e.g. by typing the following: 
* pip install nltk==3.0.1
* pip install numpy==1.9.1
* pip install scipy==0.15.1
* pip install cloud==2.8.5
* pip install scikit-learn==0.15.2
* pip install git+git://github.com/SheffieldML/GPy.git@98f632e92ec5fafaca2683ba10cf8fc1fa2296cc
* pip install matplotlib==1.4.2


#Running
To reproduce the experiments, run script: RUN.sh. 
This will run the experiments, generate the resulting text files in the "results" folder 
and gather the mean accuracy values for different settings.
This may take very long time and the results might be slightly different from the reported in the paper due to different seed for the random number generator 
(in main.util.seeds_emnlp2015.py you can find seeds we used for our EMNLP 2015 experiments for the ICM methods).

In script RUN_PARALLEL.sh is the parallelized version of the experiments, appropriate for the Iceberg server from the University of Sheffield. 
If you have access to it (or if you modify the script so that it runs in your parallel environment), after running the script you will need to run "python gather_results.py results" to analyze the results.

#Closing remarks
If you find this code useful, please let us know (m dot lukasik at sheffield dot ac dot uk) and cite our paper.

This work was partially supported by the European Union under Grant Agreement No. 611233 PHEME (http://www.pheme.eu).
