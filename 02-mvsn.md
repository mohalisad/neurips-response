Thank you for your thorough review and insightful questions. We appreciate your feedback and will address your comments and questions:

Regarding the weaknesses:

1. Explanation and justification:
We appreciate your feedback on the need for more detailed explanations. Our method provides the model with multiple initialization vectors simultaneously, allowing it to choose and combine them optimally. This approach enhances robustness to initialization choices, addressing limitations in existing methods. We will elaborate on this in the camera-ready version to improve clarity.

2. Clarity and Writing:
We apologize for any lack of clarity in our paper and will address this in the camera-ready version. To clarify our methodology: we randomly sampled m unique tokens from the embedding layer and fixed these samples across all tasks, both with and without dropout. This consistency allows for fair comparisons across experiments.

3. Experimental scope:
We understand the importance of experimenting with different architectures and larger models. However, the current experiments (over 200 for Table 1 alone) were already computationally intensive. We aimed to balance thoroughness with feasibility given our resources. We will consider expanding our experiments in future work.

Addressing your questions:

1. Addressing limitations of existing techniques:
As mentioned earlier, our method provides multiple initialization vectors simultaneously, allowing the model to optimally choose and combine them. This approach enhances robustness to initialization choices, a key limitation in existing soft prompt tuning techniques.

2. Sampling from embedding tokens: The reason to sample from the embedding layer, as mentioned in the paper, is that "initializing prompts with token representations is generally more effective than starting with random vectors (Lester et al., 2021)." To elaborate, in deep learning, it's important to maintain a consistent input distribution for the network. In prompt tuning, the main transformer network is frozen, so it's beneficial to initialize prompts in a way that's familiar to the network. Regarding the sampling process, we randomly sampled m unique tokens from the embedding layer and fixed these samples across all tasks and in both cases of with and without dropout. We chose m=128 tokens, as mentioned in the ablation study. We didn't experiment with multiple sets of tokens or different sampling strategies, as our initial results were promising with this simple approach.

3. Choice of weighted sum:
The weighted sum is equivalent to a linear layer without bias. We experimented with adding non-linearities to different parts of the network, but similar to the softmax experiments detailed in Appendix A.2, these resulted in significant performance drops. Therefore, we did not pursue this direction further.

4. Dropout omission:
We discovered after submission that T5v1.1 was pre-trained without dropout. This information will be addressed in the camera-ready version. Enabling dropout during fine-tuning can introduce significant noise, especially for parameter-efficient methods like prompt tuning. While dropout might benefit full fine-tuning through regularization, prompt tuning appears to suffer from this added noise. We hypothesize that if the network had been pre-trained with dropout, the performance difference might not have been as notable.

We appreciate your valuable feedback and questions, which have helped us identify areas for improvement in our paper. We will incorporate these insights into our camera-ready version to enhance the clarity and depth of our work.
