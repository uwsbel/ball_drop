Ball Drop Simulation
=========

Simulation parameters, initial data and other information needed to simulate ball drop example



Ball Drop Simulation
=========

Simulation parameters, initial data and other information needed to simulate ball drop example

| Varaible           | Value                               |   | Description                                 |   |
|--------------------|-------------------------------------|---|---------------------------------------------|---|
| PI                 | 3.14159265359                       |   | PI constant                                 |   |
| G                  | 9.80665 [m/s^2]                     |   | Acceleration due to gravity                 |   |

### Particle Parameters

| Varaible           | Value                               |   | Description                                 |   |
|--------------------|-------------------------------------|---|---------------------------------------------|---|
| Particle_Radius    | 0.0005 [m]                          |   | (r = 500 um = 0.5 mm => d=1mm)              |   |



### Ball Parameters
| Varaible           | Value                               |   | Description                                 |   |
|--------------------|-------------------------------------|---|---------------------------------------------|---|
| Ball_Radius        | 0.0127 [m]                          |   | (d=2.54 cm = 1 in)                          |   |
| Collision_Envelope | 0.1*Ball_Radius                     |   | Used to prevent tunneling                   |   |
| Ball_Density       | 700 [kg/m^3]                        |   |                                             |   |
| Ball_Mass          | Ball_Density*(4/3)*PI*Ball_Radius^3 |   |                                             |   |
| Start_Height       | 0.0592+Particle_Radius+Ball_Radius  |   | Starting height of the ball in simulation   |   |
| Drop_Height        | 0.1 [m]                             |   | Physical height of ball                     |   |
| Start_Velocity     | -sqrt(2*G*Drop_Height)              |   | Initial velocity computed from start height |   |
| Initial_Position   | [0,Start_Height,0]                  |   |                                             |   |
| Initial_Velocity   | [0,Start_Velocity, 0]               |   |                                             |   |
