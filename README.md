# dfci_msk_teacher_student_imaging

This repository contains training and inference code for extracting cancer outcomes from imaging reports based on the paper "Shareable artificial intelligence to extract cancer outcomes from electronic health records."

Preprocessing code is included but would need to be modified to work on external EHR data depending on its data delivery format.

To run inference, use the file 5_external_prissmm_inference.ipynb. You will need a dataset containing a column labeled "text", in which each observation corresponds to the imaging report on which you would like to run inference.

Student model weights can be obtained from https://huggingface.co/kenlkehl/dfci-student-imaging .

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
