Thank you for your review and feedback. We appreciate your thoughtful comments and would like to address the weaknesses you mentioned:

1. While we acknowledge that the idea of reusing selected vocabulary embeddings via a weighting scheme may seem straightforward, we believe its simplicity is a strength. Our method outperforms other mentioned approaches while offering a simpler implementation, which can be valuable for practical applications and ease of adoption.

2. Regarding turning off the dropout in the frozen part of the model during prompt tuning, we respectfully disagree that this is "very natural and actually a must." To the best of our knowledge, most implementations of PEFT (Parameter-Efficient Fine-Tuning) libraries do not provide an option to disable dropout in the frozen network. We have not encountered any methods that explicitly mention experimenting with this setup. Our finding highlights an important consideration that has been overlooked in previous work and can significantly impact performance.

We believe these aspects contribute to the novelty and value of our work. We would be happy to provide further clarification or additional information if needed.
