Dataset can be created in the following format


**SFT sequence (Tong's format, what LB-54 trains on):**

```
<|im_start|>system
<|im_end|>
<|im_start|>user
{problem}
Please put your final answer inside `\boxed{}`. For example: `\boxed{your answer}`<|im_end|>
<|im_start|>assistant
{reasoning trace}
</think>
\boxed{answer}<|im_end|>
```


**Eval sequence (what vLLM feeds the model):**

```
<|im_start|>system
<|im_end|>
<|im_start|>user
{problem}
Please put your final answer inside `\boxed{}`. For example: `\boxed{your answer}`<|im_end|>
<|im_start|>assistant
<think>
```




Referenc: https://www.kaggle.com/code/konstantinboyko/01-04-training-with-unsloth-batch-2-epoch-2#Mode-Selection
This notebook got 0.83 score


