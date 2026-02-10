# Precog-Task: The Lazy Artist

This repository contains a step-by-step project focused on identifying, evaluating, and mitigating color bias in convolutional neural networks (CNNs). It explores the "Shortcut Learning" phenomenon—where a model, like a **"Lazy Artist"**, learns simple cues (like color) instead of underlying shapes—and uses Sparse Autoencoders (SAEs) for interpretability.

Try to run whenever possible in colab as i havent tested in local environment

## 📁 Directory Structure

The project is organized into several tasks, each corresponding to a specific stage of the challenge:

- **[Task 0](./Task%200/)**: Initial data exploration and understanding of the MNIST dataset.
- **[Task 1](./Task%201/)**: Training a baseline CNN on a color-biased version of MNIST where certain digits are strongly correlated with specific colors.
- **[Task 2](./Task%202/)**: Evaluating the baseline model on "hard" test sets (where color-digit correlations are broken) to quantify the impact of bias.
- **[Task 3](./Task%203/)**: Implementing "Color Penalty" as a de-biasing technique to discourage the model from relying on color features.
- **[Task 4](./Task%204/)**: Implementing "Consistency Loss" (using color jitter and augmentations) to improve model robustness and generalization.
- **[Task 5](./Task%205/)**: Evaluating the adversarial robustness of biased vs. de-biased models using targeted adversarial attacks.
- **[Task 6](./Task%206/)**: Training Sparse Autoencoders (SAEs) on the hidden representations of the CNN to perform feature decomposition and interpretability analysis.

Each task directory contains the relevant Jupyter notebooks and a `weights/` subdirectory for saved model checkpoints.

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or Google Colab

### Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Precog-Task
   ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Linux/macOS
   # venv\Scripts\activate   # Windows
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Project
Launch Jupyter Notebook to explore the tasks:
```bash
jupyter notebook
```
For detailed local setup instructions, see [setup_local.md](./setup_local.md).

## 🛠 Dependencies
The project relies on the following key libraries:
- `torch` & `torchvision`: For deep learning model training and data handling.
- `numpy`: For numerical computations.
- `matplotlib`: For visualization of data and results.
- `notebook`: To run the experiments in an interactive environment.

## 🧩 The Approach

The project follows a systematic approach to model robustness:
1.  **Bias Injection**: We create a "Biased MNIST" where digits and colors are correlated (e.g., all 0s are red, all 1s are green).
2.  **Bias Quantization**: We show that standard CNNs take the "shortcut" of learning color instead of shape, leading to a massive drop in accuracy on unbiased test data.
3.  **Mitigation**: We apply regularization techniques (Color Penalty) and augmentation-based training (Consistency Loss) to force the model to focus on the actual digit shapes.
4.  **Verification**: Using adversarial attacks, we test if the model's decisions are based on robust features.
5.  **Interpretability**: We use Sparse Autoencoders to disentangle the learned features in the hidden layers, aiming to identify specific neurons or units that respond to shape vs. color.