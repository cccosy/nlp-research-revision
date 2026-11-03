# T1S2 — Teacher 1 / Student 2 (69 classes)

## Experiment identification
- Task: plant species-condition classification (69 classes)
- Teacher 1: **ResNet34**, paired with the corrected-dataset run in `teacher1results/resnet34_corrected_dataset_69classes/`
- Student 2: **MobileNetV2** (not MobileNetV3-Small)
- Knowledge distillation: temperature = 4.0; alpha = 0.5; 30 epochs; batch size = 128; learning rate = 0.0001

## Recorded results
- Teacher 1 best validation accuracy: 96.17184887997325% (from teacher run summary)
- Student 2 best validation accuracy: 96.07990638582414% (from student summary)
- Student 2 best validation epoch in the CSV log: 28
- Re-evaluated student validation loss: 0.1953976702222813
- Teacher / student parameters: 21,320,069 / 2,312,261 (approximately 89.15% fewer parameters)
- Validation-accuracy difference: approximately 0.09194 percentage points

## Files
- `summary.json`: original student summary, stored under a non-conflicting name
- `student_mobilenetv2_log.csv`: student training and validation metrics for 30 epochs

## Checkpoint files supplied separately (not pushed)
The two PyTorch weights were received but could not be uploaded through the current GitHub text-file connector; they are **not** in this GitHub folder:
- `best_student.pth`: 28,135,745 bytes; SHA-256 `684e9c222b0f36c27f186dcb141d4b14ba3484692416324dc5ddbe8c57abfc65`
- `student_latest.pth`: 28,137,333 bytes; SHA-256 `023ffe72827b84dec8b91e257f36f228c1af7b531867018d0e5af7c8c9a00d03`

For checkpoint upload, use GitHub Desktop / git on your computer (both files are under GitHub's 100 MiB per-file Git limit) or use Git LFS for model-weights management. Consider keeping the repo private until the paper is ready for release.

## Paper revision caution
The original draft described a **17-class ResNet34 → MobileNetV3-Small** experiment and much higher validation accuracies. This T1S2 run is a different **69-class ResNet34 → MobileNetV2** configuration; do not carry original metrics or architecture names into a revised Results section without re-verification.
