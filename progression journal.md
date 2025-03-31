# scope

*  learn about autonomous navigation
*  create a digital twin for an offroad capable autonomous vehicle
*  document a video of my progress and outcome

# learn
## [autonomous navigation](https://www.mathworks.com/videos/autonomous-navigation-part-1-what-is-autonomous-navigation-1592993748308.html)

* 

## [particle filters (monte carlo localization)](https://www.mathworks.com/videos/autonomous-navigation-part-2-understanding-the-particle-filter-1594903924427.html)

* robot needs to use it's sensors and motion models (dead reckoning) to estimate it pose (position and orientation)
* particle filter generates particles with random pose > generates lidar data for each of the pose > compares generated lidar with real lidar and generates probability of true pose
* particles with higher probability stay while lower are filtered out > new generation of particles based off higher probability particles in previous generation > process repeated with higher probablility particles staying and next generation of particles inheriting pose with slight differences
* as the robot moves, it will dead reckon its position and apply estimated motion to particles in filter (with level of random motion to account for dead reckoning noise)
* as the filter creates generations that are more and more accurate to true pose, less and less particles are needed and will free up processing power
* use [this example](https://www.mathworks.com/help/nav/ug/localize-turtlebot-using-monte-carlo-localization.html) to reinforce learning 

## [SLAM using pose graph optimization](https://www.mathworks.com/videos/autonomous-navigation-part-3-understanding-slam-using-pose-graph-optimization-1594984678407.html)

* Simultaneous Localization and Mapping (robot is unaware of surroudings or its pose)
* algos classified into filtering (EKF, Particle) or smoothing (pose (aka factor) graph optimization)
* in a perfect situation, robot will take scans of map and all scans will line up > in the real world, there is uncertanty that skews scans around and generates a map that makes no sense > this is where pose graph comes in to makes sense of the uncertanty
* odometry will give us best guess of how far each scan is from one another > with this we can set a confidence % in the new pose and create a constraint between each scan/odometry pair.
* this confidence dictates how far each scan will move from its initial best guess location to match up with other scans
* pose graph nomenclature: scans = nodes, constraint = edge
* the bread and butter comes when two nodes are similar and what has to happen to the pose (x, y, rotation) to line them up together is calculated and a loop closure is created
* this closure and movement of the final node to match the inital node will cascade down the line of edges and affect each one since they all relate to eachother
* this climax leads to better map, better pose estimation, and better guess of where the robot was
* from here the robot will continue to drive and make loop closures where the data presents itslef and adjust the map and past poses accordingly
* false loop closures are hard to remove once they are in
* from here we would generate a binary occupancy map that would become the map we use
* or we can create a probabilistic occupancy map where 1 and 0 are very confident on where things are or aren't blocks that fall inbetween are "undiscovered"

## [path planning with A*, RRT, RRT*](https://www.mathworks.com/videos/autonomous-navigation-part-4-path-planning-with-a-and-rrt-1594987710455.html)

*

## [exteded object tracking](https://www.mathworks.com/videos/autonomous-navigation-part-5-what-is-extended-object-tracking-1595498165103.html)

*

## [metrics for system charaacterization](https://www.mathworks.com/videos/autonomous-navigation-part-6-metrics-for-system-assessment-1597236837396.html)

* 
