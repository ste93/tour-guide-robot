# Tour Guide Robot

[![Docker Images CI](https://github.com/hsp-iit/tour-guide-robot/actions/workflows/main.yml/badge.svg)](https://github.com/hsp-iit/tour-guide-robot/actions/workflows/main.yml)

#### The Dockerfile(s) can be found [here](https://github.com/hsp-iit/tour-guide-robot/tree/master/docker_stuff).

for more information see the [wiki](https://github.com/hsp-iit/tour-guide-robot/wiki)
##### - Known problems are:
- Some applications dont behave nicely on yarpmanager (ex gazebo due to clock), so they are run seperatly with a .sh file.
- The image has to be built individually as I can't find a way to share the docker image while keeping the repository in dockerhub private.

## To launch the simulation:

### outside the docker 

#### Install docker
`sudo apt install docker`

and run post installatio steps https://docs.docker.com/engine/install/linux-postinstall/docker%20first%20installation%20guide

enable experimental features https://thenewstack.io/how-to-enable-docker-experimental-features-and-encrypt-your-login-credentials/

## Docker Standalone

#### open a terminal and go to the docker_sim directory
`cd docker_stuff/docker_sim`

#### compile the docker
`./build-docker.sh`

#### launch the docker
`./start-docker-sim.sh`

### inside the docker

#### go to the correct directory
`cd ~/tour-guide-robot/app/navigation/scripts/`

#### run the simulation
`./start_sim.sh`

then do the steps in yarp manager

## docker compose

go to the correct directory `cd docker_stuff/docker_sim`, then build docker `docker-compose build`, allow users to connect to x `sudo xhost +` and run docker `ducker-compose up`

to shut it down `docker-compose down` in the same directory, then do the steps in yarp manager


## in yarp manager

#### open the app **Navigation_ROS_R1_SIM**

#### run all the modules one by one in order (pay attention if navigationGUI starts correctly)

#### connect all

#### then localize twice in yarp navigation gui and check that in ros is correctly initialized

#### if in rviz you see local costmap, global costmap, lidar and voxels then you're done
