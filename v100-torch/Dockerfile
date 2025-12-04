FROM quay.io/jupyter/pytorch-notebook:cuda12-pytorch-2.6.0

SHELL ["/bin/bash", "-euxo", "pipefail", "-c"]

ENV PIP_NO_CACHE_DIR=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    CONDA_CHANNEL_PRIORITY=strict

RUN mamba install -y -n base -c conda-forge --override-channels \
    jupyter-ai=2.31.7 \
    jupyter-ai-magics=2.31.7 \
    jupyter_scheduler=2.11.0 \
    jupyterlab-lsp=5.2.0 \
    jupyter-lsp=2.2.5 \
    python-lsp-server=1.13.2 \
    r-languageserver=0.3.16 \
    jupyter-collaboration=4.1.2 \
    jupyter_server_ydoc=2.1.2 \
    jupyter_ydoc=3.3.2 \
    jupyter-server-proxy=4.4.0 \
    plotly=6.5.0 \
    jupyter-dash=0.4.2 \
    mlflow=3.6.0 \
    huggingface_hub=1.1.7 \
 && mamba clean -afy

RUN pip install --no-cache-dir --upgrade \
      pip \
      setuptools \
      wheel \
 && pip install --no-cache-dir \
      ai21==4.3.0 \
      langchain==0.3.27 \
      langchain-openai==0.3.35 \
      langchain-anthropic==0.3.22 \
      langchain-aws==0.2.35 \
      langchain-google-genai==2.1.12 \
      langchain-mistralai==0.2.12 \
      langchain-cohere==0.4.6 \
      langchain-ollama==0.3.10 \
      langchain_nvidia_ai_endpoints==0.3.19 \
      gpt4all==2.8.2 \
      qianfan==0.4.12.3 \
 && fix-permissions "${CONDA_DIR}" "/home/${NB_USER}"
