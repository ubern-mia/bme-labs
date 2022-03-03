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
   - As a starting point, you can use the Google Colab version of https://github.com/ysuter/bme-labs/blob/main/dataexploration.ipynb
   - As already prepared in the Python notebook, plot the volumes of the different brain regions across the age.
   - Now stratify the data for men and women to see differences
   - Check the age distribution for males and females (for example with a boxplot)
6. In the end, we would like to identify neurodegenerative diseases from normal aging. Do a brief literature search, what regions might be affected for Alzheimer's disease and epilepsy.
