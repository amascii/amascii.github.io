---
layout: post
title:  "Haskell Exercises Part 1!"
date:   2020-02-02 15:9:00 +0900
categories: haskell
---



After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/


#### Exercise 1 - Evaluation and prefix notation
Evaluate the following expressions and convert them to the equivalent expression in prefix notation.

{% highlight haskell %}
-- 1
2 ^ 4 - 1

--answer
(-) ((^) 2 4)1
= 15

-- 2
2 * 3 * (5 - 1)

-- answer
(*) 2 ((*) 3 ((-) 5 1))
= 24

-- 3
2 + 1 + 3 / 4

-- answer
(+) 2 ((+) 1 ((/) 3 4))
= 3.75

-- 4
(3 - 1) / (4 + 2)

-- answer
(/) ((-) 3 1) ((+) 4 2)
= 0.33...
{% endhighlight %}

#### Exercise 2 - Data types
```haskell
--answer
rate = 120
:t rate
> rate :: Integer

rate :: Float
> rate :: Float

result = rate * 3.40
:t result
> result :: Float
```

#### Exercise 3 - Scope
Evaluate and find x.

```haskell
-- 1
a = 1
x = a + 1

-- answer
= 2

-- 2
a = 1
x = a + 1 where a = 0

-- answer
= 1

-- 3
a = 1
x = a + 1 where a = a + 2 where a = 3

-- answer
= 6

-- 4
a = 1
x = a + let a = 2 in a + 1

-- answer
= 4
```

#### Exercise 4 - Functions
Evaluate the following expressions.

```haskell
--1
f x = x * x
f 4

-- answer
= 16

-- 2
f = (+)
f 2 1

-- answer
= 3

-- 3
f = \x -> x * x
f 2

-- answer
= 4

-- 4
f g = \x y -> 1 + g x y
(f (+)) 2 1

-- answer
= 4
```

#### Exercise 5 - Currying
Evaluate and answer the questions.

1.
```haskell
f x y = x * y  
-- Q: what is f? 
-- A: a binary function that multiplies two numbers

g = f 2
-- Q: what is g?
-- A: f with only the first argument defined

g 3

-- answer
= 6
```

2.
```haskell
p x y z = x + y - z 
-- Q: what is p?
-- A: a ternary function

p 5 4
-- Q: what is returned?
-- A: an error, not enough arguments
-- A: a unary function that subtracts the given parameter from 9

q = p 1
-- what is q?
-- A: a binary function that adds its first parameter to 1 then subtract the second parameter

r = q 2
-- what is r?
-- A: a unary function that subtracts the given parameter from 3

r 3

-- answer
= 0
```

#### Exercise 6 - Contracts
Give a possible signature for the following functions.
```haskell
-- 1
f x y = x == y

-- answer
f :: (Eq a) => a -> a -> Bool

-- 2
g x y = x <= y

-- answer
g :: (Ord a) => a -> a -> Bool
```

#### Exercise 7 - Lists
Evaluate the following expressions.
```haskell
1:[]            -- 1 [1]
1:[True]        -- 2 error
[1] : [[2],[2]] -- 3 [[1],[2],[2]]
[0,'a','b']     -- 4 error
'h':"ello"      -- 5 "hello"
"h":"ello"      -- 6 error
[]:[]:[]        -- 7 [[],[]]
```

#### Exercise 8 - Lists and signatures
Write the signature of the list accessor function `tail`.
```haskell
tail :: [a] -> [a]
```

#### Exercise 9 - Tuples
Evaluate the following expressions.
```haskell
1:[2,3]           -- 1 [1,2,3] 
1:(2,3)           -- 2 error (tuples are immutable)
(,) 1 2           -- 3 (1,2)
(,) 1 2 3         -- 4 error
(1,2,False)       -- 5 (1,2,False)
[(1,2),(9,False)] -- 6 error (elements of list can't have different types)
([1,2],[True])    -- 7 ([1,2],[True]) (anything goes in tuples)
```

#### Exercise 10 - Tuple and signatures
Write the signature of the tuple accessor function `snd`.
```haskell
snd :: (a, b) -> b
```

## Report
```haskell
[1,2,3] -> [[1,2,3], [1,3,2], ...]
perm
```
