# Dealer Outlier Detection Using Spectral Clustering

A team project completed as part of the **Fraud Analytics Using Predictive and Social Network Techniques** course during my B.Tech in Mathematics & Computing at **IIT Hyderabad**.

## Overview

This project explores the use of **spectral clustering for outlier detection** in a network of dealers.

The objective is to identify potentially malicious dealers based on patterns in their transactional behaviour. Dealers with behaviour that differs significantly from the main groups in the dataset are treated as potential outliers.

## Problem Statement

Given transaction-related features for a set of dealers, identify **potentially malicious dealers** using spectral clustering.

## Dataset

The project uses `data.csv`.

Each row represents a dealer.

The dataset contains:

* **7 correlation parameters**, with values ranging from -1 to 1
* **3 ratio parameters**

These features describe different aspects of the transactional behaviour of the dealers.

## Methodology

The project applies spectral clustering to identify groups of dealers with similar transactional behaviour and detect potential outliers.

### 1. Construct a Similarity Graph

A similarity graph is constructed from the input data using a **Gaussian kernel**.

The graph represents the similarity between dealers based on their feature values.

### 2. Compute the Graph Laplacian

The **Laplacian matrix** is derived from the similarity graph and captures the relationships between neighbouring data points.

### 3. Compute Eigenvalues and Eigenvectors

The eigenvalues and eigenvectors of the Laplacian matrix are computed using matrix decomposition techniques.

The eigenstructure of the Laplacian is used to identify the underlying structure of the data.

### 4. Transform the Data

The relevant eigenvectors are used to project the original data into a new feature space where the clusters can be more clearly separated.

### 5. Cluster the Dealers

**K-Means clustering** is applied to the transformed data to identify groups of dealers with similar behaviour.

Dealers that do not fit the main cluster structure are identified as potential outliers.

## Results

The analysis of the eigenvalues indicated a significant separation between the first two eigenvalues, suggesting that the data could be separated into **two clusters**.

The original project analysis identified:

**398 potential outliers (malicious dealers).**

## Technologies Used

* Python
* Spectral Clustering
* K-Means
* Gaussian Kernel
* Eigenvalue/Eigenvector Analysis
* NumPy
* Scikit-learn

## Repository Structure

```text
.
├── README.md
├── A3SpectralClustering.ipynb
├── data.csv
```