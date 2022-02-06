# **structural_health_monitoring**

## **Abstract**
The structural health monitoring (SHM) of civil structures through the use of pervasive sensor data is a tremendous emerging topic. In this framework, SHM aims at detecting and identifying any deviation from the damage-free baseline, allowing for timely maintenance activities. Machine learning techniques have been recently employed to empower vibration-based SHM techniques. While damage detection can be addressed exploiting unsupervised learning strategies, higher levels of characterization require to resort to more advanced supervised algorithms. However, dealing with civil structures, labeled data pertaining to a specific damage condition are often unavailable. The use of physics-based numerical models, possibly speeded-up by model order reduction strategies, enable to mimic the structural response in presence of damage. In this thesis work, the tasks of damage localization and damage quantification is systematically tackled by means of deep neural networks trained on numerically generated datasets. A detailed analysis of their performance is proposed through a study of their robustness against different type signal distortion.

&nbsp;

## **Scenario** 
All methods proposed in this repo refer to the following scenario shown on the figure below: 2D frame of a two-floor building. 16 sensors are installed at different locations to monitor both the X and Y axis. The red circles mark the exact points of the sensor positioning, in each point are placed both a *displacement sensor* and an *accelerometer*.

![plot](./img/Sensors_position.png)

&nbsp;

## **Project structure**
The project is composed by the following files and folders:
* **data** is the folder where you have to put the data in npy format. you can download the dataset at the following link (TODO put the link to the dataset), unzip the folder and move the content in this folder
* **models** is the folder where you can save the models you train.
* **autoencoderds.ipynb** is a colab notebook containing the definition of three different types of autoencoder architectures: *Feedforward AE*, *Convolutional AE* and *Long Short Time Memory AE*. Each of these architectures is trained twice: the first time on uncorrupted data to have a benchmark, the second time on data where a low power and lossy network is simulated to evaluate the performance degradation in this other scenario.
* **convolutional_models.ipynb** is a colab notebook containing the definition of the convolutional architectures of the different classifiers and regressors and the training of them on both clean and corrupted data
* **testing_models.ipynb** is a colab notebook where we evaluate how models built in *convolutional_models.ipynb* perform when distortion levels vary
* **utils.ipynb** is a colab notebook that contains some utility methods. It is run at the beginning of every other colab notebook.

