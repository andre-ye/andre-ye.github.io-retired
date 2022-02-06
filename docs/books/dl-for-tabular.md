---
layout: default
title: Modern Deep Learning for Tabular Data
parent: Books
nav_order: 2
has_children: false
---

# Modern Deep Learning for Tabular Data

Powerful Tools to Solve Common Problems
{: .fs-6 .fw-300 }

Book #2
{: .label .label-blue}

Published: n/a
{: .label .label-green}

Pages: est 500-600
{: .label .label-purple}

| This book is in the process of being written, with expected completion in late 2022. |

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Book Description 

In this book, you’ll learn how to apply one of the most powerful tools in modern AI – deep learning – to one of the most common forms of data: tabular data. Whether for finance, business, security, medicine, or countless other disciplines, deep learning can help you discover rich insights and model complex patterns in your tabular dataset. 

This book will begin with a rigorous overview of machine learning principles, concepts, algorithms, and code to set a string foundation. Then, you’ll learn how to implement successful data processing, extraction, and engineering strategies. In the following chapters, the book engages with the theory and practice of five key pillars of modern deep learning in application to tabular data: deep learning training paradigms, convolutions, recurrent networks, transformers, and tree-based design. The book concludes with a study of tabular deep learning applications in several case studies, demonstrating real-life use of the presented concepts. 

*Modern Deep Learning for Tabular Data* is one of the first of its kind - a rigorous and wide exploration of deep learning applications to tabular data, documenting novel methods and techniques in the space. Equipped with this book, you’ll be ready to utilize modern deep learning paradigms and techniques to solve today’s most challenging tabular data problems. 

---

## USPs
1. The link between deep learning and tabular data has not been seriously explored at an advanced level in the market, despite tabular data being one of the most important and common forms of data in standard data science contexts. Our book will be one of or the first book dedicated towards a rigorous and wide exploration of deep learning applications to tabular data, documenting novel methods and techniques. 
2. Besides presenting many well-developed and older concepts similar to other books in the market, our book is uniquely characterized by a focus on modern ideas and methods developed in recent deep learning advancements. 
3. Most books of similar categories do not focus on applying the skills taught in the content to real-world applications. Our book will have multiple case studies which demonstrate how the presented techniques can be used in real-life contexts like business and medicine. 
4. The book looks critically upon its own content to maximize user success, developing the user’s understanding of when deep learning is or isn’t a useful tool in various contexts rather than presenting the methods without the use case context. 

---

## Tentative Table of Contents

Page count approximation: 500-600 pages

**Introduction**

Chapter Goal: To set up ground definitions for key terms and ideas, to give the user important context for why the book was written and its goal. 
- What is tabular data? 
- Why is deep learning for tabular data important? Applications in business, medicine, and other contexts. 
- Deep learning is not a universal solution. Understand the difference between deep learning, machine learning, and statistics. 

**Chapter 1:  Classical Machine Learning Principles and Methods**

Chapter Goal: To discuss key principles and algorithms of machine learning modeling relevant to working with tabular data and to the rest of the book. 
- Fundamental principles of modeling – regression/classification, bias/variance trade-off + double deep descent, feature space concept 
- Metrics and Evaluation (MAE, MSE, AUC, Precision/Recall, F1 Score, Gini Impurity, Entropy) 
- K-Nearest Neighbors 
- Linear and Logistic Regression 
- Support Vector Machines 
- Decision Tree and Random Forest 
- Gradient Boosting 
- Problems with classical machine learning algorithms (not versatile, not automated, difficult to optimize, requires more human intervention) 

**Chapter 2:  Data Preparation Methods**

Chapter Goal: To explore a wide variety of data preparation methods, which will be valuable in using neural networks for tabular data. 
- Data manipulation methods – loading and manipulation with Pandas and NumPy 
- Data encoding: categorical data (one-hot encoding, ordinal encoding, target encoding, etc.) and continuous data (quantization, standardization, normalization, etc.) 
- Feature extraction (principal component analysis, linear discriminant analysis, U-MAP, t-SNE) 
- Feature selection and engineering (information gain, variance threshold, statistic-based selection, high-correlation features) 

**Chapter 3: Applying Standard Neural Network Structures to Tabular Data**

Chapter Goal: To understand how neural networks operate and to build successful and complex architectures using standard feedforward layers for tabular data. 
- Neural network theory crash course and math (feed-forward operation, backpropagation, optimization & metrics) 
- Building a simple neural network on tabular data with Keras crash course 
- Manual nonlinear structure design (borrowing architectural styles from CNN model heavyweights – ResNet, Inception, etc.) 
- Embedding layers 

**Chapter 4: Applying Convolutional Structures to Tabular Data**

Chapter Goal: To develop a strong understanding of what convolutional layers are and how they can be successfully applied to tabular data. 
- Convolutional neural network crash course (convolutions, pooling, specialized convolution operations, major convolutional architectures) 
- 1-Dimensional convolutional neural networks 
- The DeepInsight Method 

**Chapter 5: Applying Recurrent Structures to Tabular Data**

Chapter Goal: To develop a strong understanding of what recurrent layers are and how they can be successfully applied to both temporal and nontemporal tabular data. 
- Recurrent neural network crash course (RNNs, LSTMs, GRUs) 
- Time Series Data 
- Applications to nontemporal tabular data 

**Chapter 6: Advanced Deep Learning Strategies**

Chapter Goal: To understand advanced deep learning strategies and their applications to the tabular data context. 
- Autoencoders 
- Similarity Learning 
- Self-supervised learning 
- Meta-optimization of architecture and data pipeline 
- Data generation (GAN, VAE) 

**Chapter 7: Applying Transformer Structures to Tabular Data**

Chapter Goal: To develop a familiar understanding of what transformer structures are and to successfully apply available models to tabular data contexts. 
- Transformer theory crash course 
- Vanilla Transformer Applications – GPT-2 Example 
- TabTransformer Model and Method 
- TaBERT Model and Method 


**Chapter 8: Applying Tree-Based Logic Structures to Tabular Data**

Chapter Goal: To recognize and understand the framework of tree-based deep learning solutions and to successfully apply available models to tabular data contexts. 
- Tree-based logic theory crash course 
- GrowNet Model and Method 
- TabNet Model and Method 
- NODE Model and Method 

**Chapter 9: Tabular Data Modeling Case Studies**

Chapter Goal: To see how the theory presented throughout the book operates with real-world datasets with three tabular data machine learning case studies. 
- Mechanisms of Action Prediction by Laboratory of Innovation Sciences at Harvard 
- Stock Prediction by Jane Street 
- Predicting Fan engagement of MLB players based on Digital content by MLB and Google Cloud

