# DC-Position-Control-System
## Aim:
To control the position of motor having the following specifications using MATLAB.<br>
(J)     moment of inertia of the rotor =    0.02 kg.m^2<br>
(b)     motor viscous friction constant =    0.002 N.m.s<br>
(Ktf)    motor torque constant   =           1.5 N.m/Amp<br>
(Ra)    armature resistance  =              2 Ohm<br>
(La)     armature inductance  =              0.5 H<br>
(Kb)      back emf constant = 0.5<br>
## Apparatus Required:
Computer with MATLAB software
## Theory: 
The speed of a DC motor is directly proportional to armature voltage and inversely proportional to flux. In field controlled DC motor the armature voltage is kept constant and the speed is varied by varying the flux of the machine. Since flux is directly proportional to field current, the flux is varied by varying field current.

The speed control system is an electro-mechanical control system. The electrical system consists of armature and field circuit but for analysis purpose, only field circuit is considered because the armature is excited by a constant voltage. The mechanical system consists of the rotating part of the motor and the load connected to the shaft of the motor. The field controlled DC motor speed control system is shown in the below figure. For this field controlled DC motor we shall find transfer function.
<img width="722" height="237" alt="image" src="https://github.com/user-attachments/assets/f69d0d67-780d-44a7-89f7-4f64dc17dd79" />
Let Rf = Field resistance
Lf = Field inductance
if = Field current
Vf= Field voltage
T = Torque developed by motor
Ktf = Torque constant
J = Moment of inertia of rotor and load
The equivalent circuit of field is shown in the below figure.
image
<img width="322" height="303" alt="image" src="https://github.com/user-attachments/assets/7a9f8f4a-8780-48b5-947f-732587ca6d4c" />
By Kirchoff ‘s voltage law, we can write
image
The torque of DC motor is proportional to product of flux and armature current. Since armature current is constant in this system, the torque is proportional to flux alone, but flux is proportional to field current.
                                            T ∝ if 

                                    Torque , T = Ktf if
The mechanical system of the motor is shown in the below figure.
image                          
<img width="407" height="100" alt="image" src="https://github.com/user-attachments/assets/ff384f43-5c6b-4d24-94f7-e8dceb370717" />
The differential equation governing the mechanical system of the motor is given by,
image
<img width="263" height="92" alt="image" src="https://github.com/user-attachments/assets/997e9fdb-6ec7-4aaf-b479-9af7186c0481" />
On taking Laplace transform of the above equations with zero initial condition we get,
image
<img width="632" height="197" alt="image" src="https://github.com/user-attachments/assets/5d4e1d12-bfe2-4f8f-bc85-c20766d47f00" />
Equating equations (2) & (3) we get,
<img width="917" height="182" alt="image" src="https://github.com/user-attachments/assets/bd409506-d3c4-4aa8-a030-0b2b60522ea7" />
The equation (1) can be written as
<img width="646" height="75" alt="image" src="https://github.com/user-attachments/assets/8159e807-f464-4cc7-accf-646e17b269fb" />
<img width="303" height="137" alt="image" src="https://github.com/user-attachments/assets/53a0cb2a-af0f-49d0-842a-529ef66f5529" />

## Procedure:
1.	Open MATLAB software
2.	Open a new script file.
3.	Type the program.
4.	Save and Execute the program.
5.	Analyse the output in open loop and closed loop.

## Program
kt=0.0274
Rf=4
Lf=2.75E-6
J=3.2284E-6
B=3.5077E-6
s=tf('s')
ol_sys=kt/((Rf+Lf*s)*(J*s*s+B*s))
subplot(2,1,1)
step(ol_sys)
title('open loop response')
cl_sys=feedback(ol_sys,1)
subplot(2,1,2)
step(cl_sys)
title('closed loop response')
## Output
<img width="1686" height="960" alt="image" src="https://github.com/user-attachments/assets/c399db04-fe1a-422b-96fe-e7dbdb8adf64" />

## Result
Thus, the position of dc motor is controlled using MATLAB. 
