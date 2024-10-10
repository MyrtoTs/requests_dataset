# **Requests Dataset for Digital Assistant Evaluation**

## **Overview**
This dataset was synthesized for evaluating the performance of DA4DTE in engine selection. The objective is to test how accurately the assistant can classify user requests into predefined categories and trigger the correct engine to handle each request.

## **Dataset Structure**
- **Total Categories**: 7
- **Samples per Category**: 15
- **Labels**: Each request is labeled with the appropriate category, indicating the engine or process that should be triggered to handle the request.

### **Categories Overview**
- **Image Retrieval by Caption**: requests for images described by a sentence (e.g., an image with very big vessels).
- **Image Retrieval by Metadata**: requests for satellite images satisfying certain criteria, based on metadata but also on geographical features of entities from knowledge graphs. (e.g., Sentinel-2 satellite images that show Mount Etna, have been taken in February 2021 and have cloud cover less than 10%)
- **Geospatial QA**: questions on geographical entities and features (e.g., “Is Dublin at most 210km from Galway County?” ) based on Knowledge Graphs.
- **Visual QA (binary)**: questions based on images. In the current implementation, the vQA engine will be restricted in true/false questions , e.g., “Is this an urban area?”.
- **Image Segmentation (or object extraction):** requests like “Extract the vessels from this image”.
- **Image Retrieval by Image**: requests for images similar to the input one.
- **Object counting** : questions on images like “How many vessels does this image show?”.


### **Sample Data Format**
The dataset is stored in JSON format, where each entry contains:
- `request`: A user-generated request or query.
- `label`: The corresponding category or engine label that the request belongs to.

Example:
```json
{
    "request": "Find three images with vegetation percentage over 80%.",
    "label": "IMAGE_RETRIEVAL_BY_METADATA"
}
```

## **Pre-existing Datasets Used for Synthesis**
The requests in this dataset were inspired by and/or derived from the following pre-existing datasets:
- **Dataset 1**: [GeoQuestions1089](https://github.com/AI-team-UoA/GeoQuestions1089) - Explanation of how this dataset contributed (e.g., request formulation, category design, etc.)
- **Dataset 2**: [RSVQAxBEN](https://rsvqa.sylvainlobry.com/) - Explanation...
- **Dataset 3**: [Vessel Captioning Dataset] : captions of the images, used to train the *Image Retreival by Caption* Engine.


### **Contribution from Pre-existing Datasets**
- Two subsets of GeoQuestions1089, one as is and the other with modifications, were used for the *Geospatial QA* and *Image Retrieval by Metadata* categories, respectively.
Examples:

- Three subsets of RSVQAxBEN were used for the *Visual QA (binary)*, *Image Segmentation*, and *Object counting* categories.
Examples:

- Some of the image captions in the vessel captioning dataset were used to formulate ‘search by caption’ requests.
Examples:

- For the search by image case, we used paraphrases of “Retrieve {X} similar images to this one”.

## **Usage**
This dataset is designed for use in the evaluation and fine-tuning of digital assistants. Some potential use cases include:
- **Intent Classification Testing**: Ensuring the digital assistant can correctly classify user intents across the provided categories.
- **Response Evaluation**: Verifying that the assistant responds with appropriate actions for each request.
- **Performance Benchmarking**: Comparing the performance of different models or versions of the assistant in handling diverse requests.

### **Evaluation Metrics**
The evaluation of model performance using this dataset can be conducted using standard classification metrics such as:
- **Accuracy**: Proportion of correctly classified requests.
- **Precision, Recall, F1-score**: Breakdown of performance per category.
  
Consider using tools like `scikit-learn` for evaluation if working in Python.

## **License**
Specify the license under which the dataset is made available. For example:
- This dataset is released under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute it under the terms of the license.

## **How to Cite This Dataset**
If you use this dataset in your work, please cite it as:
```
Author Names, "Requests Dataset for Digital Assistant Evaluation", Year. Available at: [Link]
```

---

## **Contact Information**
For any questions, suggestions, or issues regarding the dataset, please contact:
- **Author Name**
- **Email Address**
- **Website (if applicable)**

---

### **Optional Sections (if applicable)**

- **Changelog**: If there are multiple versions of the dataset, include a changelog.
- **Known Issues**: Any limitations or known issues with the dataset.
- **Future Work**: Plans for expanding or improving the dataset.

---

This template provides the key information that users need to understand and use the dataset effectively, while also crediting any sources that contributed to its synthesis. You can expand or remove sections based on your specific needs.
