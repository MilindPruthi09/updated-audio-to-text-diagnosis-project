# Audio-to-text-diagnosis-project

In order to maintain the project’s system architecture as simple as possible and make it easier for others to understand, it has been carefully examined and planned. The system is made up of five main parts. These modules are: 

1. Audio Capture and converting it into text by using Transfer Learning 
2. Filter words from the converted text using Natural Language Processing 
3. Training the Machine Learning Model on the Columbia Dataset 
4. Testing and calculating the probability of disease being correctly inferred 
5. Calling the above functions to be integrated together and showcasing the result with respective API call detailing the disease description.

<b> (I) Converting audio to text </b>

Our application converts audio to text using a voice recognizer. The popularity of digital assistants like Siri, Alexa, and Google Assistant has recently helped this technology, despite the fact that it has been available for a long. Our program incorporates cutting-edge voice recognition technology that enables accurate transcription of spoken words into text. 

The speech recognizer analyzes the audio input using machine learning techniques to find and distinguish certain words. To do this, a database of recognized speech sounds is matched against each manageable segment of the audio stream. Based on this comparison, the recognizer can determine which word is more likely to have been spoken. 

Our program only supports English at this time. But, by integrating NVIDIA NeMo into our system, we intend to increase the number of languages that our program can distinguish between. 

NVIDIA NeMo is a powerful open-source toolbox for developing and enhancing conversational AI models. The accuracy and dependability of voice recognition systems are improved by the use of contemporary machine learning techniques. 

NeMo allows us to handle more languages and dialects, including some that are normally difficult to understand, like Mandarin and Arabic. 

Several steps will be required to integrate NVIDIA NeMo into our software. We must first train our voice recognition models using the NeMo toolkit. To train our algorithms to recognize the unique features of that language, extensive audio data gathering in the target language will be required. 

For use in the real world, our models will then need to be optimized. This will necessitate modifying our algorithms to account for accents, background noise, and speech unpredictability. Additionally, we will need to develop trustworthy algorithms to address common speech recognition issues including homophones, slurred speech, and mispronunciations. 

Our models will be integrated into our software platform once they have been trained and enhanced, enabling users to transcribe audio files in a larger range of languages. Compared to our current system, which is restricted to a relatively small number of languages, this will be a big advance. 

Our program has successfully completed its initial testing, demonstrating that it is functional for English speakers, and is now prepared for further testing. Nonetheless, the issue of other languages is still there. 

<b> (II) Extracting Symptoms using NLP </b>

The second module is responsible for extracting the symptoms from the converted text. Since it is sometimes important for doctors and other healthcare professionals to distinguish symptoms from patients’ descriptions of their ailments, this capability is very useful in the medical area. 

We accomplish this using Spacy, a powerful open-source natural language processing tool that enables us to extract important information from text input. The text analysis and processing tools provided by Spacy include part-of-speech tagging, dependency parsing, and named entity identification. 

Training a special model that can identify items in the text that are connected to symptoms is the first stage in utilizing Spacy to extract symptoms. In order to accomplish this, a sizable collection of text data including symptoms must be gathered, and our model must then be trained to recognize and extract symptoms from fresh text using this dataset. 

Our program can quickly identify symptoms from text input after training. When a user inputs a textual description of their symptoms, our app uses Spacy to discover and extract any entities associated to the symptoms. These entities may contain words like “fever,” “nausea,” “headache,” “fatigue,” and many others. 

However, Spacy could occasionally misinterpret symptoms from the text. This may be brought on by things like misspellings, unusual vocabulary, or other problems that make natural language processing tools less accurate. In these circumstances, it could be necessary to extract textual components relevant to symptoms using alternate techniques, like part-of-speech (POS) tagging. 

In POS tagging, specific word types, such as nouns, verbs, and adjectives, are identified by analyzing the sentence’s grammatical structure. By identifying and extracting specific types of words that are frequently associated with symptoms, such as adjectives like “painful,” “itchy,” or “swollen,” we may be able to extract symptom-related entities from text data that Spacy may not be able to recognize correctly. 

Overall, the ability of our program to extract symptoms from text data using Spacy and POS tagging has considerably increased the effectiveness and precision of symptom extraction in the healthcare industry. 

<b> (III) Machine Learning Model </b>

To create software that is effective in detecting illnesses, it is essential to train a machine learning model with relevant data. The Columbia illness symptom dataset contains a list of signs that can be used to identify this ailment. With the aid of this dataset, we can create a machine learning model that can accurately diagnose a patient’s illness based on their symptoms. 

One of the best methods for training a machine learning model on this dataset is to use a random forest classifier. Both classification and regression applications use the random forest machine learning technique. 

The first step in training a random forest classifier on the Columbia disease symptom dataset [Figure 5] is preprocessing the data. The raw data must first be cleaned and transformed into a format that the machine learning model can comprehend in order to achieve this. Categorical variables may need to be categorized, input attributes scaled, and missing data may need to be eliminated. 

The data can be split into a training set and a testing set after preprocessing. The training set is used to develop the machine learning model, whereas the testing set is used to evaluate the model’s performance. In this case, the training set is the entire dataset. 

After that, the training data must be used to develop and train the random forest classifier model. The random forest algorithm constructs a number of decision trees, each of which has been trained using a subset of the input attributes. The ultimate prediction is then obtained by combining the forecasts of each individual decision tree. 

After the model has been trained, it is critical to evaluate how well it performs on the testing set. This can be done by using a number of criteria, such as accuracy, precision, recall, and F1 score. The performance may be further enhanced by modifying the model’s hyperparameters, such as the number of decision trees and the maximum depth of each tree. 

The random forest classifier model, which may be incorporated into the software for disease diagnosis, was trained and evaluated using the Columbia illness symptom dataset. As a result, the algorithm will be able to identify the ailment from a patient’s symptoms more rapidly and accurately. 

The model we created using the dataset had a training accuracy of 0.98, while the average score from three cross-validations was about 0.95. The resultant test accuracy was 0.93. 

<b> (IV) Converting Extracted Symptoms to binary and sending it to Machine learning model </b>

In the first step, symptoms are extracted from the patient’s word using an NLP algorithm. To determine whether the extracted symptoms are present, they must be contrasted with the dataset of symptoms. The list of symptoms should include each symptom’s associated codes or labels. 

The program may use these codes or labels to create an array of 1s and 0s, where 1 indicates the presence of a symptom and 0 indicates its absence. The method, known as one-hot encoding, is frequently used in machine learning. 

Depending on the existence or lack of symptoms, the system may then train a machine learning model using this array to forecast the disease. Numerous methods, including deep learning, logistic regression, and decision trees, can be used to train the machine learning model. We employed a method called random forest classifier in this instance, which was motivated by decision trees. 

The dataset’s quality is an important factor to take into account when applying machine learning to medical diagnosis. The dataset should be updated by medical professionals, and it should be sizable enough to include a range of ailments and symptoms in order to guarantee its accuracy. To reflect the most recent medical knowledge and research, the software should also be regularly updated. 

<b> (V) Showcasing output results </b>

The results may be presented on a website [Figure 6] for both patients and medical professionals to readily access and analyze once the machine learning model has properly predicted the ailment based on the presence or absence of symptoms. 

The first step in putting the results online is creating an aesthetically pleasing and user-friendly interface. The user interface (UI) should allow them to enter their symptoms and view the impending illness. The website should also contain more information about the ailment, such as its symptoms and causes. 

To present the results on the website, the application may use a variety of visualization techniques. A common way to show whether symptoms are present or absent is with a heatmap. The heatmap can show the presence or absence of symptoms as well as how closely they connect to the illness being predicted. 

Another tactic is to use a search API, such as those provided by Google, Bing, and OpenAI, among others, to draw attention to the ailment and its prevalence. 

In addition to letting users read the results, the website might also give them personalized counsel based on the ailment they anticipate. For instance, if diabetes is the anticipated illness, the website can provide nutrition and exercise recommendations. 

Verifying that the website is secure and that user information is secured is essential. A clear privacy statement should be present on the website, and data protection rules should be followed. 
