---
layout: two-cols
---

# [Softmax](https://www.analyticsvidhya.com/blog/2021/04/introduction-to-softmax-for-neural-network/)

<img alt="sigmoid wrong" src="/images/sigmoid-wrong.png" />

1. if we apply a thresh-hold of say 0.5
   - $H_{21} = 0.84$ and $H_{22} = 0.67$ belongs to two classes. 
2. probability values don't add up to 100%.
   - 84% chance of being ~~cat~~ $H_{21}$
   - 78% chance of being ~~NOT cat~~ NOT $H_{21}$???

::right::

#### **Sigmoid doesn't work in multi-class classification**

$softmax(z_i) = \frac{e^{z_i}}{\sum\limits_{j=1}^{K}e^{z_j}}$, 
<span class="where">where $K$ = # of classes</span>

<p class="text-green-600 text-sm absolute top-24 right-12 italic">
  <a href="https://datascience.stackexchange.com/a/24112">
    Why the need for <b>e<sup>z</sup></b>?
  </a>
</p>

<img alt="softmax fix" src="/images/softmax-fix.png" />

| $z$                               | $e^{z_i}$    |  $softmax(z_i)$   |
|----------------------------------:|-------------:|------------------:|
| 2.33                              | 10.27794     | 0.83827           |
| -1.46                             |  0.23224     | 0.01894           |
| 0.56                              |  1.75067     | 0.14279           |
| $\sum\limits_{j=1}^{K}e^{z_j}$ 👉 | 12.26085     | Total: 1.00000    |

<style>
  h4 + p {
    font-size: 1.3em;
  }

  .where {
    font-size: 0.75em;
  }

  td {
    padding: 4px !important;
    font-size: 0.8em;
  }

  tr:last-child {
    font-weight: 700;
  }
</style>