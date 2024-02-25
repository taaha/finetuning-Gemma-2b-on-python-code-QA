# finetuning Gemma 2b on python code QA

Gemma 2 billion was finetuned on a dataset of [25k python codes](https://huggingface.co/datasets/flytech/python-codes-25k)

For the following question
### write code to find the most frequent element in the list

The following replies were given

### Model before training
```
def most_frequent(lst):
    if len(lst) == 0:
        return None
    else:
        max_count = 0
        max_element = None
        for i in lst:
            if lst.count(i) > max_count:
                max_count = lst.count(i)
                max_element = i
        return max_element
```

### Model after training
```
from collections import Counter
def find_most_frequent_element(list):
    return Counter(list).most_common(1)[0][0]
```

As it can be seen, trained model generates more efficient and elegant code
