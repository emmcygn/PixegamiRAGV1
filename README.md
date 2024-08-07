Langchain RAG Tutorial
Install Dependencies
Install ONNX Runtime (specific to macOS and Windows):

macOS Users: To address current challenges installing onnxruntime via pip, first install it using Conda:
bash
Copy code
conda install onnxruntime -c conda-forge
For additional help, refer to this thread.

Windows Users: Follow the guide here to install the Microsoft C++ Build Tools, making sure to complete all steps and set the environment variable path.
Create and Activate a Virtual Environment:

Create a virtual environment:
bash
Copy code
python -m venv myenv
Activate the virtual environment:

macOS/Linux:
bash
Copy code
source myenv/bin/activate
Windows:
bash
Copy code
myenv\Scripts\activate
Install Python Dependencies:

Install dependencies listed in the requirements.txt file:
bash
Copy code
pip install -r requirements.txt
Install Markdown Dependencies:

Install additional markdown dependencies:
bash
Copy code
pip install "unstructured[md]"
Create the Database
Generate the Chroma DB by running:

bash
Copy code
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

This guide includes installation steps, environment configuration, and usage instructions tailored to your project.

> You'll also need to set up an OpenAI account (and set the OpenAI key in your environment variable) for this to work.

Here is a step-by-step tutorial video: [RAG+Langchain Python Project: Easy AI/Chat For Your Docs](https://www.youtube.com/watch?v=tcqEUSNCn8I&ab_channel=pixegami).
