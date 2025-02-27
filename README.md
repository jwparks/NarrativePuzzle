# NarrativePuzzle
## Description
This repository contains the code for the paper **"Solving the Narrative Puzzle: Hippocampal Systems for Event Encoding and Sequencing during Ongoing Comprehension"** by Park et al. (in prep.).
The paper investigates how the hippocampus contributes to encoding individual events and sequencing them into a coherent narrative during ongoing comprehension.
This repository provides the analysis code required to reproduce the results presented in the paper.
To ensure reproducibility, we have verified that all analysis scripts run successfully in an independent environment with all necessary resources available in the code and data repository.

## Data
For reproducibility, we provide the preprocessed data used in this study:
- **DATA/**: Contains behavioral scores, ROI time series, and functional connectivity data required to reproduce all results in the paper. Due to the large data size, we have uploaded it to an external storage, which can be accessed [here](https://drive.google.com/file/d/15x0pxJV8RZ7CdPGaJzbbRSG-nSJMNiQg/view?usp=sharing).
- **utils/**: Contains behavioral data (free recall in Korean), movie annotations, and brain atlases used for analysis.

For access to the raw fMRI data used in this study, please refer to the [OpenNeuro](https://openneuro.org/datasets/ds005215) repository. The data is organized in BIDS format and includes the following files:
- `sub-<subject_id>/anat/sub-<subject_id>_T1w.nii.gz`: Structural MRI data for each subject.
- `sub-<subject_id>/func/sub-<subject_id>_task-filmrecall_run-1.nii.gz`: fMRI data for each subject.
> **Note**: All neuroimaging data has been defaced and does not contain any personally identifiable information.

## Code Description
### Main Figures
- **`Figure_2.ipynb`**: Assessment of content and sequence memory in ongoing narrative comprehension.
- **`Figure_3.ipynb`**: Predictive modeling of content and ordering scores using functional connectivity patterns.
- **`Figure_4.ipynb`**: Identification of event sequencing moments using LLMs based on moment-by-moment narrative coherence.
- **`Figure_5.ipynb`**: Predictive performance of the hippocampo-cortical model using LLM-generated sequencing moments.
> **Note**: `Figure_1` is not included in this repository as it is a schematic figure that can be generated separately.
### Supplementary Figures
- **`Figure_S1.ipynb`**: Structure of the temporally scrambled movie stimulus with sequencing and post-event boundary moments.
- **`Figure_S2.ipynb`**: Assessing individual narrative memories using a topic model.
- **`Figure_S4.ipynb`**: Performance of the hippocampo-cortical FC model across different cortical parcellation schemes.
- **`Figure_S6.ipynb`**: Performance of the FC-based predictive models with and without hippocampal connectivity.
- **`Figure_S7.ipynb`**: Supplementary analysis of the LLM-generated sequencing moments.
> **Note**: `Figure_S3` and `Figure_S5` are not included in this repository as they consist of brain maps with varying parcellation schemes that can be generated using `Figure_3.ipynb`.

## Python Environment
To reproduce the results, we recommend using the following Python environment:
```bash
conda create -n narrative_puzzle python=3.10
conda activate narrative_puzzle
git clone https://github.com/jwparks/NarrativePuzzle.git
pip install -r requirements.txt
```
### Key dependencies:
- Python 3.10
- NumPy (`numpy==1.25.0`)
- SciPy (`scipy==1.15.1`)
- pandas (`pandas==2.0.2`)
- KoNLPy (`konlpy==0.6.0`)
- scikit-learn (`scikit-learn==1.2.2`)
- statsmodels (`statsmodels==0.14.0`)
- matplotlib (`matplotlib==3.7.1`)
- seaborn (`seaborn==0.13.2`)
- nibabel (`nibabel==5.1.0`)
- nilearn (`nilearn==0.10.1`)
- nltools (`nltools==0.4.7`)
For additional dependencies, please refer to `requirements.txt` included in the repository.

## Running the Analysis
To run the analysis and generate figures, execute the Jupyter notebooks in the order outlined in the **Code Description** section. Ensure the required data files are downloaded and placed in the appropriate directories before execution.
For any issues or questions, please contact **[jiwoongpark@skku.edu]**.