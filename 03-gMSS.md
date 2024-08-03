Thank you for your thorough review and insightful questions. We appreciate your feedback and will address your comments and questions:

Regarding the figures:
We understand your concern about Figure 2 containing multiple unrelated subfigures. While we initially thought consolidating them might be more concise (similar to some journal publications), we agree that separating them could improve clarity. We will revise this in the camera-ready version.

Concerning the appendix reference:
We appreciate your suggestion to move the forward reference to appendix A2 to the discussion of our method. We agree this would provide better context and address potential questions about the softmax application earlier. We will implement this change in the revised version.

Addressing your questions:

1. Conditioning p' on input:
We have indeed considered extending the method to make p' weighting input-dependent. The main challenge lies in the embedding layer's position as the first layer after the tokenizer, where inputs are sequences of token IDs. To condition p' on the input effectively, we would need to design a network agnostic to varying input lengths, such as a pooling layer. Our initial experiments with pooling on input embeddings alone did not yield satisfactory results. While this idea merits further exploration, finding an effective way to condition p' on input requires more extensive research.

2. Dropout and T5 pre-training:
Thank you for bringing up this important point about T5v1.1 being pre-trained without dropout. We noticed this after submitting the paper and plan to address it in the camera-ready version. This information, while not prominent in the original paper, is mentioned in sources like the Hugging Face model card. We now believe that the network's pre-training without dropout likely contributes to our findings. Enabling dropout during fine-tuning can introduce significant noise, especially for parameter-efficient methods like prompt tuning. While dropout might benefit full fine-tuning by providing regularization, prompt tuning seems to suffer from this added noise. We hypothesize that if the network had been pre-trained with dropout, the performance difference might not have been as notable.


We appreciate your valuable feedback and questions, which have helped us refine our understanding and presentation of the work.
