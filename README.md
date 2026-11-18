# NTUA Pattern Recognition — speech, music, and analytical exercises

This NTUA Electrical and Computer Engineering portfolio applies pattern-recognition methods to spoken digits and music. The two laboratories were implemented and submitted jointly by **Michail Athanasios Peppas** and **Panagiotis Avgerinos**. The evidence includes the original notebooks, submitted reports, Python exports, analytical solutions, and recorded outputs.

## Engineering and experimental work

| Work | Contribution and evidence |
| --- | --- |
| Spoken-digit recognition | Compared acoustic features and classical classifiers, then implemented GMM-HMM and recurrent-network experiments. [Notebook](lab/ex1/patrec1_03121026_03121023.ipynb) · [Python export](lab/ex1/patrec1_03121026_03121023.py) · [Submitted report](lab/ex1/docs/submission/patrec1_03121026_03121023_report.pdf) |
| Music genre and affect | Compared LSTM, CNN and Audio Spectrogram Transformer classifiers, then evaluated single-target regression, classification-to-regression transfer and multitask prediction. [Notebook](lab/ex2/patrec2_03121026_03121023.ipynb) · [Python export](lab/ex2/patrec2_03121026_03121023.py) · [Submitted report](lab/ex2/docs/submission/patrec2_03121026_03121023_report.pdf) |
| Analytical exercises | Studied HMM Viterbi training, online LMS classification and recurrent models. [Solution, plots and logs](analytical_exercises/README.md) |
| Semester project | The [Team 12 project index](project/README.md) points to the separate [500M training workflow](https://github.com/ntua-el21026/ntua-llama-500m-nanotron) and [artifact repository](https://github.com/ntua-el21026/ntua-llama-500m-artifacts). |

## Results and interpretation

Lab 1 records 98.6667% test accuracy for the validation-selected BiLSTM and 94.67% for the separate GMM-HMM. The saved GMM-HMM output logs no test-triggered refits. The [evaluation notes](lab/README.md#evaluation-interpretation) explain the conditional refit rule and its implications.

In Lab 2, the 2D CNN on mel spectrograms achieved 41.57% test accuracy and a macro-F1 of 0.3312 over ten genres, with uneven per-class performance. The [laboratory guide](lab/README.md#lab-2-music-genre-and-affect) compares the CNN with the Audio Spectrogram Transformer and describes the separate affect-prediction evaluation.

## Reproduction and external inputs

Open the notebooks to review the experiments, or clone the repository to work with a local copy.

```bash
git clone https://github.com/ntua-el21026/ntua-pattern-recognition-public.git
cd ntua-pattern-recognition-public
```

Lab 1 includes all **3,000 Free Spoken Digit Dataset recordings** under their own license. The **separate group of 135 preparatory WAVs** is an external course input for the acoustic-feature and preliminary classifier work. Lab 2 needs separately authorized music arrays, matching course helpers and applicable checkpoints. The [laboratory guide](lab/README.md) gives input paths and evaluation protocols, and the [support-code guide](lab_material/README.md) records the external references and revision caveats.

Local verification read the bundled 8 kHz mono WAV payloads and checked the balance across six speakers and ten digit classes. Complete Colab/Kaggle reproduction depends on access and environment compatibility, particularly the audio/HMM stack. There is no unified locked environment. The historical Python exports preserve notebook-specific syntax. Use a separate output location for new results.

The [course reading and attribution index](docs/README.md) documents external references and the retained learning resources. The [MIT notice](LICENSE) applies to original contributions covered by it. Third-party materials retain their own terms and attribution.
