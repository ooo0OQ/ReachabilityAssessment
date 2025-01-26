# Reachability Assessment

#### This repository is based on the [DeepReach Toolbox](https://github.com/smlbansal/deepreach/tree/public_release)

## Environment Setup

Please go to [DeepReach](https://github.com/smlbansal/deepreach/tree/public_release) for reference.

## Problem Description

Consider the following 2D model of an autonomous navigation robot:
$$\begin{equation*} \dot{p_x} = v \cos(\theta)\\
\dot{p_y} = v \sin(\theta) \end{equation*}$$
where $(p_x,p_y)$ is the position of the robot, $v$ = $1$m/s is its (constant) speed, and $\theta$ is the robot heading. The robot state is given by $x = (p_x,p_y)$ and it can directly control its heading $u$ :$= \theta$, where $\theta \in [-\pi, \pi]$

## Running a DeepReach Experiment

Training command for "There is an obstacle of radius 0.5m at the origin that the robot needs to avoid". The results will be under runs/avoid/.
```
python run_experiment.py --mode train --experiment_class DeepReach --dynamics_class AutonomousNavigationRobot --experiment_name avoid --minWith target --Radius 0.5 --velocity 1.0 --avoid True
```
Training command for " There is a goal region of radius 0.25m at the origin". The results will be under runs/reach/.
```
python run_experiment.py --mode train --experiment_class DeepReach --dynamics_class AutonomousNavigationRobot --experiment_name reach --minWith target --Radius 0.25 --velocity 1.0
```

## Samples

Trained checkpoints and plots can be found under avoid_sample and reach_sample.