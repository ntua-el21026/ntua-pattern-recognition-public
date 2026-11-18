# Course notes and references

- [bibliography/](bibliography/) contains the retained open book, educational-use slides and supplementary links.
- [exam_notes/](exam_notes/) contains LaTeX exam notes and their compiled PDF.
- [project_structure/](project_structure/) contains a structure-generation script and a captured tree; the capture is historical and may differ from the current checkout.

The OneDrive folder in `bibliography/ML_Intro.txt` and external lecture links are supplementary references, not required inputs for inspecting the submitted laboratory notebooks.

For executable work and data prerequisites, start with [the laboratory guide](../lab/README.md). The separate [semester-project index](../project/README.md) links to the Team 12 workflow and artifacts.

## Reading and course sources

- Dan Jurafsky and James H. Martin, *Speech and Language Processing*, 24 August 2025 [archived draft](https://web.stanford.edu/~jurafsky/slp3/ed3book_aug25.pdf) and [HMM appendix](https://web.stanford.edu/~jurafsky/slp3/old_aug25/A.pdf).
- Lawrence R. Rabiner, *A Tutorial on Hidden Markov Models and Selected Applications in Speech Recognition*. [IEEE DOI](https://doi.org/10.1109/5.18626)
- [HMM acoustic modelling](https://maelfabien.github.io/machinelearning/speech_reco_1/), [Andrej Karpathy's RNN article](https://karpathy.github.io/2015/05/21/rnn-effectiveness/), [Christopher Olah's LSTM article](https://colah.github.io/posts/2015-08-Understanding-LSTMs/) and the [NeurIPS interpretability tutorial](https://shichangzh.github.io/xaiTutorial/).
- A. Potamianos and V. Digalakis, *Probability Notes for Engineers*, Technical University of Crete, 2009. Consult the university holdings or course bibliography for the cited edition.
- [NTUA Pattern Recognition course](https://cvsp.cs.ntua.gr/pattern-recognition/) for the lab statements, analytical exercise prompts, topic bank and templates. See [pinned lab support](../lab_material/README.md) for setup.
- [Generative AI with Large Language Models](https://www.deeplearning.ai/courses/generative-ai-with-llms) for the three course lab notebooks.

## Role of externalized material

| Material | Role and reproduction |
| --- | --- |
| Stanford drafts and HMM appendix, Rabiner tutorial, third-party reading mirrors and the probability-notes edition | Theory references for speech modelling, recurrent networks, interpretability or probability. The source links above replace the copied publications. The analytical solutions, exam notes and authored classification/HMM work remain. Replaying that work has no dependency on local publisher PDFs. |
| Course handouts, prompt sets, topic bank, supplied notebook and report templates | These defined the assessment tasks and submission structure. Consult the authorized NTUA course for the correct edition. The repository includes authored reports, analytical solutions, lab code and results. Older path captures may refer to the supplied files. |
| Three DeepLearning.AI course notebooks | Separate guided language-model exercises. The course platform supplies authorized access. The retained Week 1–3 slides have their own narrower educational-use basis. These notebooks play no runtime role in the submitted speech and music laboratories. |
| Preparatory audio package and example helpers | The 135 preparatory WAVs were input data for early Lab 1 exercises. Lab 2's mirrors supplied example support for feature loading and modelling. Obtain the matching course materials through authorized access. [Laboratory inputs](../lab/README.md) and [helper references](../lab_material/README.md) give the layouts. Exact reproduction is conditional on the relevant inputs and environment. |

## Retained third-party material

- [Free Spoken Digit Dataset](../lab/ex1/material/free-spoken-digit-dataset/) by the [upstream authors and contributors](https://github.com/Jakobovski/free-spoken-digit-dataset/tree/26eb9aaf76e81b692f806f9140c2d2777410d7a1), [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode.en). The 3,000 recordings and 12 ancillary files match that revision. Two acquisition scripts differ only by newline normalization. The original upstream README and credits remain.
- [Dive into Deep Learning](bibliography/Dive%20into%20Deep%20Learning.pdf) by Aston Zhang, Zachary C. Lipton, Mu Li and Alexander J. Smola. [Official edition](https://d2l.ai/d2l-en.pdf), [CC BY-SA 4.0 book text](https://github.com/d2l-ai/d2l-en/blob/master/LICENSE), [modified MIT terms for sample code](bibliography/D2L-LICENSE-SAMPLECODE.txt), copied from the [upstream license](https://github.com/d2l-ai/d2l-en/blob/master/LICENSE-SAMPLECODE). The original PDF is unmodified.
- [Week 1](bibliography/llm%20class%20from%20coursera/W1.pdf), [Week 2](bibliography/llm%20class%20from%20coursera/W2.pdf) and [Week 3](bibliography/llm%20class%20from%20coursera/W3.pdf) slides are reproduced unchanged with credit to DeepLearning.AI for this noncommercial educational portfolio. Their notices expressly allow educational copying with attribution, disallow commercial distribution, and separately link [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/legalcode). This portfolio relies on the narrower printed educational permission.
