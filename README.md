Q learning v/s Monte Carlo in Reinforcement Learning
So essentially reinforcemnet learning in openAI gym is termed so because the agent performs an action, observes and reaps a reward and this happens over so many time times over 5000 episodes 
Q-Learning trains the agent after each step while Monte Carlo trains the model after the episode has been completed- tracing back the steps
In both learning methods we have used greedy algorithm as the policy to take action based on epsilon which continously decays(i.e: we start with 10% exploration and after each episode the agent gains some experience after which the exploration rate decreases and exploitation rate increases)
Essentially we have a Q table for both models- q_table_ql and q_table_mc
Q table has the states mapped with the action space containing a q-value for the action taken when in that state-programmed as a dictionary with key values as the state assigned a numpy array of action space(0-5) so index denotes the action and the value of the list is the q value
q value denoted as q_table[state][action] 
In Q-Learning Algorithm- the q value is updated after each time step= (*updated*)q[state][action]=alpha*(reward+gamma*(max_reward of next state)-q[state][action](*current*))
In Monte Carlo- the q value is upadted after every episode, after each episode the state,action,reward is traced back in a reversed order
  essentially episode data is a list- collects a tuple (state,action,reward) after every timestep and after the episode the episode data is unwrapped from the last step(step,action,reward) 
  G=gamma*reward+G
  (*updated*)q[state][action]=alpha*(G-q[state][action](*current*))
So in both steps the q table is continuously updated/back traced and updated 
