# simplifying protests :fist: - a simple method of classifying protest demands using machine learning 


### Detailed description of the idea and project. #

In light of recent civil unrest, including #blacklivesmatter and #metoo movements,it has never been more important for people in positions of power to listen citizen voices.

<p> For my microsoft student accelerator project, I will be trying to develop machine learning model which can read descriptions about government protests, and construct a suitable label for the event.

<p> Along with certain RSS scraping methods, I would like to extend this project to automatically label incoming news articles in accordance to protest demands. I would also love to have more comprehesive labels to describe each event, to provide insightful analysis of what specifically demands are around the world, to see if there are any similarities and differences.
    
### Environment set up and dependencies #
    
 The following packages will be required for performing my analysis. Most of which would already be available if anaconda is installed on the local machine. 
    
    *pandas
    *numpy 
    *tensorflow
    *sklearn 
    *keras 
    *matplotlib
   
### Instructions on how I trained and tested my training model #

The database I will be using is a dataset collected by the Mass mobilisation data project. Each data row many descriptions including a 200 word description of the event that took place and a label describing protestor demands.

Data processing 

To process the data, I first changed all capitalised words into non-capitalised words. I also split my data into test, validation and training sets. After that, I tokenised and padded each protest description using Kera's tokenizer and padding functions and also vectorized labels.

Model 

 I then used Keras to build the training model layer by layer, with a input layer consisting of all the words in each protest description, turned into 100-length vectors a hidden layer which processes input using a Long-short-term-memory neural network, and an output layer consisting of 8 neurons , each corresponding to the possible protest categories. I have used regularisers and dropout methods to reduce model overfitting. The model is then compiled using categorical cross-entropy and the adam optimiser was chosen as it was seen to have the best metrics. The process was run with 2 epochs because previous runs of the program showed the model overfitted quickly with larger epoch runs.

Evaluation

 I then assessed how well model worked by observing learning curves which plot the loss and accuracy of the model against the number of times the data was trained. I also tested the accuracy based on the entire test dataset. The model doesn't seem to be very accurate and tended to overfit. 
This is likely because some of the protest data had very short descriptions and descriptions weren't very detailed. Perhaps a way to improve the model could be use the articles which the events were based, however some were too old to have the correct descriptions.

