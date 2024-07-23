# dfci_msk_teacher_student_imaging

This repository contains training, inference, and evaluation code for extracting cancer outcomes from imaging reports based on the paper "Shareable artificial intelligence to extract cancer outcomes from electronic health records."

Preprocessing code is included but would need to be modified to work on external EHR data depending on its data delivery format. Preprocessing is done in 1_json_to_csv_imaging.ipynb and 2_link_text_to_imaging_labels.ipynb.

Training and initial evaluation of the DFCI-imaging-teacher model is done in 3_train_dfci_teacher.ipynb. Training and initial evaluation of the DFCI-imaging-student model is done in 4_train_mimic_student.ipynb. These notebooks are provided for illustration purposes only, since we cannot share the private PHI data used to train the teacher, and the MIMIC data are available on Physionet to credentialed users.

In accordance with policies specified on the MIMIC-IV dataset site, which require that models trained using MIMIC data be released through Physionet to enable proper credential checks, student model weights and sample code for inference on synthetic data have been submitted to Physionet. To run inference after obtaining the weights, the notebook 5_external_prissmm_inference.ipynb can also be used. It expects a dataset containing a column labeled "text", in which each observation corresponds to the imaging report on which you would like to run inference. The notebook currently runs inference on synthetic_example_imaging_data.csv, yielding output file synthetic_example_imaging_inference_result.csv 

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
