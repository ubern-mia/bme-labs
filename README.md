# First session

Welcome to our small medical image analysis project "automated detection of neurodegenerative diseases on MRI"!

As we age, and with some neurodegenerative diseases, our brain changes considerably. With Magnetic Resonance Imaging (MRI), we can monitor the disease progression and possibly improve personalized treatment options.
Studies have shown distinct patterns of disease progression and aging. These were only made possible due to advances in Machine Learning and Deep Learning since manually segmenting brain structures is prohibitively time-consuming. With automated methods to segment important brain structures on MRI, we can assess if a given patient is within the expected distribution of the age group or affected by a neurodegenerative disease. In this small lab project, you will get acquainted with the whole workflow commonly applied in medical image analysis. You will start with understanding the clinical task, basic processing steps such as registration and continue with manual and automated segmentation using a state-of-the-art deep learning model, and finally perform a statistical evaluation of the results. With 3D Slicer, you will work with a widely used medical image analysis tool and get used to interacting with medical imaging data. Furthermore, you will work with Python scripts for modeling and evaluation.

During this first afternoon, you will get a brief introduction into what we are trying to achieve and the data we will use for the project. Additionally, you will test your skills to identify certain structures on magnetic resonance imaging (MRI) data.



## Data

In a first step, we will analyze the data of healthy subjects. You find these in the folder "healthy_controls_anonymized" on the external drive. In each folder, you see a file "brain.mgz", which is the MRI, and some other data. The other two *.mgz files are the segmentations of different brain regions obtained with FreeSurfer.

## Tasks

1. You find data of healthy subjects on the external drive in the folder. Open a couple of these in 3D Slicer and familiarize yourself with the controls and visualizations.
2. We aim to find age-related and disease-related patterns. The filenames give you a hint of the age of the subjects (e.g., MS_HC020_m_25_MPRfischl_corr_YB is a 25 year old man). Open images with a large age gap in between. For example, a seven year old and a 78 year old. Do you spot any differences?
3. Next, we will try what neuroradiologist do to generate training data for our machine/deep learning models: Manually segment. We do that for the *corpus callosum*. Do a quick google search to get an idea of how this part of the brain looks on MRI.
4. As soon as you have segmented the corpus callosum, you can compare it to the automated segmentation by FreeSurfer. For that, load the file "aparc+aseg.mgz" into 3D Slicer. The segments with the prefix "CC" define different parts of this brain structure.
5. The dataset has already been processed with FreeSurfer by us. The aggregated volumes of the different brain regions for each subject is listed in the csv file in the data folder. We will use this to get a first overview of the data with plotting:
   - As a starting point, you can use the Google Colab version of https://github.com/ubern-mia/bme-labs/blob/main/dataexploration.ipynb
   - As already prepared in the Python notebook, plot the volumes of the different brain regions across the age.
   - Now stratify the data for men and women to see differences
   - Check the age distribution for males and females (for example with a boxplot)
6. In the end, we would like to identify neurodegenerative diseases from normal aging. Do a brief literature search, what regions might be affected for Alzheimer's disease and epilepsy.


# Second session
After you did an initial exploration of healthy subject's data, we will now use additional data from epilepsy and autism spectrum disorder (ASD) patients to investigate further. We processed the whole dataset with FastSurfer to extract the size of given brain regions.


## Tasks
1. FastSurfer has a great speed advantage over the conventional FreeSurfer pipeline. Still, processing the whole dataset would take too much time and too little insight for you within one afternoon. To get an impression of the tool, visit https://colab.research.google.com/github/Deep-MI/FastSurfer/blob/master/Tutorial/Complete_FastSurfer_Tutorial.ipynb and perform an automated segmentation (use case 1)  for three subjects of your choice, possibly a healthy one, and one with epilepsy and ASD.
2. The data you will work with today is located on the external drive: fsfaststats.csv It contains volume information for the whole dataset. The added "Disease" column gives you information on the status. Healthy subjects are encoded as "0", ASD patients with "1", and epilepsy patients with "2". The ASD data (and accompanying data of healthy subjects) stem from the ABIDE I dataset (http://fcon_1000.projects.nitrc.org/indi/abide/abide_I.html). Visit this website briefly to check out the general data description.
3. Next, we we will do some basic data exploration and try to classify the disease automatically based on the extraced volumes. For this, we provide you with a Colab notebook to get you started: https://github.com/ubern-mia/bme-labs/blob/main/Session2.ipynb Please go through it and see if you understand what the general process is. 
4. Next, we will try to get the best possible performance for disease classification. The scikit-learn package offers many classifiers apart from the Random Forest classifier you saw in the Colab notebook. Try to the Random Forest with other classifiers and note the performance on the training set (cross-validation), and test set. Please compile a table. When you apply a new classifier, briefly go over the basic principle behind it. Classifiers you could test: KNeighborsClassifier, SVC (Support Vector Classifier), AdaBoost, ...

# Third session
Last time you gained some hands-on experience on training and testing classifiers. Today, you will wrap up these experiments and look into which features are actually imporant for this particular classification task. 

## Tasks
1. First, please wrap-up the testing of different classifiers as in the last task of last week. If a 10-fold cross-validation takes too long for some classifiers, you may reduce the cross-validation splits to e.g. four in last week's Python notebook. But please re-run everything with the same number of splits to make sure you have a consistent performance comparison. Please try at least two classifiers apart from the Random Forest.
2. For some classifiers, we can gain insight regarding which input features play an important role. The random forest classifier offers such insight very easily through the feature_importance_ attribute. Experiment briefly with the parameters n_estimators and max_depth to get the best performance for this classifier. Do not spend a lot of time with it. Based on this, you can look into the features importances with the help of today's Colab notebook https://github.com/ubern-mia/bme-labs/blob/main/Session3.ipynb. Does the most important features match what you would expect from the literature?
3. That's it for new experiments for today, please take the remaining time to work on your report, generate figures and look up relevant references.

(if you're interested, please also consider using the 'exploreClassificationModels.mlx' file - written in MATLAB - to see how various models work)

# References
- [Fischl, B., 2012. FreeSurfer. Neuroimage, 62(2), pp.774-781.](https://www.sciencedirect.com/science/article/pii/S1053811912000389?casa_token=zcGnrEXdvoIAAAAA:ji7Sej8gSL32yFb6WJzsbVabxbVReS6lAsToc3-rXMhFWPCc8APADIjZ_as7vGilLCamRWNTb8rn)
- [Henschel, L., Conjeti, S., Estrada, S., Diers, K., Fischl, B. and Reuter, M., 2020. Fastsurfer-a fast and accurate deep learning based neuroimaging pipeline. NeuroImage, 219, p.117012.](https://www.sciencedirect.com/science/article/pii/S1053811920304985)
- [Breiman, L., 2001. Random forests. Machine learning, 45(1), pp.5-32.](https://link.springer.com/content/pdf/10.1023/A:1010933404324.pdf)
- [Di Martino, A., Yan, C.G., Li, Q., Denio, E., Castellanos, F.X., Alaerts, K., Anderson, J.S., Assaf, M., Bookheimer, S.Y., Dapretto, M. and Deen, B., 2014. The autism brain imaging data exchange: towards a large-scale evaluation of the intrinsic brain architecture in autism. Molecular psychiatry, 19(6), pp.659-667.](https://www.nature.com/articles/mp201378)
- [Fedorov, A., Beichel, R., Kalpathy-Cramer, J., Finet, J., Fillion-Robin, J.C., Pujol, S., Bauer, C., Jennings, D., Fennessy, F., Sonka, M. and Buatti, J., 2012. 3D Slicer as an image computing platform for the Quantitative Imaging Network. Magnetic resonance imaging, 30(9), pp.1323-1341.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3466397/pdf/nihms383480.pdf)
