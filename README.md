```markdown
# Data Analysis and Question Answering Pipeline

This repository contains a Python notebook, **`final.ipynb`**, designed for data analysis and running a question answering (QA) pipeline. You can execute this notebook either locally on your machine or in Google Colaboratory.

## Prerequisites

* **Python 3.10.6** is required to run this notebook.

## Running Locally

Follow these steps to set up your local environment:

### 1. Install Python 3.10.6

* **Windows:**
    1.  Go to the official Python downloads page: [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)
    2.  Look for the specific release: "Python 3.10.6".
    3.  Download the appropriate installer for your system (either 64-bit or 32-bit).
    4.  Run the installer. **Make sure to check the box that says "Add Python to PATH"** during the installation process.
    5.  Open Command Prompt and verify the installation by running:
        ```bash
        python --version
        ```
        You should see `Python 3.10.6` in the output.

* **macOS:**
    1.  The easiest way to manage multiple Python versions on macOS is using a tool like **pyenv**. If you don't have it, you can install it using Homebrew:
        ```bash
        brew update
        brew install pyenv
        ```
        Follow the instructions that `brew` provides to add `pyenv` to your shell configuration (usually by adding a few lines to your `.bashrc`, `.zshrc`, or `.profile` file). Restart your terminal after making these changes.
    2.  Once `pyenv` is installed, install Python 3.10.6:
        ```bash
        pyenv install 3.10.6
        ```
    3.  Navigate to the repository directory in your terminal:
        ```bash
        cd path/to/your/repository
        ```
    4.  Set the local Python version for this project:
        ```bash
        pyenv local 3.10.6
        ```
    5.  Verify the Python version in this directory:
        ```bash
        python --version
        ```
        You should see `Python 3.10.6`.

### 2. Create and Activate a Virtual Environment

It's highly recommended to use a virtual environment to isolate the project dependencies.

* **Windows:**
    1.  Open Command Prompt, navigate to the repository directory:
        ```bash
        cd path/to/your/repository
        ```
    2.  Create a virtual environment named `.venv`:
        ```bash
        python -m venv .venv
        ```
    3.  Activate the virtual environment:
        ```bash
        .venv\Scripts\activate
        ```
        Your command prompt should now be prefixed with `(.venv)`.

* **macOS:**
    1.  Open Terminal, navigate to the repository directory:
        ```bash
        cd path/to/your/repository
        ```
    2.  Create a virtual environment named `.venv`:
        ```bash
        python -m venv .venv
        ```
    3.  Activate the virtual environment:
        ```bash
        source .venv/bin/activate
        ```
        Your terminal prompt should now be prefixed with `(.venv)`.

### 3. Run the Python Notebook

1.  Ensure your virtual environment is activated.
2.  Open your preferred Jupyter Notebook environment (e.g., Jupyter Notebook, JupyterLab).
3.  Navigate to the repository directory and open the file **`final.ipynb`**.
4.  **Run all cells in the notebook sequentially.** The notebook is designed to automatically install any necessary Python packages using `pip` as it executes.
5.  Upon successful execution, the notebook will:
    * Generate data analysis figures.
    * Run the QA pipeline on 500 questions and passages.
    * Output the generated answers.

## Running in Google Colaboratory

Follow these steps to run the notebook in Google Colab:

### 1. Open the Notebook in Google Colab

1.  Go to [https://colab.research.google.com/](https://colab.research.google.com/).
2.  You can either upload the **`final.ipynb`** file from your local machine or open it directly from GitHub by selecting "GitHub" in the "File" menu and pasting the repository URL.

### 2. Specify Python Version

1.  In the Colab notebook, open a new code cell.
2.  Execute the following commands to specify Python 3.10.6:
    ```python
    import sys
    if sys.version_info < (3, 10, 6):
        print("Warning: Your Python version is older than 3.10.6. Attempting to switch...")
        import subprocess
        try:
            subprocess.run(['sudo', 'apt-get', 'update'], check=True)
            subprocess.run(['sudo', 'apt-get', 'install', 'python3.10'], check=True)
            subprocess.run(['sudo', 'update-alternatives', '--install', '/usr/bin/python3', 'python3', '/usr/bin/python3.10', '1'], check=True)
            subprocess.run(['sudo', 'update-alternatives', '--config', 'python3'], check=True, input=b'1\n') # Select python3.10
            import sys
            print(f"Switched to Python {sys.version_info.major}.{sys.version_info.minor}.{sys.version_info.micro}")
        except Exception as e:
            print(f"Error switching Python version: {e}")
            print("Please ensure Python 3.10.6 is available in the Colab environment.")
    else:
        print(f"Using Python {sys.version_info.major}.{sys.version_info.minor}.{sys.version_info.micro}")
    ```
    **Note:** This attempts to install and switch Python versions. Colab environments can be dynamic, and this might require adjustments or might not always be successful. Verify the Python version after running this cell.

### 3. Run All Cells

1.  Once the **`final.ipynb`** notebook is open and the Python version is (ideally) set, simply go to the "Runtime" menu in Colab and select "Run all".
2.  The notebook will automatically install any necessary Python packages using `pip` as it executes.
3.  Upon successful execution, the notebook will:
    * Generate data analysis figures (which will be displayed within the Colab notebook).
    * Run the QA pipeline on 500 questions and passages.
    * Output the generated answers within the notebook.

## Expected Output

After successfully running all cells in **`final.ipynb`**, you should observe:

* Generated plots and visualizations related to the data analysis.
* Output from the QA pipeline, displaying answers generated for the 500 provided questions based on the corresponding passages.

## Troubleshooting

* **Local Environment:** If you encounter issues, double-check that you have Python 3.10.6 installed and that your virtual environment is activated. Ensure that `pip` is up-to-date within your virtual environment:
    ```bash
    pip install --upgrade pip
    ```
* **Google Colab:** If package installation fails, ensure that Colab has internet access. If you encounter Python version issues, you might need to restart the runtime and try the Python version switching code again.

Enjoy exploring the data analysis and question answering pipeline using **`final.ipynb`**!
```