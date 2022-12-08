**Describe the bug**
- As training goes on, the memory usage by the process increases. It reaches around 6GB in episode 245 while only 1.9GB in episode 20. In later episodes, memory usage goes up around 70MB per episode, as shown in [04_q_learning_for_trading.ipynb](https://github.com/DavidHJong/machine-learning-for-trading/blob/e514b7a47d9df1cda453161b35b63e0ed54955eb/22_deep_reinforcement_learning/04_q_learning_for_trading.ipynb)'s `Train Agent` cell's output. 

**What I did to find this**
1. In [04_q_learning_for_trading.ipynb](https://github.com/DavidHJong/machine-learning-for-trading/blob/e514b7a47d9df1cda453161b35b63e0ed54955eb/22_deep_reinforcement_learning/04_q_learning_for_trading.ipynb), I added a cell `monitor RAM usage` with 2 functions to monitor the process memory usage and call these functions multiple times in the `Train Agent` cell. 
2. I recorded the process memory changes and save it into [a `.csv` file](https://github.com/DavidHJong/machine-learning-for-trading/blob/main/22_deep_reinforcement_learning/memory_change_record.csv) in a fork project.

**Steps to reproduce the behavior:**
1. To see in which steps the major memory changes occurred, open the[ `memory_change_record.csv` file](https://github.com/DavidHJong/machine-learning-for-trading/blob/main/22_deep_reinforcement_learning/memory_change_record.csv) 
2. To reproduce this record, run [04_q_learning_for_trading.ipynb](https://github.com/DavidHJong/machine-learning-for-trading/blob/e514b7a47d9df1cda453161b35b63e0ed54955eb/22_deep_reinforcement_learning/04_q_learning_for_trading.ipynb). 

**Questions**
 - Is this memory leak? 
 - What is the main part of code contributing to this increasing memory usage? 
 - Any way to keep the memory usage constant or at a small size as training goes on? 

**Why it matters**
 - An increasing memory usage seems like a major reason for the slowing down in later episode training. 
