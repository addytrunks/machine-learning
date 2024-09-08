# Simple RNN Overview

## 1. What is RNN (Recurrent Neural Network)?

A **Recurrent Neural Network (RNN)** is a type of neural network designed to recognize patterns in sequential data. Unlike traditional feedforward networks, RNNs have connections that form cycles, allowing them to maintain memory of previous inputs and process sequences, such as time-series data, natural language, or video frames.

---

## 2. Why Use RNN?

RNNs are used primarily to capture sequential patterns and dependencies in data that traditional neural networks, like a simple **Artificial Neural Network (ANN)**, cannot handle effectively.

### Why RNNs Over Simple ANN:

- **ANNs** treat each input independently, which makes them ineffective for handling data with time dependencies (e.g., sentences in natural language or stock prices over time).
- **RNNs**, by contrast, maintain memory of previous inputs through recurrent connections, allowing them to understand context in sequences. This is crucial in tasks like machine translation, speech recognition, and time-series prediction.

---

## 3. How Does RNN Work?

RNNs work by looping through sequences, taking input at each time step while retaining information from previous steps using hidden states. In simple terms, the network processes one element of the sequence at a time, while also considering what it has seen before.

### Key Points:

- At each time step, the input is combined with the hidden state (memory) from the previous step.
- The output is generated from the current input and the updated hidden state, which is then passed to the next step.
- This recurrent process allows the model to "remember" past inputs and improve predictions on the current input.

---

## 4. Disadvantages of Simple RNNs:

### **Long-Term Dependencies**:

While RNNs are good at capturing short-term patterns, they struggle with **long-term dependencies** (i.e., information far back in the sequence). As sequences get longer, RNNs can "forget" earlier inputs, making them less effective in capturing relationships between distant elements in a sequence.

### Why This Happens:

- The gradients during backpropagation can either shrink (vanishing gradient) or grow too large (exploding gradient), making it difficult to train the network on long sequences.

---

## Additional Information:

While Simple RNNs are useful for certain tasks, more advanced models like **LSTMs** (Long Short-Term Memory) and **GRUs** (Gated Recurrent Units) were developed to address the limitations of Simple RNNs in handling long-term dependencies.
