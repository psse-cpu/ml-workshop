---
layout: center
---

# Mean-square error

- Squaring values also make them positive, and **penalizes bigger errors.**

$$
\frac{1}{m} \sum\limits_{i = 1}^{m}(y_i - \hat{y_i})^2
$$

- Some mathematicians also halve this mean, which is still proportional, for a very cool reason 😉
  $\frac{1}{2m} \sum\limits_{i = 1}^{m}(y_i - \hat{y_i})^2$

|  $y$  | $\hat{y}$  | $\| y - \hat{y}\|$  | $(y - \hat{y})^2$ |
|-------|------------|---------------------|-------------------|
|  4    | 4          | 0                   | 0                 |
|  4    | 3          | 1                   | 1                 |
|  4    | -3         | 1                   | 1                 |
|  4    | 7          | 3                   | 9                 |
|  4    | -8         | 4                   | 16                |