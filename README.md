# Grammar-Correction-Model
 A PyTorch implementation of a grammar correction model based on the T5 transformer architecture, trained on a subset of the [C4](https://huggingface.co/datasets/liweili/c4_200m/viewer/default/train?views%5B%5D=train) dataset. 

The model is designed to automatically correct grammatical errors in English sentences by restructuring and refining the input into a grammatically sound form.


- **Model Architecture**: T5
- **Training Objective**: Transform input text into its grammatically correct version.
- **Dataset**: A subset of the C4 dataset
- **Evaluation Metric**: [GLEU](https://huggingface.co/spaces/evaluate-metric/google_bleu), preferred over BLEU for sentence-level grammatical evaluation.
- **Training Details**: trained for 1 epoch (~50k steps), achieving a validation GLEU score of 0.52.

## T5 Or BART
- T5 is preferred over BART for the following reasons:
  - T5 was pretrained for filling missing spans, making it ideal for minimal and local correction tasks.
  - T5 accepts explicit task prompts (e.g., "fix grammar:") that guide the model to produce more focused and precise outputs..
  
## Output Example

Input: ```fix grammar:My names is ali and i went at school yesterday```

Model output: ```My name is ali and i went to school yesterday.```
