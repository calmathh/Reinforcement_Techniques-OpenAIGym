so the observation space of cartpole essentially [0]th of env.reset() is a list of 4 values-box array with max min values specified in it's documentation and implemented in the code
these observation spaces are continous and infinite such values exist and if you have reffered to my TAXI-v3 code, you see that q table has been trained q(s,a) with keys as the state and with infinite such values training would be ://
Hence we discretize into bins  of 11 for each element of observation space-refer to code
SARSA considers the best reward of next step into evaluation as well
