## Unsupervised Energy Prediction Smart Grid context using reinforcement cross-building transfer learning

<https://core.ac.uk/download/pdf/82748024.pdf>

* How to predict energy demand?
* This paper uses a Deep Boltzmann Machine to estimate the continuous state of the energy consumption.
* On top of it, it builds an reinforcement learning model that predicts the energy consumption using a policy.
* On top of this policy, the paper also builds a transfer learning model for a different kind of building using Model (M) and initial policy (P), comes up with a new policy (PP). For example, predicting energy consumption of a commercial building using a personal building.
* Data is coming from an electrical company in UK. It has categorical features. (Personal building, Commercial building etc). Train- Test split was done.
* Some statistical testing was done to evaluate the predictions from Boltzmann Machines.
* RBM were used for state estimation.
* What is the reward function in RL model? What are the actions? Not a discrete problem. Continuous state & continuous action Reward is RMSE between actual and predicted.
* Didn't completely understood how they were using RL here.