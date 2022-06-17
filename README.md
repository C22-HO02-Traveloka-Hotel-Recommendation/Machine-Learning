# Hotel_Recomendation_Model_Traveloka
Bangkit 2022 Company-based Capstone <br> <br>
Team ID	: C22-HO02 <br>
(ML) M2010F1018 - Lufthi Kautsar - Universitas Indonesia <br>
(ML) M7012G1242 - Ridhwan Nashir - Telkom University <br>
(ML) M2123F1566 - Joane Vanesa Hadi - Politeknik Elektronika Negeri Surabaya <br>
(ML) M7123G1556 - Zul Fauzi Oktaviansyah <br>

## Data Engineering <br>
Our dataset is created using 2 datasets from Kaggle Goibibio India hotel, a list of hotels with more than 3000 unique hotels, and Datafiniti hotel review, a list of hotel reviews with more than 9000 hotel reviews in the US.

From our analysis, there are some strengths and weaknesses in each dataset. Goibibo dataset gives a much wider range of hotels, includes useful features such as property_type, room_facilities, and hotel_facilities,
and also more details about the hotel description. On the other side, the Datafiniti gives information about the user, a more reliable coordinate value, and detailed information for each review.

For the data processing flow, each dataset is preprocessed. Then, for Datafiniti, the data is split into 3. On Goibibo, the hotel data features go through the one-hot encoding process, and the merger of hotel data from both datasets gives us the final hotel dataset. Then, the final user dataset is created by extracting Machine Learning features from each hotel the user reviewed.

For data structure, data is split between Machine Learning and Non-Machine Learning, with the machine learning one containing the one-hotted features.

The Data Exploration is done is Jupyter Notebooks on the "Eksplorasi Data" folder, the dataset then extracted to get location data, experiment folder, and main dataset. The main dataset folder, contains the final datasets and the train test split using stratified split based on the total of user review.

## Model Deployment <br>
We deploy the model using Flask by creating a python code that will load the required dataframe and Keras h5 model. The Flask will receive a user_id as a string from the backend, then load the features of the user using the already loaded pandas dataframe. After that, the model will predict by ranking the hotel recommendations for the given user. The recommendation is returned in JSON format using jsonify.

## Machine Learning Model <br>
