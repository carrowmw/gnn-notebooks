# Dockerfile for running GNN notebooks in Test-3
# Supports PyTorch, PyTorch Geometric, DGL, and Jupyter

FROM python:3.11-slim

# Set environment variables
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_NO_CACHE_DIR=1 \
    PIP_DISABLE_PIP_VERSION_CHECK=1

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Change this line (PyTorch):
RUN pip install torch==2.5.1 --index-url https://download.pytorch.org/whl/cu121

# Change this line (PyTorch Geometric):
RUN pip install torch-geometric==2.6.1 \
    torch-scatter \
    torch-sparse \
    torch-cluster \
    torch-spline-conv \
    -f https://data.pyg.org/whl/torch-2.5.1+cu121.html

# Install Jupyter and common data science packages
# Pin httpx<0.28 to avoid compatibility issue with JupyterLab extension manager
RUN pip install \
    "httpx<0.28" \
    jupyter==1.1.1 \
    jupyterlab==4.2.5 \
    notebook==7.2.2 \
    numpy==1.26.4 \
    pandas==2.2.3 \
    matplotlib==3.10.1 \
    networkx==3.4.2 \
    scikit-learn==1.5.2 \
    scipy==1.13.1 \
    seaborn==0.13.2 \
    tqdm==4.67.0

# Copy the Test-3 directory contents
COPY . /app/

# Expose Jupyter port
EXPOSE 8889

# Set up Jupyter configuration
RUN mkdir -p /root/.jupyter && \
    echo "c.NotebookApp.ip = '0.0.0.0'" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.open_browser = False" >> /root/.jupyter/jupyter_notebook_config.py

# Default command: start Jupyter Lab (uses JUPYTER_TOKEN env var if set)
CMD ["sh", "-c", "jupyter lab --ip=0.0.0.0 --port=8889 --no-browser --allow-root --ServerApp.token=${JUPYTER_TOKEN:-''}"]
