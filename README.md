# NFT Price Prediction with Compression Distances

This repository contains the code for a project developed as part of the "Algorithmic Information & Artificial Intelligence" course. The goal is to predict the price of NFTs based on their visual and attribute-based similarities, leveraging compression distances and machine learning techniques.

## Overview
The project explores two main approaches:

1. **Normalized Compression Distance (NCD):** Based on data compression to measure visual similarity. This approach was not conclusive due to the limitations of compression in approximating Kolmogorov complexity.
2. **Normalized Information Distance (NID):** Leverages the relationship between Kolmogorov complexity and attribute probabilities. This approach yielded significantly better results.

After computing the distances, various methods were explored to predict the price of NFTs:
- Assigning the price of the closest NFT.
- Calculating a weighted average price based on distances.
- Using a neural network to predict prices based on distances and prices of other NFTs in the collection.

## Files

### Code

- **`NID.py`**: Implements the NID distance and multiple price prediction strategies.
- **`NCD.py`**: Implements the NCD distance. Not used in the final results due to its limitations.
- **`neural_network.py`**: Defines and trains a neural network to predict NFT prices using NID distances and associated prices.

### Data

- **`sandbar`**: Raw data of the NFT collection.
- **`sandbar_dist`**: Precomputed NID distances between NFTs.
- **`sandbar_price`**: Prices of NFTs in the collection.

These files are generated during runtime but are also stored for reproducibility and efficiency.

## Results

| Method                     | Mean Absolute Error | Relative Error (%) |
|----------------------------|---------------------|--------------------|
| Closest NFT (< 11 Sol)     | 2.1 Sol            | 50.5%             |
| `x` Closest NFTs (< 11 Sol)| 1.26 Sol           | 30.3%             |
| Weighted Average (< 11 Sol)| 1.7 Sol            | 40.9%             |
| Neural Network (< 11 Sol)  | 1.39 Sol           | 33.7%             |

- Filtering NFTs with prices above 11 Sol improved accuracy significantly because some listed NFTs are overpriced.
- Neural networks showed promise but require more and better data for further improvement.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/NathanRouille/NFT-Pricing.git
   cd NFT-Pricing
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

For more details, check the [Report](Report.pdf)
