# Langchain RAG Tutorial

## Install Dependencies

1. **Install ONNX Runtime** (specific to macOS and Windows):
    - **macOS Users**: To address challenges installing `onnxruntime` via pip, first install it using Conda:

    ```bash
    conda install onnxruntime -c conda-forge
    ```

    For additional help, refer to this [thread](https://github.com/microsoft/onnxruntime/issues/11037).

    - **Windows Users**: Follow the guide [here](https://github.com/bycloudai/InstallVSBuildToolsWindows?tab=readme-ov-file) to install the Microsoft C++ Build Tools. Make sure to complete all steps and set the environment variable path.

2. **Create and Activate a Virtual Environment**:
    - Create a virtual environment:

    ```bash
    python -m venv myenv
    ```

    - Activate the virtual environment:
        - **macOS/Linux**: 

        ```bash
        source myenv/bin/activate
        ```

        - **Windows**: 

        ```bash
        myenv\Scripts\activate
        ```

3. **Install Python Dependencies**:
    - Install dependencies listed in the `requirements.txt` file:

    ```bash
    pip install -r requirements.txt
    ```

4. **Install Markdown Dependencies**:
    - Install additional markdown dependencies:

    ```bash
    pip install "unstructured[md]"
    ```

## Create the Database

Generate the Chroma DB by running:

```bash
python create_database.py
Query the Database
Query the Chroma DB with:

bash
Copy code
python query_data.py "How does Alice meet the Mad Hatter?"
Ensure you have set up an OpenAI account and added your OpenAI API key to your environment variables for this to work.

Environment Setup Tweaks
Conda Setup
To set up the Conda environment:

json
Copy code
{
  "name": "myenv",
  "packages": [
    "python=3.12",
    "pip"
  ],
  "commands": [
    "pip install -r requirements.txt"
  ]
}
LLVM Configuration (macOS)
For LLVM configuration on macOS:

bash
Copy code
brew install llvm
export PATH=/usr/local/opt/llvm/bin:$PATH
export LDFLAGS="-L/usr/local/opt/llvm/lib"
export CPPFLAGS="-I/usr/local/opt/llvm/include"
export PKG_CONFIG_PATH="/usr/local/opt/llvm/lib/pkgconfig"
Zsh Configuration
Add the following to your .zshrc file:

bash
Copy code
export PATH=$HOME/.local/bin:$PATH
export PATH=$PATH:/usr/local/bin
Additional Resources
Here is a step-by-step tutorial video: RAG+Langchain Python Project: Easy AI/Chat For Your Docs.
