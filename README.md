# Brain Tumor DNA Analysis and Treatment Recommendation System

## Overview
This project is a comprehensive system for analyzing DNA sequences associated with brain tumors and generating personalized treatment recommendations. It integrates advanced machine learning models, including DNABERT and SmileBERT, to process DNA sequences, classify tumor types, and suggest both standard and novel treatments. The system also includes visualization capabilities for molecular structures and a web interface for user interaction.

## Features
- **DNA Sequence Analysis**: Processes DNA sequences to identify tumor-specific patterns and characteristics.
- **Tumor Type Classification**: Predicts brain tumor types (e.g., glioma, meningioma, pituitary, healthy, or unknown) based on DNA sequence features.
- **Treatment Recommendations**: Provides standard treatments from a knowledge base, personalized treatments based on DNA characteristics, and AI-suggested novel treatments using SmileBERT.
- **Molecular Visualization**: Generates visual representations of recommended treatment molecules using RDKit.
- **Web Interface**: Offers a Flask-based web application for users to input DNA sequences and receive treatment recommendations, accessible via a public URL using pyngrok.
- **Data Processing**: Handles multimodal imaging data (CT and MRI) and generates synthetic DNA sequences for analysis.
- **Validation and Statistics**: Validates generated DNA sequences and provides detailed statistics on sequence features and treatment outcomes.

## Requirements
- Python 3.10+
- Libraries: `biopython`, `pandas`, `transformers`, `torch`, `rdkit`, `matplotlib`, `seaborn`, `scikit-learn`
- Kaggle dataset: [Brain Tumor Multimodal Image CT and MRI](https://www.kaggle.com/datasets/murtozalikhon/brain-tumor-multimodal-image-ct-and-mri)
- Pre-trained models: DNABERT (`zhihan1996/DNA_bert_6`), SmileBERT (`seyonec/PubChem10M_SMILES_BPE_450k`)
- ngrok authtoken for web interface deployment

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/brain-tumor-dna-analysis.git
   cd brain-tumor-dna-analysis
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Download the Kaggle dataset and place it in the project directory or use the provided Kaggle API download in the notebook.

## Usage
1. Run the Jupyter notebook (`cagg.ipynb`) to process data, generate DNA sequences, and analyze treatments.
2. Use the Flask web interface to input DNA sequences and view treatment recommendations:
   ```bash
   python app.py
   ```
3. Access the web interface via the ngrok-generated public URL (displayed in the terminal).

## Output
- **CSV Files**:
  - `image_sequence_mapping.csv`: Mapping of images to synthetic DNA sequences.
  - `brain_tumor_dna_sequences.csv`: Generated DNA sequences with tumor metadata.
  - `brain_tumor_dna_validation_results.csv`: Validation results for DNA sequences.
  - `dataset_statistics.csv`: Summary statistics of the dataset.
  - `brain_tumor_treatment_summary.csv`: Summary of treatment recommendations.
- **Visualizations**:
  - Molecular structure images (`treatments_for_<tumor_type>.png`).
  - Plots of sequence features and validation metrics.

## Dataset
The project uses the [Brain Tumor Multimodal Image CT and MRI dataset](https://www.kaggle.com/datasets/murtozalikhon/brain-tumor-multimodal-image-ct-and-mri) from Kaggle, containing CT and MRI images of brain tumors classified into glioma, meningioma, pituitary, healthy, and unknown tumor types.

## Models
- **DNABERT**: Used for DNA sequence generation and validation, tailored for brain tumor characteristics.
- **SmileBERT**: Employed for generating novel treatment recommendations based on DNA sequence patterns.
- **RDKit**: Utilized for visualizing molecular structures of recommended treatments.

## Web Interface
The Flask-based web interface allows users to:
- Input DNA sequences and optionally specify tumor types.
- View predicted tumor types (if not specified).
- Receive detailed treatment recommendations, including standard, personalized, and AI-suggested treatments.
- Download visualizations of molecular structures.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue for bug reports, feature requests, or improvements.

## Acknowledgments
- Kaggle for providing the brain tumor dataset.
- Hugging Face for the pre-trained DNABERT and SmileBERT models.
- RDKit for molecular visualization capabilities.
