# Local Environment Setup Guide

Follow these steps to set up a local Python environment to run your Colab notebooks.

### 1. Prerequisites
Ensure you have Python installed on your system. You can check by running:
```bash
python3 --version
```

### 2. Create a Virtual Environment
It is recommended to use a virtual environment to keep your dependencies organized.
```bash
python3 -m venv venv
```

### 3. Activate the Virtual Environment
- **Linux/macOS**:
  ```bash
  source venv/bin/activate
  ```
- **Windows**:
  ```bash
  venv\Scripts\activate
  ```

### 4. Install Dependencies
Install the required packages using the provided `requirements.txt`:
```bash
pip install -r requirements.txt
```

### 5. Launch Jupyter Notebook
Run the following command to start the Jupyter server:
```bash
jupyter notebook
```
This will open a browser window where you can navigate to your `.ipynb` files and run them.

### GPU Support (Optional)
If you have an NVIDIA GPU and want to use it locally, you may need to install the CUDA-enabled version of PyTorch. Visit [pytorch.org](https://pytorch.org/) for specific installation commands based on your OS and CUDA version.
