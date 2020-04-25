class notes: 04/22/2020

# deep learning
 - especially useful in dealing with "unstructured data"
   - images: relationships with adjacent pixels, sure, but not as structured as our tables from before
   - other examples: audio, video, natural language processing (NLP)
 - input:
   - convert image into matrix (e.g., `numpy`)
 - convolution: feature extraction method where
   - not really understood why this works so well
   - when modifying
 - batch normalization: used to level the playing field for images
 - rectified linear unit (ReLU)
   - function that gives the max of 0 or x: $f(x)=x^+=\max(0,x)$
   - helps us extract the most important information from our features
 - max pooling: sliding window (no overlap) that takes max value from each window
   - these functions essentially act as aggregation functions
 - dropout layer: randomly drop 1/2 of signals in this layer (to prevent overfitting)
 - epoch: training iterations
   - curve of training accuracy versus training loss: would also see test accuracy (start to decrease) and test loss (start to increase) at point of overfitting
 - loss function
   - cross entropy: $H(p,q)=-\sum\limits_{x\in X}p(x)\log(q(x))$

# issues with using deep learning
 - can be quite prone to overfitting
 - would you use with rectangular data?
   - maybe (e.g., h2o automl), but more likely than not would guess other models could outperform
 - training can be very computationally intensive (but unsure about how intensive using a model is)
 - lose interpretability when using neural networks, even though prediction improves

# keras and tensorflow
 - application program interface (API): tools to interact with other software
 - keras is essentially an API for tensorflow

# sequential API
 - create a model, and specify its layer configurations via list:
   ```{python}
   model = tf.keras.Sequential([
   # densely-connected layer w/ 64 units
   layers.Dense(64, activation='relu', input_shape=(32,)),
   # another of the same
   layers.Dense(64, activation='relu'),
   #output layer w/ 10 output units
   layers.Dense(10)])
   
   # compile model
   model.compile(optimizer=tf.keras.optimizers.Adam(0.01),
   loss=tf.keras.losses.CategoricalCrossentropy(from_logits=True), # indicates this is classification
   metrics=['accuracy'])
   ```
 - can fit model based on data using fit method: `model.fit(data, labels, epochs=10, batch_size=32, validation_data=(val_data, val_labels))`
   - can also use keras datasets to combine `labels`, `data`, and `batch_size`:
   ```
   dataset = tf.data.Dataset.from_tensor_slices((data, labels))
   dataset = dataset.batch(32)
   
   model.fit(dataset, epochs=10)
   ```
 - more advanced uses of keras/tensorflow: functional API and model subclassing

# regularization
 - also has $L_1$ & $L_2$ regularization, just like linear regression
 - $\beta$ values are coefficients or "weights" for each of $p$ features
   - sum all weights, and penalty is proportional to this
   - $L_1$ penalty proportional to $\sum\limits_{j=1}^p ||\beta_j||_1$
   - $L_2$ penalty proportional to $\sum\limits_{j=1}^p ||\beta_j||^2_2$
 - essentially, these regularization methods help to restrict values of weights
   - in deep learning, can apply regularization to "kernal matrix" and "bias vector"

# saving your work
 - can save weights of model to use them later: `model.save_weights('./weights/my_model')`
   - load later: `model.load_weights('./weights/my_model')`
