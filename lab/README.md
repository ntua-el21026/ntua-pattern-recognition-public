# Audio-learning laboratory work

The notebooks are the primary executable narratives; their Python exports and PDF reports retain the original submissions. The two-person team is Michail Athanasios Peppas and Panagiotis Avgerinos. The original `lab/docs/` template location is a historical workflow reference. Obtain the course report and notebook templates through the [official course](https://cvsp.cs.ntua.gr/pattern-recognition/) if needed for an assessment reproduction.

## Lab 1: speech features and spoken digits

Start with [the notebook](ex1/patrec1_03121026_03121023.ipynb) and [submitted report](ex1/docs/submission/patrec1_03121026_03121023_report.pdf). The work covers:

- Praat pitch/formant inspection recorded in the report, followed by MFCC, delta/delta-delta and summary-feature analysis.
- Gaussian Bayes, SVM, k-NN, logistic-regression and decision-tree comparisons.
- A recurrent sine-to-cosine exercise and spoken-digit GMM-HMM/recurrent-network experiments.

The committed notebook has 46 cells, including 20 code cells. These counts describe the preserved file, not a successful rerun.

### Data and path setup

The two corpora support different experiments. The preparatory recordings are external. The 3,000 FSDD WAVs are included under their upstream terms.

| Resource | Repository path | Contents |
| --- | --- | --- |
| Preparatory corpus | `ex1/material/pr_lab2_data/` after obtaining the lab package through the [official course](https://cvsp.cs.ntua.gr/pattern-recognition/) | 135 external WAVs. The package supplies 133 isolated digits in `digits/`, plus `onetwothree1.wav` and `onetwothree8.wav` for sequence examples. These inputs support feature inspection and preliminary classifier exercises. |
| Free Spoken Digit Dataset | [ex1/material/free-spoken-digit-dataset/](ex1/material/free-spoken-digit-dataset/) | 3,000 WAVs in `recordings/`, with upstream README and utilities |

For the preparatory experiments, obtain the original audio package via authorized course access and extract it to `lab/ex1/material/pr_lab2_data/` locally. Create that directory as part of setup. Without the package, those experiments are unavailable for exact reruns and the authored explanations and recorded outputs remain inspectable.

In a **copy** of the notebook, replace the Google Drive mount/setup cell with paths appropriate to your checkout. With the kernel working directory at the repository root, the initial preparatory path is:

```python
from pathlib import Path
repository = Path.cwd().resolve()
dataset_path = str(repository / "lab/ex1/material/pr_lab2_data")
```

The later FSDD cell assigns a separate old Drive-based `dataset_path` and changes the working directory. Replace that assignment in the working copy with `str(repository / "lab/ex1/material/free-spoken-digit-dataset/recordings")`. Keep `repository` absolute, and inspect the subsequent directory changes rather than replacing only the first path. The HMM/recurrent sections expect `recordings/*.wav`; the final section also searches several relative locations.

For Colab, open/upload a notebook copy and make the repository data available in that runtime. The personal Drive layout embedded in the submission is historical, not a required storage account. NumPy/audio-processing and pomegranate API compatibility still need qualification; the notebooks do not pin resolved package versions.

### Evaluation interpretation

The preparatory classifier comparison uses a stratified 70/30 split with random state 0. FSDD instead fixes utterance indices 0–4 as test and derives validation data from the remaining pool. Preserve these distinct protocols and fit preprocessing only on the corresponding training data.

Step 12 fits a GMM-HMM per digit on the combined training and validation sets, then evaluates all digits on the test set. For each digit with zero correct test predictions in the initial pass, the code allows up to three deterministic reseeds and refits using that digit’s training and validation data. Each refit reruns evaluation on the full test set and updates the reported scores if the target digit improves above zero. The stored run records 94.67% overall accuracy before and after the retry stage, with no retries logged. A triggered retry would use test outcomes for model selection. The 98.6667% test accuracy in the submitted report (page 28) belongs to the separate BiLSTM selected on validation loss, with validation accuracy used to break ties. Both procedures and the weaker configurations remain visible in the original notebooks and reports.

## Lab 2: music genre and affect

Read [the notebook](ex2/patrec2_03121026_03121023.ipynb), [submitted report](ex2/docs/submission/patrec2_03121026_03121023_report.pdf) and [course support for the data-loading tutorial](https://github.com/slp-ntua/patrec-labs/tree/180ec709c2e26860d05f59106e5cb3be64612d06). The notebook has 41 cells, including 21 code cells.

Steps 0–7 explore mel/chroma and beat-synchronized features, label consolidation, an LSTM classifier, CNNs and an Audio Spectrogram Transformer. Steps 8–10 compare single-target affect regression, classification-to-regression transfer and joint valence/energy/danceability prediction. The optional Step 11 is not part of the submission. Genre evaluation includes accuracy, precision, recall, F1 and confusion matrices. Regression uses MSE and Spearman rank correlation.

In the submitted ten-class genre experiment, the 2D CNN on mel spectrograms recorded test accuracy 0.4157 and macro-F1 0.3312 (report p. 22). The Audio Spectrogram Transformer recorded 0.3757 and 0.3261 under the same splits (p. 24). The per-class results show that both models performed unevenly across genres. These figures describe the saved coursework runs.

### External inputs

Obtain the music arrays, checkpoints and course helper files through authorized access to the corresponding sources. These are separate from the Lab 1 audio inputs. The notebook references the following sources.

- [geoparslp/patreco3-multitask-affective-music](https://www.kaggle.com/datasets/geoparslp/patreco3-multitask-affective-music): prepared music arrays and labels.
- [multitask-affective-music-lab-2022](https://www.kaggle.com/competitions/multitask-affective-music-lab-2022): competition source, subject to its access/participation requirements.
- `michaelpeppas/preparation-dataset`: historical Kaggle identifier from the exported setup. Public access to this dataset could not be verified.
- The external `dataset.py`, `lstm.py`, `modules.py` and other course helpers come from [slp-ntua/patrec-labs](https://github.com/slp-ntua/patrec-labs). See [the recorded revision](../lab_material/README.md).

Kaggle is the original execution layout. Attach the required data there and confirm that the path `../input/patreco3-multitask-affective-music/data/` resolves from the working directory. Expected subdirectories include `fma_genre_spectrograms/`, `fma_genre_spectrograms_beat/` and `multitask_dataset/`, with train/test arrays and the corresponding label files. Later cells also contain absolute `/kaggle/input/` paths. The exported Colab setup uses `kagglehub`, but later path cells do not automatically use its returned download locations; adapt all of them in a separate notebook copy for another environment.

The original notebook clones the course repository and adds its `lab3` directory to `sys.path`. The linked source is needed for the dataset adapters and course model utilities. The repository includes the team’s experiment notebooks and supplementary regression, transfer and multitask modules. Recover the [recorded support-code revision](../lab_material/README.md) before checking compatibility. The files [step8_regression.py](ex2/codex/step8_regression.py), [step9_transfer.py](ex2/codex/step9_transfer.py) and [step10_multitask.py](ex2/codex/step10_multitask.py) depend on preceding notebook globals/backbones and are supplementary experiments, not standalone CLI programs.

## Evidence and rerun record

Original figures and submission files remain in the [Lab 1 documentation](ex1/docs/) and [Lab 2 documentation](ex2/docs/). The old Colab link and signed Kaggle export URL in the Python headers are historical source locations. The preserved notebooks provide review access directly.

Before a rerun, record the source commit, exact packages and managed runtime, hardware, seeds, data/helper/pretrained-model revisions and hashes, split definitions and checkpoint-selection rule. Store new checkpoints/results separately and label them as new observations.
