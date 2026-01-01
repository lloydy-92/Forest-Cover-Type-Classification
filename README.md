# Forest-Cover-Type-Classification
This project aims to build a deep-learning neural network model to predict the forest cover type based on certain cartographic variables. Hyperparameters were tuned via a random search cross-validation to find the most optimal model with the highest performance.

## Key Insights (Summary)
- Preprocessed dataset by scaling features (cartographic variables), handling class labels, and splitting data using `scikit-learn`.
- Built a deep learning neural network classifier using `tensorflow/keras` to predict labels (forest cover type) from features.
- Performed extensive RandomisedSearchCV using `scikeras` to identify optimal hyperparameters.
- Evaluated model perforamnce using:
  - Classification reports (precision, recall, F1-score per cover type)
  - Confusion matrices to analyse model misclassifications.
  - Training vs Validation accuracy and loss curves to assess behaviour of model generalisation.

## Tools and Libraries
| Purpose | Libraries Used |
|---------|----------------|
| Data manipulation | `pandas`, `numpy` |
| Data visualisation | `matplotlib`, `seaborn` |
| Model building and tuning | `scikeras`, `tensorflow`, `scikit-learn` |

## Installation
1. **Clone this repository**
   ```bash
   git clone https://github.com/lloydy-92/Forest-Cover-Type-Classification.git
   cd FIFA-21
2. **(Optional) Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate       # On Windows use: venv\Scripts\activate
3. **Install dependencies**
   ```bash
   pip install pandas scipy matplotlib seaborn scikeras tensorflow scikit-learn jupyter
4. **Launch the notebook**
   ```bash
   jupyter notebook CoverType-classification.ipynb

## Project Structure
```bash
Forest-Cover-Type-Classification/
├── CoverType-classification.ipynb        # Main analysis notebook
├── requirements.txt          # Python dependencies
├── analysis.md               # Written analysis file
└── README.md                 # Project documentation
```

## Contributing
Contributions, suggestions, and improvements are welcome and encouraged! If you would like the enhance any aspect of the project, such as analysis or visualisations:
1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/improve-analysis
3. Commit your changes
   ```bash
   git commit -m 'Add new visualisation'
4. Push to the branch
   ```bash
   git push origin feature/improve-analysis
5. Open a Pull Request

## Author
**Sam Lloyd**, sammy.lloyd@live.com, *github.com/lloydy-92*
