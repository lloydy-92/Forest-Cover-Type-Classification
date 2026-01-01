# Forest Tree Cover Type Classification
### Objective: Build a deep learning model to predict the forest cover type from different cartographic variables.
**Hyperparameter Distributions** = {
    'model__n_hidden': [1, 2, 3, 4],
    'model__n_units': [32, 64, 128, 256],
    'model__dropout_rate': np.linspace(0.2, 0.6, 5),
    'model__learning_rate': [1e-2, 1e-3, 1e-4],
    'batch_size': [256, 512, 1024]
}

**Best hyperparameters**: {'model__n_units': 256, 'model__n_hidden': 2, 'model__learning_rate': 0.0001, 'model__dropout_rate': np.float64(0.2), 'batch_size': 256}<br/>
**Best CV F1-score**: 0.8610991843144769

<img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/137ae795-c5b9-493f-b99f-dba4e6530397" />

<img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/7b6d4d4a-c634-4de0-ad34-a933acdce417" />

Classification report of best model:

|                     | precision | recall | f1-score | support |
|---------------------|-----------|--------|----------|---------|
| Spruce/Fir | 0.91 | 0.88 | 0.90 | 42368 |
| Lodgepole Pine | 0.91 | 0.93 | 0.92 | 56661 |
| Ponderosa Pine | 0.90 | 0.91 | 0.90 | 7151 |
| Cottonwood/Willow | 0.84 | 0.82 | 0.83 | 549 |
| Aspen | 0.83 | 0.68 | 0.74 | 1899 |
| Douglas-fir | 0.81 | 0.82 | 0.81 | 3473 |
| Krummholz | 0.92 | 0.92 | 0.92 | 4102 |
| | | | | |
| accuracy | | | 0.90 | 116203 |
| macro avg | 0.87 | 0.85 | 0.86 | 116203 |
| weighted avg | 0.90 | 0.90 | 0.90 | 116203 |

Weighted F1-score: 0.9032524283866233

<img width="1093" height="1163" alt="image" src="https://github.com/user-attachments/assets/7bcb1d62-938d-421b-9377-4116e24396fc" />

# Conclusion
### Overall Model Performance
Given that the weighted F1-score and overall accuracy of the final model were roughly the same (about `0.9`), and that precision and recall are almost the same for the most dominant classes (Spruce/Fir and Lodgepole Pine) implies that the model is not biased towards one class.
Similar F1-scores between that of the randomised cross-validation search (`~0.86') and the final model also suggests that the selected hyperparameters generalise well to the model and that extensive hyperparameter seatches meaningfully improves model performance.
### Training vs Validation data performance
Although the curves do not overlap in either plot, this does not necessarily suggest overfitting. Looking at the plots, validation accuracy was consistently higher than training accuracy, validation loss was consistently lower than training loss, and both curves improved smoothly and plateaued together. This was because the dropout layers were switched off during the validation, so therefore the model behaves stronger during this phase, inicating effective regularisation of the neural network, as opposed to divergence or instability; the model learns the patterns without the noise.
### Class Performance and real-life ecological similarity
Looking at the confusion matrix, there is a strong diagonal dominace, meaning that the majority of the time, the predicted class by the model lined up correctly with the true class. Whilst Spruce/Fir and Lodgepole Pine both show the highest number of correct classifications, they also show the highest mutual misclassification rate due to their large representation (around 85%) in the dataset and their overlapping environmental characteristics (taking one look at each cover type shows that they are both tall, are a similar shade of green, and similar canopy shape - an easy mistake for a deep learning model to make). Because of this, even a small number of misclassifications can result in a large number of errors. The model is therefore making plausible mistakes rather than seemingly random ones.
## Final Conclusion
The deep learning neural network model was able to effectively retrieve significant associations between the features (cartographic variables) and the label (forest cover type) of the dataset, with a strong predictive performance and weighted F1-score of around `0.9`. As expected, forest types classes that dominated the dataset (Spruce/Fir and Lodgepole Pine) were classified with the highest accuracy. Minority classes, whilst exhibiting lower performnace, showed that this was due to class imbalance and real-world ecological overlap as opposed to a flaw in the model. Training data performance and the confusion matrix indicated effective regularisation and plausible misclassifications, demonstrating that the model generalises well and captures underlying environmental patterns.


