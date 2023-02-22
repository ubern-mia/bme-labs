# First session

Welcome to our 3-week BioMedical Engineering (BME) Lab on medical image analysis. We will focus on "A.I. for automated medical image classification"!

See [here](/session01/README.md) for more instructions and details.

## Data

We use data from the [MedMNIST v2 data set](https://medmnist.com/), specifically the DermaMNIST subset to demonstrate how simple Deep Learning models work for a classification problem. Once we get used to loading the data appropriately, the infrastructure around training such models, and evaluating performance using suitable metrics, we will then focus on the interpretability and understanding part of the analysis.

## Tasks

1. (30 minutes) Go over some introductory Deep Learning content (to be shared separately) and a brief presentation of the analysis we plan to run. 
2. (30 minutes) Setup google colab and be able to run the training script to completion - so the infrastructure is setup and you can focus on the incremental updates/tweaks next.
3. (60 minutes) Appreciate what hyperparameters are available to tune: run through some of these and find out how it impacts the classification accuracy.
4. (30 minutes) (optional) Go beyond version 7 - and try to tweak the training process to improve test accuracy beyond what has been reported in v7 (0.770).


# Second session
TBD - focused on interpretability and understanding why models work the way they do.


## Tasks
1. TBD

# Third session
TBD - continuing interpretability and understanding of the model behavior, followed by some time reserved for report writing

## Tasks
1. TBD

# References
- Jiancheng Yang, Rui Shi, Bingbing Ni. "MedMNIST Classification Decathlon: A Lightweight AutoML Benchmark for Medical Image Analysis". IEEE 18th International Symposium on Biomedical Imaging (ISBI), 2021.
- Jiancheng Yang, Rui Shi, Donglai Wei, Zequan Liu, Lin Zhao, Bilian Ke, Hanspeter Pfister, Bingbing Ni. Yang, Jiancheng, et al. "MedMNIST v2-A large-scale lightweight benchmark for 2D and 3D biomedical image classification." Scientific Data, 2023.
- For more general tips and tricks around model training (general because it isn't Medical Imaging in particular), [Andrei Karpathy's recipe from 2019](https://karpathy.github.io/2019/04/25/recipe/) is highly recommended.
- If you're inclined to use MONAI, consider following [this](https://github.com/Project-MONAI/tutorials/blob/main/2d_classification/mednist_tutorial.ipynb) tutorial. It follows an older version of the medMNIST data set, and uses MONAI to load the data and build models more easily.
- This integrated medical image visualization tool for jupyter notebooks called [itkwidgets](https://github.com/InsightSoftwareConsortium/itkwidgets) and [this getting started guide](https://www.kitware.com/monai-and-itkwidgets-getting-started/) with MONAI could be very useful!
- For medical image visualization within tensorboard ("tensorboard3d"), [this nice plugin developed by Kitware](https://www.kitware.com/tensorboardplugin3d-visualizing-3d-deep-learning-models-in-tensorboard/) could be super useful for volumetric data.
- [This](https://medium.com/miccai-educational-initiative/project-roadmap-for-the-medical-imaging-student-working-with-deep-learning-351add6066cf) blog post for more great tips while training models.
- Consider following the [MICCAI Hackathon reproducibility checklist](https://github.com/JunMa11/MICCAI-Reproducibility-Checklist) to ensure that your pipeline is not too exotic, and future researchers can build on your work!
