# 🧠 Neural Network From Scratch

A **fully implemented neural network** built from scratch to classify handwritten digits (MNIST) with **interactive visualization** and **live learning capabilities**.

---

## 🎯 What This Does

- ✅ **Trains a 2-layer neural network** from scratch (no frameworks, pure NumPy)
- ✅ **Visualizes the entire learning process** — see neurons activate, weights update, backpropagation flow
- ✅ **Interactive drawing interface** — draw digits and watch the model predict in real-time
- ✅ **Live feedback learning** — correct wrong predictions to trigger backpropagation and improve the model

---

## 🏗️ Architecture

```
Input Layer (784)
    ↓
Hidden Layer (64 neurons, ReLU)
    ↓
Output Layer (10 neurons, Softmax)
    ↓
Predictions (0-9)
```

| Component | Details |
|-----------|---------|
| **Input** | 28×28 grayscale images (784 features) |
| **Hidden Layer** | 64 neurons with ReLU activation |
| **Output** | 10 neurons with Softmax (probability distribution) |
| **Initialization** | He initialization for weights |

---

## 📊 Key Metrics

- **Training Set:** 60,000 MNIST images
- **Test Set:** 10,000 MNIST images
- **Learning Rate:** 0.15 (configurable)
- **Iterations:** 101 (default)
- **Activation Functions:** ReLU (hidden), Softmax (output)

---

## 🚀 Quick Start

### 1. **Install Dependencies**
```bash
pip install keras tensorflow numpy matplotlib gradio opencv-python
```

### 2. **Run the Training**
```python
# The notebook trains the model automatically
W1, b1, W2, b2, history = gradient_descent(X_train, Y_train, alpha=0.15, iterations=101)
```

### 3. **Launch Interactive Interface**
```python
# Open the interactive visualization with drawing pad
demo.launch(inbrowser=True)
```

---

## 🎨 Interactive Features

### **Neural Network X-Ray**
Draw a digit and see **8 visualizations** in real-time:

1. **Input** — Your drawn digit (28×28)
2. **Hidden Neurons** — What the network "sees" (activation map)
3. **Raw Output (Z2)** — Pre-activation scores
4. **Probabilities (Before)** — Model's confidence before learning
5. **Probabilities (After)** — How weights adjusted after correction
6. **Output Error** — What the model got wrong
7. **Neuron Blame** — Which hidden neurons to adjust
8. **Weight Updates** — Which connections changed most

### **Two Modes**
- **Test Mode:** Draw and see predictions (no learning)
- **Learning Mode:** Enter true label to trigger backpropagation

---

## 📈 Training Progress

The notebook includes:
- ✅ **Accuracy tracking** across iterations
- ✅ **Visual accuracy curve** showing improvement over time
- ✅ **Test set evaluation** with confidence scores
- ✅ **Random sample predictions** with visual feedback (green ✓ / red ✗)

---

## 🔬 Behind the Scenes

### Forward Propagation
```
Z1 = W1·X + b1
A1 = ReLU(Z1)
Z2 = W2·A1 + b2
A2 = Softmax(Z2)
```

### Backpropagation
```
dZ2 = A2 - Y_onehot
dW2 = (1/m) · dZ2 · A1ᵀ
dZ1 = W2ᵀ · dZ2 ⊙ ReLU'(Z1)
dW1 = (1/m) · dZ1 · Xᵀ
```

### Parameter Update
```
W = W - α · dW
b = b - α · db
```

---

## 📁 File Structure

```
neural_network.ipynb
├── Data Loading (MNIST)
├── Data Preprocessing (Flatten & Normalize)
├── Network Definition (Functions)
├── Training (Gradient Descent)
├── Evaluation (Accuracy, Predictions)
├── Visualization (Matplotlib plots)
└── Interactive Demo (Gradio UI)
```

---

## 🎓 Learning Outcomes

By studying this code, you'll understand:
- ✅ How neural networks forward pass works
- ✅ How backpropagation calculates gradients
- ✅ Weight initialization strategies
- ✅ Activation functions (ReLU, Softmax)
- ✅ Hyperparameter tuning (learning rate, iterations)
- ✅ Why visualizing weights and activations matters

---

## ⚙️ Customization

| Parameter | Location | Effect |
|-----------|----------|--------|
| `n_neurons` | Cell 7 | Number of hidden layer neurons |
| `alpha` | Training call | Learning rate (higher = faster but less stable) |
| `iterations` | Training call | Number of training steps |
| `temperature` | Cell 7 | Softmax sharpness (higher = more confident) |

---

## 🎯 Expected Results

- **Training Accuracy:** ~97% after 101 iterations
- **Test Accuracy:** ~96%
- **Inference Time:** < 1ms per digit

---

## 💡 Pro Tips

1. **Quick Demo:** Set `iterations=11` to see the model train in seconds
2. **Detailed Learning:** Increase `iterations=501` for better accuracy
3. **Fine-tune:** Adjust `alpha` (learning rate) for different behaviors
4. **Visualize Intermediate:** Check activation maps to debug model behavior

---

## 🔗 Resources

- **MNIST Dataset:** http://yann.lecun.com/exdb/mnist/
- **Backprop Explained:** https://karpathy.medium.com/yes-you-should-understand-backprop-e2f06eab496b
- **Neural Network Basics:** https://neuralnetworksanddeeplearning.com/

---

## 📝 License

Free to use, modify, and share for educational purposes.

---

**Built with ❤️ | Learn. Build. Understand.** 🚀