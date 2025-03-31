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

*

## [path planning with A*, RRT, RRT*](https://www.mathworks.com/videos/autonomous-navigation-part-4-path-planning-with-a-and-rrt-1594987710455.html)

*

## [exteded object tracking](https://www.mathworks.com/videos/autonomous-navigation-part-5-what-is-extended-object-tracking-1595498165103.html)

*

## [metrics for system charaacterization](https://www.mathworks.com/videos/autonomous-navigation-part-6-metrics-for-system-assessment-1597236837396.html)

* 
