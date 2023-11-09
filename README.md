# GridWorld Nutrient Search with Q-Learning
This repository hosts the code for a GridWorld nutrient search game, designed to illustrate the application of QLearning, a reinforcement learning technique. The structure of the program is as follows:

    Initialize the Environment (GridWorld class): The game environment is initialized with a grid size of 100 x 100px and a nutrient source placed at its very center. The initialization also includes setting a nutrient gradient, which is used to create a more complex landscape for the agent to navigate.

    Agent Definition (Agent class): The agent within this game occupies a single pixel in the grid and is capable of moving in four directions with a pace of one pixel per round. It is initialized at a random position within the grid. The agent's actions are determined either randomly (exploration) or by making use of a Q-table (exploitation).

    Feedback Mechanism (via step method in GridWorld class): Feedback to the agent is provided through rewards based on the Manhattan distance to the nutrient source, incentivizing the agent to find the shortest path to the nutrient source.

    QLearning Update (within the main training loop): The Q-table is updated after each action taken by the agent, factoring in the current state, action, reward, subsequent state, learning rate (alpha), and discount factor (gamma). This method forms the core of the agent's learning process.

    Reward Function (calculate_reward function): The reward function allocates numerical rewards or penalties to the agent. It favors actions that reduce the distance to the nutrient source and penalizes those that do not, with a substantial reward being given when the agent finds the source.

The primary execution loop runs the agent's training for a designated number of episodes, during each of which the agent attempts to locate the nutrient source, limited by a maximum number of moves per episode. The agent follows an epsilon-greedy policy, which ensures a balance between exploration (choosing a random action) and exploitation (choosing the best-known action from the Q-table). The rate of exploration (epsilon) is set to decay over time, encouraging the agent to depend more on its learned experiences as it becomes more adept.

In this repository, the provided script is designed to encourage experimentation with the underlying mechanics of Q-learning. Users are empowered to adjust a variety of hyperparameters, such as the learning rate, discount factor, and the degree of exploration versus exploitation, to observe their impact on the agent's ability to learn effectively. Moreover, the game environment can be configured with three distinct nutrient gradient shapes — radial, rectangular, and diamond — each offering a unique challenge for the agent's search strategy.

Finding a configuration that enables the agent to consistently locate the nutrient source is a non-trivial task. The interplay between the agent's exploratory moves and the strategy it learns is complex, and intuitive solutions may not always lead to success. In fact, even after extensive training, the agent can exhibit repetitive and inefficient behaviors, especially if the initial parameters are not conducive to learning in the given environment.

![agent_movement](https://github.com/DataScienceFH/RL_QLearn_GridWorldGradient/assets/129044997/6f9ad032-a19d-42fb-8b0c-60942e693790)

As a result, this repository is not just a demonstration of Q-learning's capabilities but also a sandbox for exploration. It invites users to dive into the intricacies of reinforcement learning, to tweak and tune the environment and learning process, and to observe how slight changes can dramatically affect the agent's performance. Through this hands-on experience, one can gain deeper insights into the potential and limitations of applying a Q-learning approach to nutrient search tasks within a grid world. It's a call to explore, learn, and understand the nuances that make reinforcement learning a fascinating and challenging field.
