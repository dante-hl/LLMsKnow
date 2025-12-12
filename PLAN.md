


1. for a certain dataset (or subset of it), generate responses from large(r) model. get 


paper's approach: train probing classifiers on models themselves:
- given a dataset of questions with ground truth answers, create a dataset of (question, hallucination_indicator) by 
  - feeding question to model and comparing the model's output to the ground truth answer
  - generate_model_answers.py should produce the answers to questions, and extract_exact_answer actually obtains the exact answer from the model response
- 


TODOs
- map out what generate_model_answers.py returns (for now lets look at triviaqa dataset)
- get generate_model_answers.py to work with small model Qwen-3-1.7b-base
  - what type of model does geneate_model_answers expect? HF models i assume?


  https://github.com/huggingface/transformers/blob/main/src/transformers/generation/utils.py#L150

  generate_model_answer returns four lists. the types of contents of each list are shown below, next to the list containing it
  
  model_answers: model answers
  input_output_ids: list of indices representing tokens of entire sequence (both input and output), one list per question/answer
  all_scores: logits for all generated tokens in an answer, arranged in a tensor of shape (num_generated_tokens, vocab_size)
  all_output_ids: list of indices representing tokens of generated output, one list per question/answer