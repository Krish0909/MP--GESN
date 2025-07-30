# Enhanced Echo State Network V2 (MP-GESN)

> Multi-Perspective Graph Echo State Network with Attention and Learnable Projections

This repository contains an advanced implementation of an Echo State Network (ESN) tailored for temporal signal modeling. The architecture extends traditional ESNs with:

- Multi-timescale sub-reservoirs
- Multi-head attention across reservoir outputs
- A learnable projection mechanism to downstream output space
- PyTorch-based modular design for fast prototyping and extensibility

---

## 🧠 Features

- **Sub-Reservoir Decomposition**: Multiple smaller ESNs capture dynamics at varied time scales.
- **Multi-Head Attention**: Learnable attention layers enhance the expressiveness of readouts from each reservoir.
- **Reservoir Dropout**: Regularization on hidden states.
- **Flexible Configuration**: Set number of sub-reservoirs, spectral radius, leak rate, etc.
- **Training History**: Logs loss curves across epochs for debugging and visualization.

---

## 🗂️ Project Structure

enhanced_esn/
│
├── model.py # Main MP-GESN model definition
├── train.py # Training loop with support for Optuna & visualization
├── utils.py # Utility functions for logging, reproducibility
├── config.yaml # Centralized configuration file
├── requirements.txt # Dependencies
└── README.md # You're here!


---

## ⚙️ Installation

git clone https://github.com/Krish0909/enhanced-esn-v2.git
cd enhanced-esn-v2
pip install -r requirements.txt
🏃 Usage

To train the model:

python train.py --config config.yaml
You can also launch hyperparameter optimization via Optuna (if enabled in config):

python train.py --optuna
⚒ Configuration (config.yaml)

RESERVOIR_SIZE: Number of neurons per sub-reservoir
NUM_SUB_RESERVOIRS: Number of time scales used
LEAK_RATE: Governs memory in ESN dynamics
SPECTRAL_RADIUS: Controls stability
DROPOUT: Dropout applied to reservoir states
USE_ATTENTION: Whether to apply multi-head attention
OUTPUT_SIZE: Dimensionality of final task output
📊 Example Logs

Loss curves are tracked via defaultdict and stored for inspection. Add custom metrics to train.py as needed.

🧪 Tests & Evaluation

You can write evaluation scripts using the forward API. The model returns:

Final prediction
Raw concatenated reservoir states
Attention outputs (if enabled)
🤝 Contributing

Pull requests are welcome! If you’d like to contribute new features, optimizations, or use-cases (e.g., EEG decoding, stock prediction), feel free to fork the repo and propose your changes.

📜 License

MIT License © Krishnan Venkiteswaran


---

Let me know if you'd like me to auto‑generate a `requirements.txt` or add usage examples for a specific dataset (like EEG, time series, etc.).
