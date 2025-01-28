# Torque-Calculating
# Descreption
- Calculating the torque required from each motor in the robot arm
- What is the appropriate servo motor for each joint?
# 1-Calculating the torque required from each motor in the robot arm
# Equation
To calculate the required torque for each motor in the robotic arm, we use the torque equation: 𝜏=𝐹×𝑑 ,,
where:
𝜏 ->is the torque (N·cm).
𝐹 ->is the applied force (N).
𝑑 ->is the effective arm length (cm).
# Method
1- Before calculat Convert the Weight to Force
𝐹=𝑚×𝑔
where:
𝑚=1 kg .
𝑔=9.81 m/s² (gravitational acceleration).
So 𝐹 = 1×9.81=9.81 N
2- Calculate Torque for Each Joint
Each joint carries the torque from the previous segments plus its own load:
- Joint 1 (Base Joint): Supports the entire arm and the load.
- Joint 2 (Middle Joint): Supports the end link and the load.
- Joint 3 (End Joint): Supports only the load at the tip.
# Torque at Joint 3 (End Joint)
Only the load is considered:
𝜏3=𝐹×𝑑3=9.81×4=39.24 N\cdotpcm
 
# Torque at Joint 2 (Middle Joint)
This joint supports:
1-The load.
2- The last segment (10 cm), assuming it has a mass of 0.5 kg.
- Force from the arm segment:
𝐹2=0.5×9.81=4.905 N

- Torque from the arm segment:
𝜏2,𝑎𝑟𝑚=4.905×(10/2)=24.53 N\cdotpcm

- Total torque at joint 2:
𝜏2=𝜏3+𝜏2,𝑎𝑟𝑚=39.24+24.53=63.77 N\cdotpcm

# Torque at Joint 1 (Base Joint)
This joint supports:
1-The middle joint.
2-The first arm segment (15 cm), assuming it has a mass of 0.7 kg.
- Force from the arm segment:
𝐹1=0.7×9.81=6.867 N

- Torque from the arm segment:
𝜏1,𝑎𝑟𝑚=6.867×(15/2)=51.50 N\cdotpcm

- Total torque at joint 1:
𝜏1=𝜏2+𝜏1,𝑎𝑟𝑚=63.77+51.50=115.27 N\cdotpcm

# 2- What is the appropriate servo motor for each joint?
For Joint 1 (Base): Needs at least 115.27 N·cm torque. Suggested motors: Dynamixel MX-64 or MG995 (130 N·cm).
For Joint 2 (Middle): Needs at least 63.77 N·cm torque. Suggested motor: MG996R (90 N·cm).
For Joint 3 (End): Needs at least 39.24 N·cm torque. Suggested motor: MG995 or MG996R.
