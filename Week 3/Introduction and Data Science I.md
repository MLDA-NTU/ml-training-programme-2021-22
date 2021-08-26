# Introduction and Data Science I

## What is Artificial Intelligence, Machine Learning, Data Science, and Deep Learning?

Three levels of AI

- Narrow (ANI): Weak AI, **specializes in 1 task** and can only do that task e.g. facial recognition, play chess, self-driving
- General (AGI): Strong AI, or Human-Level AI, can perform **any intellectual task that a human being can**, including reasoning, abstract thinking, learning and solving new problems 
- Superintelligence (ASI): "**much smarter than the best human brains** in practically every field, including scientific creativity, general wisdom and social skills.”

*Question to ponder: Does AI have, or need to have, consciousness?*

Artificial Intelligence vs Machine Learning

- AI: machine's ability to do something that a human can do → **decision making**
- ML: sub-area of AI, machine learns a pattern in data → **data understanding**

What about Deep Learning?

-  Deep Learning: sub-field of Machine Learning, refers to **neural networks** that have many layers (deep)
- Traditional Machine Learning: algorithms before the rise of neural networks e.g. Support Vector Machine, Histogram of Oriented Gradients

What about Data Science and Data Analytics?

- Both are usually more business-oriented, focusing on finding patterns and insights from data for business decisions
- Data Science: more statistics and machine learning, including building predictive models
- Data Analytics: data collection, visualization, and monitoring

## Careers

Huyen Chip's ML interviews Book: [Chapter 1](https://huyenchip.com/ml-interviews-book/contents/chapter-1.-ml-jobs.html)

Machine Learning jobs:

- Machine learning engineer
- Data scientist
- ML/AI platform engineer
- ML/AI infrastructure engineer
- ML accelerator/hardware engineer
- Framework engineer
- Solution architect
- Developer advocate
- Solutions engineer
- Applications engineer
- Applied research scientist
- Research engineer
- Research scientist

ML Research vs ML Production:

- Research: pushing the boundaries of ML e.g. invent a new Object Detection model architecture. Research can be both in Academia or Industry
- Production: making an ML product e.g. self-driving cars

## Intermediate Python for Machine Learning

### List (and Dictionary) comprehension

```python
pred_error = [-1,2,-3,4,-5]
pred_error_sq = [x**2 for x in pred_error]          # map
positive_error = [x for x in pred_error if x > 0]   # filter

names = ["Adam", "Rosa", "Alice"]
ages = [18, 20, 21]
name_to_age = {name: age for name, age in zip(names, ages)}
```

### Generator

Example from [RealPython](https://realpython.com/introduction-to-python-generators/)

```python
def infinite_sequence():
    num = 0
    while True:
        yield num
        num += 1

for i in infinite_sequence():
    print(i, end=" ")
```

### Other Python features good to know

- Spread operators (`*` and `**`)
- `*args` and `**kwargs`
- Context manager
- Decorator
- Multi-processing / Multi-threading
- Asyncio
- Writing Python modules and packages

## Data Science and Tabular Data

Pandas cheat sheet: [link](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)

Pandas skills

- Read and write csv files
- Understand rows (samples) and columns (features)
- Select data using index and column names (`[]`, `.loc[]`, and `.iloc[]`)
- Filter data with boolean mask
- Understand data via data summary and visualization
- Data transformation: Filter, Map, Reduce
- Combine data with `.concat()` and `.merge()`
- Group data with `.groupby()`
