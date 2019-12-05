# Driver-Safety-Interface

### Need

India is the no.1 contributor to global road crash mortality and morbidity figures. Every hour, around 16 lives are lost to road crashes in India. In the last decade alone, India lost 1.3 million people to road crashes and another 5.3 million were disabled for life, and yet, drivers fail to give up risky habits. We can work on completing the GUI component and integrating it with user inputs. We can develop an end product using IoT and this Model in which: 

• While driving, the driver's behaviour may be continuously monitored through 2-D pictures clicked by a camera placed on the dashboard (pi-camera), and the driver is immediately notified if he/she is found to be distracted (through alert tones using pi). 

• Our in-vehicle device can help anyone with a personal and/or financial interests in improving driving safety of friend, family, employees etc. If we prepare database of co-ordinates and time of distraction it may help at Individuals Level : The in-car device combined with web-based analytics can give you accurate feedback on your loved one’s driving safety. Business Level : Many businesses own one or more company vehicles. These vehicles are driven by employees but are company liability. This device and web analytics can give you the peace of mind that your assets are in good hands and being driven responsibly. If you discover distracted driving, you can review the photo evidence and intervene as needed. 

### Technology

• Python 

• Image processing 

• Deep learning 

### Dependencies

• Python 3.6.1 

• Tensorflow 1.3.0 

• Keras 2.1.2 

• matplotlib 2.0.2 

• numpy 1.12.1 

• PyQT5 and QtDesigner (optional : to run Interface designed which is half completed and takes an input image and displays it)

### Dataset

Datset is collected from StateFarm's Distracted Driver Detection competition on Kaggle. It has 10 classes for telling the status of driver which include he usage of a mobile phone, eating and drinking, conversation with co-passengers, self-grooming, reading or watching videos and adjusting the radio or music player. 

### Implementational Detail

Our model is trained on images obtained from a Kaggle Competition sponsored by State Farm Insurance which has 10 distinct classes. Each input image is resized to 224 pixels by 224 pixels , Image processing techniques such as histogram equalization across all 3 channels and randomly rotating images have been done which also serves in data augmentation . We have used transfer learning due to limited dataset and resources, where we have utilized pre-trained VGG-16 net CNN model (over VGG-19,GoogLeNet ,ResNet-50,it produced the best results) and then further trained to learn the idiosyncrasies of our data. We performed Global Average Pooling just before the final output layer at the end .This helps the convolutional neural network to have localization ability despite being trained on images. The accuracy of model for a subset of test data was found to be between 50-60% as model find it difficult to differentiate between the 
safe driving ,talking to passengers ,and hair and make-up class. The model is trained on Google Colab which uses Tesla K80 GPU.

### Running Model

There are three steps to run the model: 

• First download the training data from kaggle and split it into training, test and validation set in 60,20,20 proportion using splitting.ipynb (or splitting.py file generated from colab) . 

• In order to train the model on your dataset use training.ipynb and specify the file paths at respective positions. 

• Use prediction.ipynb to know the 5 most accurate class , the trained model can be found in model folder. Use predictioninkaggleforcsv.ipynb to write results on csv file in a form which is acceptable at Kaggle Competition.


Run the GUI by command : python GUI_ADDD.py and click browse button to output an image . The integration part of UI with model is yet to be completed.





