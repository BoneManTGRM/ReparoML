# 🧠 ReparoML — Energy-Bounded Self-Repair in PyTorch

**Author:** Cody R. Jenkins — Open Science Reparodynamics Initiative  
**Version:** v1.0 (October 2025)  

ReparoML demonstrates energy-bounded self-repair using the Targeted Gradient Repair Mechanism (TGRM).  
It compares full retraining versus bounded repair updates on degraded neural networks.

## 🚀 Quickstart

```bash
pip install -r requirements.txt
python experiments/run_mnist_cnn.py --phase train --out outputs/mnist_baseline
python experiments/run_mnist_cnn.py --phase fault --in_ckpt outputs/mnist_baseline/best.pt --out outputs/mnist_faults
python experiments/run_mnist_cnn.py --phase repair --in_ckpt outputs/mnist_faults/faulted.pt --out outputs/mnist_repair
python experiments/plot_runs.py --dirs outputs/mnist_baseline outputs/mnist_faults outputs/mnist_repair
