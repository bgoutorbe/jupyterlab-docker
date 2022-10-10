# Dockerfile to build custom image for jupyter lab server
FROM jupyter/datascience-notebook:python-3.10.6

# jupyterlab extensions
RUN jupyter labextension install --no-build  \
      jupyterlab-theme-toggle

RUN pip install --no-cache-dir \
      jupyterlab-system-monitor==0.8.0 \
      jupytext==1.14.1 \
      jupyterlab-code-formatter==1.5.3 \
      black==22.8.0 \
      isort==5.10.1 \
      jupyter-bokeh==3.0.4 \
      jupyter-dash==0.4.2

# rebuilding jupyterlab
RUN jupyter lab build && jupyter lab clean

# Python modules
RUN pip install --no-cache-dir \
      openpyxl==3.0.10 \
      xlsxwriter \
      numpy==1.23.3 \
      googlemaps==4.6.0 \
      mapclassify==2.4.3 \
      pygeos==0.13 \
      geopy==2.2.0 \
      arcgis==2.0.0 \
      simpledbf==0.2.6 \
      xgboost==1.6.2  \
      lightgbm==3.3.2  \
      torch==1.12.1  \
      torchaudio==0.12.1  \
      torchvision==0.13.1  \
      transformers[torch]==4.22.1

RUN conda install -y geopandas==0.11.1

CMD ["start-notebook.sh", "--NotebookApp.token=''", "--NotebookApp.password=''"]
