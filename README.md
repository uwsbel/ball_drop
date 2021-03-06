Ball Drop Simulation
=========

A spherical projectile impacts a bed of granular material. 

<img src="https://raw.githubusercontent.com/uwsbel/ball_drop/master/images/validation_ballDrop.png" alt="" height="300px">

### References

[Low-Speed Impact Craters in Loose Granular Media](http://journals.aps.org/prl/abstract/10.1103/PhysRevLett.90.194301)

[Erratum: Low-Speed Impact Craters in Loose Granular Media](http://journals.aps.org/prl/abstract/10.1103/PhysRevLett.91.149902)

[Penetration depth for shallow impact cratering](http://journals.aps.org/pre/abstract/10.1103/PhysRevE.71.051305)

[Scaling of impact craters in unconsolidated granular materials](http://scitation.aip.org/content/aapt/journal/ajp/81/11/10.1119/1.4817309)


## Parameters used in simulation

### Constants

| Variable           | Value                               | Units    | Description                                 |
|--------------------|-------------------------------------|----------|---------------------------------------------|
| PI                 | 3.14159265359                       | [-]      | PI constant                                 |
| G                  | 9.80665                             | [m/s^2]  | Acceleration due to gravity                 |

### Particle Parameters

| Variable           	| Value                                       	| Units    	| Description                                 	|
|--------------------	|---------------------------------------------	|----------	|---------------------------------------------	|
| Particle_Radius    	| 0.0005                                      	| [m]      	| (r = 500 um = 0.5 mm => d=1mm)              	| 
| Particle_Density   	| 2500                                        	| [kg/m^3] 	|                                             	| 
| Particle_Mass      	| Particle_Density*(4/3)*PI*Particle_Radius^3 	| [kg]     	|                                             	| 
| Particle_Friction  	| 0.3                                         	| [-]      	| Friction between particles                  	|
| Total_Particles   	| 500400                                        | [-]      	| Total particles in simulation                	|

### Ball Parameters

| Variable           | Value                               | Units    | Description                                 |
|--------------------|-------------------------------------|----------|---------------------------------------------|
| Ball_Radius        | 0.0127                              | [m]      | (d=2.54 cm = 1 in)                          |
| Collision_Envelope | 0.1*Ball_Radius                     | [m]      | Used to prevent tunneling                   |
| Ball_Density       | 700                                 | [kg/m^3] |                                             |
| Ball_Mass          | Ball_Density*(4/3)*PI*Ball_Radius^3 | [kg]     |                                             |
| Start_Height       | 0.0592+Particle_Radius+Ball_Radius  | [m]      | Starting height of the ball in simulation   |
| Drop_Height        | 0.1                                 | [m]      | Physical height of ball                     |
| Start_Velocity     | -sqrt(2*G*Drop_Height)              | [m/s]    | Initial velocity computed from start height |
| Initial_Position   | [0,Start_Height,0]                  | [m]      |                                             |
| Initial_Velocity   | [0,Start_Velocity, 0]               | [m/s]    |                                             |

### Container Parameters

| Variable  	| Value 	| Units 	| Description                              	|
|-----------	|-------	|-------	|------------------------------------------	|
| Length    	| 0.1   	| [m]   	| Length of Container                      	|
| Width     	| 0.1   	| [m]   	| Width of Container                       	|
| Height    	| 0.15  	| [m]   	| Height of Container                      	|
| Thickness 	| 0.01  	| [m]   	| Thickness of Container                   	|
| Friction  	| 0.3   	| [-]   	| Friction between container and particles 	|

### Simulation Parameters

| Variable               	| Value                                  	| Units   	| Description                                                                                      	|
|------------------------	|----------------------------------------	|---------	|--------------------------------------------------------------------------------------------------	|
| Gravitational_Accel    	| -G                                     	| [m/s^2] 	|                                                                                                  	|
| Time_Step              	| 0.00002                                	| [s]     	| Time Step for Solver                                                                             	|
| Simulation_Length      	| 0.2                                    	| [s]     	| Total Length                                                                                     	|
| Solver                 	| Accelerated Projected Gradient Descent 	| [-]     	|                                                                                                  	|
| Solver Tolerance       	| 1e-3                                   	|         	|                                                                                                  	|
| Max_Iterations         	| 1000                                   	|         	|                                                                                                  	|
| Contact_Recovery_Speed 	| 0.6                                    	| [m/s]   	| This is the maximum velocity correction that can be applied by the penetration depth correction. 	|


### Initial Data Set

An initial data set for the 500,400 spheres is located [here](http://sbel.wisc.edu/documents/ball_drop/SpherePos_500K.dat). 

The data is stored in a csv format and organized in the following manner:
Each line contains the information for a single sphere. 

Sphere_id, position_x, position_y, position_z, rotation_x, rotation_y, rotation_z, velocity_x, velocity_y, velocity_z



### Results

[Link](http://sbel.wisc.edu/radu_tmp/)
