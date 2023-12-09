# DeepLProject
Group name: Neural Net Ninjas <br>
Group members: Emmer Marcell (DL55DP), Gedeon Máté Károly (HIIMNO), Kiss Csaba (B73BSA) <br>
Challenge: https://www.kaggle.com/competitions/kaggle-llm-science-exam <br> <br>
Documentation:
- scientific-question-answering-using-machine-learning-techniques.pdf
Colab Notebooks:
- data_viz.ipynb: Colab Notebook for data visualization
- embedding_approach.ipynb: The first notebook for building and evaluating the model. The evaluation metric on the test set is MAP@3=0.423.
- context-creation.ipynb: A notebook that creates a context element for each question in the dataset, turning it into an "open-book exam".
- training-an-open-book-model.ipynb: The second notebook for building and evaluation the model, now with the open-book approach using the dataset created in the context-creation notebook. It uses the Huggingface Trainer API and Weights & Biases for hyperparameter tuning and logging. This method reaches an evaluation metric of MAP@3=0.800 on the test set with the following training arguments:

| Parameter                       | Value                       |
|----------------------------------|-----------------------------|
| num_train_epochs                 | 50                          |
| learning_rate                    | 3.868708800630949e-05      |
| weight_decay                     | 0.03                        |
| warmup_ratio                     | 0                           |
| gradient_accumulation_steps      | 4                           |
| per_device_train_batch_size      | 1                           |
| per_device_eval_batch_size       | 2                           |
| overwrite_output_dir             | True                        |
| fp16                             | True                        |
| logging_steps                    | 25                          |
| evaluation_strategy              | 'steps'                     |
| eval_steps                       | 25                          |
| save_strategy                    | 'steps'                     |
| save_steps                       | 25                          |
| load_best_model_at_end           | True                        |
| metric_for_best_model            | 'map@3'                     |
| lr_scheduler_type                | 'cosine'                    |
| save_total_limit                 | 2                           |

Running either embedding_approach.ipynb or training-an-open-book-model.ipynb is enough to both train and evaluate the models.

