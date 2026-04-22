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

### Examples

**FULL SFT STRING**

<|im_start|>system
<|im_end|>
<|im_start|>user
In Alice's Wonderland, a secret bit manipulation rule transforms 8-bit binary numbers. Given examples: 00001111 -> 11110000. Apply the rule to 10100101.
Please put your final answer inside `\boxed{}`. For example: `\boxed{your answer}`<|im_end|>
<|im_start|>assistant
The rule appears to flip every bit. 00001111 flipped is 11110000. Applying to 10100101 gives 01011010.
</think>
\boxed{01011010}<|im_end|>

**FULL EVAL STRING**

<|im_start|>system
<|im_end|>
<|im_start|>user
In Alice's Wonderland, a secret bit manipulation rule transforms 8-bit binary numbers. Given examples: 00001111 -> 11110000. Apply the rule to 10100101.
Please put your final answer inside `\boxed{}`. For example: `\boxed{your answer}`<|im_end|>
<|im_start|>assistant
<think>



Referenc: https://www.kaggle.com/code/konstantinboyko/01-04-training-with-unsloth-batch-2-epoch-2#Mode-Selection
This notebook got 0.83 score


