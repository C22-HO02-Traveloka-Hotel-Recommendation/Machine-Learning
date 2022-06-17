# Hotel Recomendation Model Traveloka - Machine Learing Path
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

1. Content based <br>
Content-based filtering system: Content-Based recommender system tries to guess the features or behavior of a user given the item’s features, he/she reacts positively to. Once, we know the likings of the user we can embed him/her in an embedding space using the feature vector generated and recommend him/her according to his/her choice. During recommendation, the similarity metrics are calculated from the item’s feature vectors and the user’s preferred feature vectors from his/her previous records. Then, the top few are recommended. It does not require other users' data during recommendations to one user.

2. Collaborative <br>
Collaborative does not need the features of the items to be given. Every user and item is described by a feature vector or embedding. It creates embedding for both users and items on its own. It embeds both users and items in the same embedding space. It considers other users’ reactions while recommending a particular user. It notes which items a particular user likes and also the items that the users with behavior and likings like him/her likes, to recommend items to that user. It collects user feedbacks on different items and uses them for recommendations.

3. DeepFM <br>
DeepFM is an end-to-end model that seamlessly integrates Factorization Machine (the wide component) and Multi-Layer Perceptron (the deep component). Compared to the Wide and Deep Model from Google, DeepFM does not require tedious feature engineering. DeepFM consists of an FM component and a deep component which are integrated in a parallel structure. The FM component is the same as the 2-way factorization machines which is used to model the low-order feature interactions. The deep component is an MLP that is used to capture high-order feature interactions and nonlinearities. These two components share the same inputs/embeddings and their outputs are summed up as the final prediction. It is worth pointing out that the spirit of DeepFM resembles that of the Wide & Deep architecture which can capture both memorization and generalization


