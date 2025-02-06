# LLMParadox
Codes for NAACL 2025 Paper "LLM The Genius Paradox: A Linguistic and Math Expert’s Struggle with Simple Word-based Counting Problems"
### Datasets
We release four word-based counting tasks in folder `./datasets`: 1) char occur, 2) substring occur, 3) word len, and 4) distinct char.
You can load data line-by-line with the following code:
```python
import json 

for line in open('./datasets/char_occur.jsonl'):
    instance = json.loads(line)
```
Here is an example instance for `char occur` task:
```python
{
    "question": "How many m's in the word \"Missourianism\"?", 
    "word": "Missourianism", 
    "question_id": 0, 
    "answer": "1"
}
```
which contains the question for LLMs, the queried word, the question id, and the true answer.

### Evaluation
Once you get responses (e.g., gen_file.jsonl) from LLMs on four counting tasks, you can evaluate accuracy with the following command:
```shell
python evaluate.py --gen-file gen_file.jsonl --task char_occur
```

### Citation
Please cite this paper is you find this work helpful
```shell
@article{xu2024llm,
  title={LLM The Genius Paradox: A Linguistic and Math Expert's Struggle with Simple Word-based Counting Problems},
  author={Xu, Nan and Ma, Xuezhe},
  journal={arXiv preprint arXiv:2410.14166},
  year={2024}
}
```
