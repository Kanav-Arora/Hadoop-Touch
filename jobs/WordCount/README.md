# Word Count

## Goal

Count the number of occurrences of each word in a given text file.

## Why This Matters

The Word Count program is the "Hello World" of Hadoop MapReduce. It introduces the core concepts of distributed data processing — splitting data, mapping key-value pairs, and reducing them to aggregated results.

## How It Works

### 1. Input

A text file containing any kind of content — books, articles, logs, or any raw text.

### 2. Map Phase

- Each line is split into words.
- For each word, the Mapper emits a key-value pair
```
(word, 1)
```

### 3. Shuffle & Sort Phase

Hadoop groups all identical keys (words) together across the entire dataset.

### 4. Reduce Phase

For each key, the Reducer sums up the values.
Output is
```
(word, total_count)
```