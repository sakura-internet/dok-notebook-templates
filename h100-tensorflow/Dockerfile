FROM quay.io/jupyter/tensorflow-notebook:cuda-tensorflow-2.19.0

SHELL ["/bin/bash", "-euxo", "pipefail", "-c"]

ENV PIP_NO_CACHE_DIR=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    CONDA_CHANNEL_PRIORITY=strict

RUN mamba install -y -n base -c conda-forge --override-channels \
    jupyter-ai=2.31.7 \
    jupyter-ai-magics=2.31.7 \
    jupyter_scheduler=2.11.0 \
    jupyterlab-lsp=5.2.0 \
    jupyter-lsp=2.2.6 \
    python-lsp-server=1.14.0 \
    r-languageserver=0.3.16 \
    jupyter-collaboration=4.2.0 \
    jupyter_server_ydoc=2.2.0 \
    jupyter_ydoc=3.3.3 \
    jupyter-server-proxy=4.4.0 \
    plotly=6.5.0 \
    jupyter-dash=0.4.2 \
    mlflow=3.8.0 \
    huggingface_hub=1.2.3 \
 && mamba clean -afy

RUN pip install --no-cache-dir --upgrade \
      pip==25.3 \
      setuptools==80.9.0 \
      wheel==0.45.1 \
 && pip install --no-cache-dir \
      protobuf==5.29.4 \
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
      uv==0.9.18 \
 && fix-permissions "${CONDA_DIR}" "/home/${NB_USER}"
