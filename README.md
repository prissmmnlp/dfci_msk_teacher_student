# dfci_msk_teacher_student_imaging

This repository contains training, inference, and evaluation code for extracting cancer outcomes from imaging reports based on the paper "Shareable artificial intelligence to extract cancer outcomes from electronic health records."

Preprocessing code is included but would need to be modified to work on external EHR data depending on its data delivery format.

To run inference, use the notebook 5_external_prissmm_inference.ipynb. You will need a dataset containing a column labeled "text", in which each observation corresponds to the imaging report on which you would like to run inference. The notebook currently runs inference on synthetic_example_imaging_data.csv, yielding output file synthetic_example_imaging_inference_result.csv .

Student model weights can be obtained from https://huggingface.co/kenlkehl/dfci-student-imaging .  A Docker image that will run inference on a synthetic dataset of five imaging reports is also available there.

The model will output predicted logits (log odds) that the following outcomes are present in each report:
1) Any cancer
2) Response to therapy/improving cancer
3) Progression of disease/worsening cancer
4) Brain metastasis
5) Bone metastasis
6) Adrenal metastasis
7) Liver metastasis
8) Lung metastasis
9) Lymph node metastasis
10) Peritoneal metastasis
