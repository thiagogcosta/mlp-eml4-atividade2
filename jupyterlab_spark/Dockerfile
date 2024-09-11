FROM jupyter/all-spark-notebook:latest

RUN pip install xgboost

COPY jupyter_notebook_config.py /home/jovyan/.jupyter/jupyter_notebook_config.py

COPY train_test_ml_model_certo.ipynb /home/jovyan/work/train_test_ml_model_certo.ipynb

COPY adult-preprocessed.data /home/jovyan/work/adult-preprocessed.data

CMD ["start-notebook.sh", "--NotebookApp.token=''"]