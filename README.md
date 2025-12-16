## License

The contents of this repository (e.g. the Dockerfile and other configuration files)
are licensed under the **BSD 3-Clause License**.

See [LICENSE](./LICENSE) for the full license text.

This project builds on top of the
[`quay.io/jupyter/pytorch-notebook`](https://quay.io/repository/jupyter/pytorch-notebook)
image from the [Jupyter Docker Stacks](https://github.com/jupyter/docker-stacks) project,
which is licensed under the Modified BSD License (BSD 3-Clause).

The resulting Docker image also includes various third-party packages
(e.g. PyTorch, JupyterLab extensions, LangChain, MLflow, Hugging Face libraries, etc.),
each of which is licensed under its respective open-source license
(Apache-2.0, MIT, BSD, etc.). This repository does not change the licenses of
those third-party components; please refer to each upstream project for details.