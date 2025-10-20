## License
This software is available under the Academic/NonCommercial License:

- Free for academic, research, and educational use.
- Commercial use requires a separate license.

For commercial licensing inquiries, contact: xavisanco@gmail.com & jordi.sole@uvic.cat

VOMEDIAL: Voice Mental Disorders Algorithm

VOMEDIAL (Voice Mental Disorders Algorithm) is an academic implementation for analyzing and classifying voice signals in individuals with and without depression.
It is based on the paper:

Sánchez-Corrales, F. J., & Solé-Casals, J. (2025). Feature Extraction in Voice Signals for Depression Detection: A Machine Learning Perspective with Empirical Mode Decomposition.

OVERVIEW

This algorithm processes voice signals from clinically evaluated participants (depressed vs. healthy) using Empirical Mode Decomposition (EMD) and machine learning techniques.

Main steps:

Signal Decomposition
Each voice signal is decomposed into Intrinsic Mode Functions (IMFs) using EMD.

Similarity Analysis
Gaussian kernel similarity is computed between IMFs from both groups.
IMFs with similarity ≤ 1e-10 are selected as relevant.

Feature Extraction
Selected IMFs are divided into windows.
Descriptive statistics are extracted: mean, median, standard deviation, skewness, kurtosis.

Data Balancing
Random undersampling ensures equal sample sizes per class.

Model Training
Gradient Boosting model trained and tuned using GridSearchCV with cross-validation.
Metrics: Accuracy, Precision, Recall, F1-score, Specificity.

Visualization
ROC curve and confusion matrix display classification performance.

RESULTS

VOMEDIAL automatically identifies the most discriminative frequency bands (IMFs) and builds robust models for differentiating healthy and depressed voice samples.
This facilitates the exploration of vocal biomarkers for mental health in a reproducible, transparent, and scalable way.

USAGE

Clone the repository and install the dependencies:

git clone https://github.com/Xavisanco/VOMEDIAL-Voice-Mental-Disorders-Algorithm---Depression

cd VOMEDIAL-Voice-Mental-Disorders-Algorithm---Depression
pip install -r requirements.txt

Run the main script:

python female_eval_model.py

Note: The original clinical dataset used to develop the algorithm is not included in this repository due to ethical and data protection restrictions.
Users must adapt their own data to the same input structure and preprocessing format described in the documentation to run the algorithm properly.

LICENSE

This code is released under an Academic/NonCommercial License.
Free for academic and research purposes.
Commercial use requires explicit written permission from the authors.

See the full license text in LICENSE.txt.

AUTHORS

F. Javier Sánchez Corrales
Email: xavisanco@gmail.com

Jordi Solé-Casals
Email: jordi.sole@uvic.cat

CITATION

If you use this code, please cite:

Sánchez-Corrales, Xavier., & Solé-Casals, Jordi. (2025).
Analyzing Male Depression Using Empirical Mode Decomposition. 
In Proceedings of the 18th International Joint Conference on Biomedical Engineering Systems and Technologies - BIOSIGNALS; 
ISBN 978-989-758-731-3; ISSN 2184-4305, SciTePress, pages 886-892. DOI: 10.5220/0013157600003911

NOTES

This tool is intended for research and educational purposes only.
It must not be used for clinical diagnosis or commercial deployment without prior authorization.
