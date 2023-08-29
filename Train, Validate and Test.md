- Training data are collections of examples or samples that are used to 'teach' or 'train the machine learning model. The model uses a training data set to understand the patterns and relationships within the data, thereby learning to make predictions or decisions without being explicitly programmed to perform a specific task.

- In contrast, validation datasets contain different samples to evaluate trained ML models. It is still possible to tune and control the model at this stage. Working on validation data is used to assess the model performance and fine-tune the parameters of the model. This becomes an iterative process wherein the model learns from the training data and is then validated and fine-tuned on the validation set. A validation dataset tells us how well the model is learning and adapting, allowing for adjustments and optimizations to be made to the model's parameters or hyperparameters before it's finally put to the test.

- Finally, a test data set is a separate sample, an unseen data set, to provide an unbiased final evaluation of a model fit. The inputs in the test data are similar to the previous stages but not the same data. The test data set mirrors real-world data the machine learning model has never seen before. Its primary purpose is to offer a fair and final assessment of how the model would perform when it encounters new data in a live, operational environment.

- Testing is not data validation. Testing is much more involved than performing basic data validation. Since data can drive system functionality, it is important to perform data validation and testing in tandem. The data may look correct, but that does not mean the system is functioning as expected.