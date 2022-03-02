# Unmarked Crosswalk Carla Scenario
This repository includes a dataset from an unmarked crosswalk scenario, implemented in CARLA 0.9.9.4 simulator. The dataset consists of 300 signals with their binary labels, which poses a two-class classification problem.

# Description of the scenario:
The scenario consists of an autonomous vehicle (referred to as ego), a pedestrian and another car, which is assumed to be driven by a "reasonable" human driver who obeys traffic laws. Ego and the other car are in different, adjacent lanes, moving in the same direction. The cars move uphill in the y-z plane of the coordinate frame, towards positive y and z directions, with no lateral movement in the x direction (see Figure 1). The accelerations of the cars are constant, and smaller for ego. 

<p align="center">
  <img width="500" src="https://user-images.githubusercontent.com/47225763/156440667-506a4b8f-4825-4605-8b9d-bf5efe60153a.png">
</p>
<p align="center">
Figure 1: Snapshot of the unamrked crosswalk scenario in simulator CARLA
</p>

The positions and accelerations of the cars are initializes such that the other car is always ahead of ego. The vehicles are headed toward an intersection without any traffic lights. There is an unmarked crosswalk at the end of the road before the intersection. When the pedestrian crosses the street, the other car brakes to stop before the intersection. If the pedestrian does not cross, the other car keeps moving without decreasing its velocity. The simulation of this scenario ends whenever ego gets closer than 8 meters to the intersection.

**Objective**: Ego does not have a clear line-of-sight to the pedestrian crossing at the intersection, because of the other car and the uphill shape of the road.  The goal is to develop a method allowing ego to infer whether a pedestrian is crossing the street by observing the behavior (e.g., relative position and velocity over time) of the other car. 


# About the dataset:
The labeled behaviors of the cars, which are the relative distance and velocity of other car with respect to ego in the y and z directions, are provided in this dataset. The labels indicate whether a pedestrian is crossing the street (label 1) or not (label 0). We collected 300 signals with 500 uniform time-samples per trace, where 150 are with and 150 without pedestrians crossing the street. 

The signals are 4 dimensional: first component is the relative distance in y direction, second component is the relative distance in z direction, third component is the relative velocity in y direction, and the fourth component is the relative velocity in z direction. 

# Citation:
If you use this dataset, then please consider citing the reference paper:
Aasi, Erfan, Cristian Ioan Vasile, Mahroo Bahreinian, and Calin Belta. "Classification of Time-Series Data Using Boosted Decision Trees." arXiv preprint arXiv:2110.00581 (2021). doi: 10.48550/arXiv.2110.00581

# Simulation Videos:
Here are some recorded videos from the CARLA simulator, for each case of the pedestrian crossing and no pedestrian crossing. Ego is the red car and the other vehicle is the gray car.

#### Pedestrian Crossing: ####

Ego's point of view | top view
:-: | :-:
<video src='https://user-images.githubusercontent.com/47225763/156450441-67283bef-1676-446f-afb7-5e5ed1a4da3f.mp4' width=180/> | <video src='https://user-images.githubusercontent.com/47225763/156450686-38cb4611-6cae-4380-afb7-186c62ef0114.mp4' width=180/>

  
#### No Pedestrian Crossing: ####

Ego's point of view | top view
:-: | :-:
<video src='https://user-images.githubusercontent.com/47225763/156450887-9e81ff0c-29d5-4be2-80fc-0c4af297c198.mp4' width=180/> | <video src='https://user-images.githubusercontent.com/47225763/156450934-388d8276-6952-4455-bba8-756aae12da5a.mp4' width=180/>




