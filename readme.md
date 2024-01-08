# Box in Box collision simulator
## Dynamics project

This is a course project to simulate in 2D, a box in a box and collision with each others.

* Dynamic simulation 
    * Object have weight and inertia
    * Additional external force applied to one of the object
    * Have gravity

* Collision updates with 20 collision pairs
    * All corners and edges between boxes are considered (16 collision pairs) 
    * outer box has collision with ground as well

* Visualization and animation with plotly

Video showing everything working:

[Working with slow rainbow](https://github.com/Gray-Stone/ME314-box-in-box-dynamics-sim/assets/7969697/d1c54af8-e664-4fcc-a324-ba0c1bddcb2e)

## Design

Due to the large amount of computation from symbolic math, jupyter notebook is used to allow rework and debug with sections of codes.

The generate steps are: 

1. Define the dynamic system in symbolic math (Euler lagrange) 
2. Create the symbolic impact equations (but not solving it) systematically for each pair.
3. Create impact update lambda and impact checking lambda 
4. Combined dynamic equations and impact update into the same simulation function, and conditionally call impact update during the simulation.
5. Use the simulated output to generate plots and animations.

## Problems and future works:

The impact systems only handle 1-to-1 impact pairs between edge and vertex, simulations impacts are not handled (multiple vertex hitting edges at the same time-step).

Here is another video showing it failed to handle simultaneous impact 

[Punched through floor with simultaneous impact](https://github.com/Gray-Stone/ME314-box-in-box-dynamics-sim/assets/7969697/f87c2c30-0c82-406a-8ca6-fc0f83138057)  


The system is only in 2d. But there should be very little work to expand it into 3d. 


## Other:


All code in the repo are jupyter notebooks. 

The project code is in `Project/Project.ipynb` 

There are also lots of homework files in other folder.