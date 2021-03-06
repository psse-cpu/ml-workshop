---
layout: two-cols
---

# Building a Binary Classifier

It's not much different from linear regression.  We just change a couple of things:

1. we now **add** an activation function to our **NEURON** 
   - _actually ALL neurons in the entire layer_ will have the **same activation function**
   - only that right now, our layer has only one neuron
    ```py {4|all}
    keras.layers.Dense(
        units=1, 
        input_shape=[2], 
        activation='sigmoid' # 👈 ADD THIS
    )
    ```

2. change the loss function
   ```diff
   - loss=keras.losses.MeanSquaredError(),
   + loss=keras.losses.BinaryCrossentropy(),
   ```

::right::

3. <twemoji-pencil /> a <mdi-function /> to turn $\lt 50\%$ probability to $0$, $\ge 50\%$ to $1$
    ```py
    def predict(normalized_input):
        # model.predict returns 0 to 1, due to sigmoid
        return model.predict(normalized_input) >= 0.5
    ```

4. predict using your shiny new function
    ```py
    predict(np.array([[38, 75]]))
    ```

### Full example (NN part only)

```py {5|9|all}
model = keras.Sequential([
    keras.layers.Dense(
        units=1, 
        input_shape=[2], 
        activation='sigmoid' # string, not object
    )
])
model.compile(  # note lwoercase 👇 `e`
    loss=keras.losses.BinaryCrossentropy(),
    optimizer=keras.optimizers.SGD()
)
```

<style>
  .slidev-code {
    overflow: hidden;
  }
</style>