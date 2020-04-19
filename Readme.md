**Problem statement:**
1. On a map environment of city we have to run the car(agent) from one location(goal) to the other.
2. Using TD3 algorithm to train the continuous policy estimation model.
3. Extract patch which contains car and its surroundings, can be used as state and use CNN based neural network model for actor-critic networks.


**Changes made from the Session-7 Assginment:**

**1. Replaced dqn with TD3: **
TD3 is policy estimation algorith, which contains 6 NN models in total.
Two actor models -- actor model, actor target
Four critic models -- two critic models, two critic targets.

*three model networks take input from the curret state(s) and its action(a).
*three target networks take input from the nest state(s') and next action(a').
For detailed theoritical understanding with code please refer to this link https://github.com/chunduri11/session-9_RL.


**2. State space:**
For state input we are using an 80x80 patch of sand image around the current car location. Resized it to 40x40 using cv2.
These patches are stored into the Replay Buffer and subsiquently sampled in batches to be used for training the TD3 models.

**3. Action space:**
Since the TD3 allowes us the flexibility of continuous action spaces. We are using one output dimention to represent the angle of car. This single output value estimates values in the range of -5 to 5, which is also the range of car rotation from left extream to right extream. This is seen as a regresion problem on the side of actor model.

4. 
