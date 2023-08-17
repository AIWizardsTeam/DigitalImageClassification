# DigitalImageClassification

# SearchEngine Class

A class representing a search engine for image retrieval using feature extraction and matching.

## Constructor

### `__init__(self)`

- Initializes the SearchEngine object.
- Creates an ORB feature extractor with a maximum of 3000 keypoints.
- Sets the dataset folder path.
- Initializes the features dictionary.
- Calls the `index_dataset()` method.

## Methods

### `index_dataset(self)`

- Indexes the dataset by extracting and storing features of the images.
- Checks if the features are already serialized and loads them if available.
- If features are not available, it loops through the images in the TEST folder recursively.
- Loads each image and extracts its features using the ORB feature extractor.
- Serializes the features dictionary and saves it to disk.
- Calls the `load_features()` method to load the features into memory.

### `load_image(self, path)`

- Loads an image from the specified path.
- Converts the image to grayscale.
- Returns the grayscale image.

### `extract_features(self, image)`

- Extracts features from the given image using the ORB feature extractor.
- Returns the extracted features.

### `serialize_features(self, features)`

- Serializes the features dictionary and saves it to disk.

### `load_features(self)`

- Loads the serialized features from disk into memory.

### `search(self, query)`

- Performs a search for similar images given a query image.
- Loads the query image and extracts its features.
- Computes the similarity between the query features and the features of all indexed images.
- Sorts the similarities in descending order.
- Displays the most similar image and the query image side by side.

### `show_result(self, result, query)`

- Displays the query image and the most similar image side by side.

### `compute_similarity(self, matches)`

- Computes the similarity between two sets of feature matches.
- Calculates the average distance between the matches and converts it into a similarity score.
- Returns the similarity score.

