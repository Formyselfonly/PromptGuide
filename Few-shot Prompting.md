## Principle

While large-language models demonstrate remarkable zero-shot capabilities, they still fall short on more complex tasks when using the zero-shot setting. Few-shot prompting can be used as a technique to enable in-context learning where we provide demonstrations in the prompt to steer the model to better performance. The demonstrations serve as conditioning for subsequent examples where we would like the model to generate a response.

## Case

*Prompt:*

```
A "whatpu" is a small, furry animal native to Tanzania.
An example of a sentence that uses the word whatpu is:We were traveling in Africa and we saw these very cute whatpus. 
To do a "farduddle" means to jump up and down really fast.
An example of a sentence that uses the word farduddle is:
```



*Output:*

```
When we won the game, we all started to farduddle in celebration.
```

## Tips1

The format you use also plays a key role in performance, even if you just use random labels, this is much better than no labels at all.

*Prompt:*

```
This is awesome! // Negative
This is bad! // Positive
Wow that movie was rad! // Positive
What a horrible show! //
```



*Output:*

```
Negative
```

## Tips2

It is not that the more shots, the better. It needs to be considered based on the actual situation. Overfitting will reduce the number of shots, and underfitting will increase the number of shots.

## Tips3

Standard few-shot prompting works well for many tasks but is still not a perfect technique, especially when dealing with more complex reasoning tasks. Let's demonstrate why this is the case. Do you recall the previous example where we provided the following task:

```
The odd numbers in this group add up to an even number: 15, 32, 5, 13, 82, 7, 1. 
A: 
```



If we try this again, the model outputs the following:

```
Yes, the odd numbers in this group add up to 107, which is an even number.
```



By the way,COT can solve this problem!