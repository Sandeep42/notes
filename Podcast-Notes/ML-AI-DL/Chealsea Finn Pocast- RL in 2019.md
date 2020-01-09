# Chelsea Finn Podcast

[https://twimlai.com/twiml-talk-335-trends-in-reinforcement-learning-with-chelsea-finn/](https://twimlai.com/twiml-talk-335-trends-in-reinforcement-learning-with-chelsea-finn/)

* Chelsea talks about important research lines in RL in 2019 and speculate the general direction of the filed for the next year.

## Dexterous manipulation tasks: Good Progress on using Physical Robots to perform activities

* Huge influx of interest in using real robots to perform activities, especially tasks which require Dexterous manipulation (Rotating faces of a Rubik's cube etc.)
* Two important papers:
	* [Dexterous Manipulation with Deep Reinforcement Learning: Efficient, General, and Low-Cost](https://arxiv.org/abs/1810.06045) 
		* Model free method, data from real world, directly learn from raw demonstrations. 
		* Example of data collected in the real world to activity done in the real world
	* [Solving Rubik's Cube with a Robot Hand](https://arxiv.org/abs/1910.07113):
		* Example of data collected in the simulated world and transferred to do activites
		* Controversial because they did not actually learn how to solve the cube, they were using a preexisting solver.
		* Finn thinks that it shouldn't be criticised because she thinks manipulation of actions is the harder task when compared with solving the cube. 

## Resurgence of Model based RL

* Model based is sample efficient. Real world objectives always come with some sort of model. Researchers are keen to exploit that.
* Two papers. Both of them build a model.
	* [Learning Latent Dynamics for Planning from Pixels](https://arxiv.org/abs/1811.04551)
		* Predict future values based on a latent represention
		* Use this as a model, and learn.
		* Trained on ATARI games
	* [Mastering Atari, Go, Chess and Shoji by Planning with a Learned Model](https://arxiv.org/abs/1911.08265)
		* Predict pixels into future. Fully convolutional networks. Trained on Atari. 
		* Use predicted pixels to plan efficient future actions

## Batch Off Policy RL

* Difficult to collect data in real time for all usecases. For example, medical studies. You can not take bad actions, kill patients and claim that you learned that it is a bad action.
* Difficult to simulate the environment
* In such cases, you typically have some data from an already existing policy.
* Can you use this "batch" data to train agents that are doing better than the old policy? This is concept behind batch-off policy RL.
* [RoboNet: Large-Scale Multi-Robot Learning](https://arxiv.org/abs/1910.11215): 
	* A dataset collected by various environments, actions, different types of robots, varying locations of the cameras, first person vs third person etc. Batch of policy RL must be used because the dataset is already collected through cooperation.

## Curriculum learning

* Learning through iterative process of solving increasingly complex environments
* Hallmark of human learning, building from basic blocks.
* Who provides the circular?
	* Agent creating it's own curriculum
	* Model trainer giving them in a sequence
* Learning from simple behaviour to complex behaviour
* Two papers:
	* [Paired Open-Ended Trailblazer (POET): Endlessly Generating Increasingly Complex and Diverse Learning Environments and Their Solutions](https://arxiv.org/abs/1901.01753)
		* Generate increasingly based environments to challenge the robot agent
		* Learn better policies
	* [Emergent Tool Use From Multi-Agent Autocurricula](https://arxiv.org/abs/1909.07528)
		* Multi-agent cooperation
		* Both the hider and finder wants to fullfill their corresponding activities.
		* As the simulation progresses, hider finds novel ways to hide objects. When finder identifies the strategy, the hider has to come up with new actions.
		* Self-generating curriculum.

## Some practical tools

* Tf-agents, open ai gym
* Dopamine. Reproducing various q learning algorithms with a reliable implementation
* PyTorch Higher: Meta learning. Optimisation inside optimisation. Higher can be used to get these gradients.
* Environments:
	* AI Habitat. Photo realistic images. Learning to navigate in real world
	* Meta world environment. Generalization across tasks. Created by Finn & Team.
	* Mine-RL task. Ability to learn from demonstration. Complex and long horizon skills
	* Recsim simulation platform for recommender systems. 