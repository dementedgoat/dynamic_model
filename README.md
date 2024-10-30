Dynamic Liquidity Provision and Fee Adjustment for Uniswap V4

This repository contains the implementation of a dynamic liquidity provision and fee adjustment strategy for Uniswap V4, specifically designed for the WSTETH/ETH, using advanced machine learning and reinforcement learning techniques. The strategy optimizes liquidity positions and swap fees based on real-time market conditions, aiming to maximize returns while managing risks like impermanent loss.

Table of Contents

	1.	Overview
	2.	Features
	3.	Architecture
	4.	Requirements
	5.	Installation
	6.	Usage
	7.	Repository Structure
	8.	Results
	9.	Future Work
	10.	Contributing

Overview

This project implements a dynamic liquidity management strategy for Uniswap V4, integrating:

	•	Predictive Analytics: Uses EGARCH for volatility estimation and Transformer-based models for price prediction.
	•	Reinforcement Learning: Employs a Proximal Policy Optimization (PPO) agent to make strategic decisions on liquidity rebalancing and fee adjustments.
	•	Smart Contract Interaction: Uses an on-chain Hook architecture to apply dynamic fee adjustments and liquidity rebalancing.

Features

	•	Dynamic Range Optimization: Adjusts liquidity positions based on real-time volatility predictions.
	•	Dynamic Fee Adjustment: Sets optimal swap fees to align with market demand and volatility, maximizing returns and compensating for impermanent loss.
	•	Off-Chain Computation & On-Chain Execution: Uses a decentralized Keeper network for off-chain calculations and on-chain Hooks for execution.

Architecture

The architecture consists of three major components:

	1.	Predictive Models: Includes EGARCH and Transformers to forecast market conditions and volatility.
	2.	Reinforcement Learning Agent: Uses PPO to make dynamic decisions on liquidity and fee adjustments.
	3.	Smart Contract Implementation: Features Oracle and Hook contracts for seamless integration of off-chain analytics with on-chain actions.

Requirements

The project uses Python and several dependencies, as specified in requirements.txt. Key libraries include:

	•	TensorFlow
	•	PyTorch
	•	stable_baselines3
	•	web3
	•	pandas
	•	numpy
	•	scipy
	•	gymnasium

Refer to the requirements file for a full list ￼.

Installation

	1.	Clone the repository:

git clone <repository-url>
cd <repository-directory>


	2.	Install the required Python packages:

pip install -r requirements.txt


Usage

1. Running and Training the PPO Model

	•	The PPO model is implemented and trained directly within the provided Jupyter notebook ppo.ipynb.
	•	Open the notebook using Jupyter:

jupyter notebook ppo.ipynb


	•	Follow the instructions in the notebook to configure parameters and run the training process.
	•	The model is trained using historical Uniswap V3 data, with outputs detailing the optimization of liquidity positions and fee adjustments.

2. On-Chain Data Handling

	•	The onchain_data.ipynb notebook handles the extraction and preprocessing of on-chain data.
	•	Open the notebook using Jupyter:

jupyter notebook onchain_data.ipynb


	•	Adjust data sources or configurations based on your environment.

3. Deployment

	•	Integrate the generated fee and liquidity recommendations with the Oracle and Hook contracts on Uniswap V4.

Repository Structure

|-- ppo.ipynb                 # Notebook for training and running the PPO model
|-- onchain_data.ipynb        # Notebook for retrieving historical on-chain data
|-- requirements.txt          # Project dependencies
|-- README.md                 # Project documentation

Results

The proposed model demonstrates significant improvements in annualized returns and overall profitability compared to passive strategies. Key metrics include:

	•	Annualized Return: 40.11%
	•	Total Fees Earned: 18.42 ETH
	•	Impermanent Loss: Managed with dynamic adjustments

Detailed results are presented within the notebooks.

Future Work

	•	Hedging Strategies: Integrating financial derivatives to hedge impermanent loss.
	•	Deployment on Uniswap V4: Testing the strategy in a live environment for further optimization.
	•	Broader Application: Extending the model to other DeFi platforms and asset pairs.

Contributing

Contributions are welcome! Please follow these steps:

	1.	Fork the repository.
	2.	Create a new branch (git checkout -b feature/YourFeature).
	3.	Commit your changes (git commit -am 'Add new feature').
	4.	Push to the branch (git push origin feature/YourFeature).
	5.	Create a new Pull Request.