# fine-tuning
Fine-tuning a LLM for a specific task in a niche domain.

## Future Work / To-Do

This list outlines potential next steps to further enhance and productionize the fine-tuned customer service model.

### Training & Data Enhancement

- [ ] **Increase Training Duration:** Extend training beyond the initial `max_steps=13` (e.g., train for full epochs or based on validation performance) to allow the model to learn more deeply from the dataset.
- [ ] **Systematic Hyperparameter Tuning:** Optimize key hyperparameters (`learning_rate`, LoRA `r`, `lora_alpha`, `weight_decay`, etc.) by monitoring performance on a validation set.
- [ ] **Improve Response Diversity:** If needed, explore data augmentation techniques or curate more varied training examples to reduce reliance on specific repetitive phrases learned during initial fine-tuning.

### Comprehensive Evaluation

- [ ] **Implement Quantitative Metrics:** Add code to evaluate the fine-tuned model on the test set using standard metrics (e.g., Perplexity, ROUGE, BLEU).
- [ ] **Expand Qualitative Testing:** Create a diverse test suite with various prompt types, tones, and edge cases to thoroughly assess the model's capabilities and limitations.
- [ ] **Conduct Rigorous Catastrophic Forgetting Tests:** Perform more extensive testing on general knowledge and reasoning tasks to ensure fine-tuning hasn't significantly degraded core capabilities.

### Deployment Readiness & Optimization

- [ ] **Develop and Implement Guardrails:** Design and integrate mechanisms to:
    - Ensure the model stays on-topic (e.g., relevant customer service).
    - Filter potentially harmful or inappropriate inputs/outputs.
    - Validate inputs and outputs for expected formats.
- [ ] **Explore Post-Training Optimization:** Based on deployment requirements (latency, cost, memory), investigate:
    - Merging LoRA adapter weights into the base model.
    - Applying further quantization techniques.
    - Knowledge distillation to potentially create a smaller, faster model.
- [ ] **Add Robust Error Handling:** Implement standard error handling and logging for operational stability.