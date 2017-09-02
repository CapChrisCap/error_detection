# Error Detection for Roboy

This is the workspace pattern for the error detection of roboy. 

## Installation

### 0. Run ROS Master

```bash
roscore
```

### 1. Clone Repo

```bash
cd YOUR_DEST_DIR
git clone --recursive https://github.com/Roboy/error_detection .
```

### 2. Change path to powerlink

Open the file `src/roboy_managing_node/src/myoMaster.cpp` with
`vi src/roboy_managing_node/src/myoMaster.cpp`

And search for the line: 
`strncpy(pOpts_p->cdcFile, "SOME_PATH/src/roboy_powerlink/powerlink/output/mnobd.cdc", 256);`

and replace SOME_PATH with your path (to the workspace). 

**SOME_PATH is of course only exemplary!**

### 3. Compile it

```bash
cd WORKSPACE_DIR
catkin_make
```

### 4. Source it

```bash
cd WORKSPACE_DIR
source devel/setup.bash
```

### 5. Run the FPGA

see [https://devanthro.atlassian.net/wiki/display/CO/Tutorial+of+how+to+control+the+PaBiLegs](https://devanthro.atlassian.net/wiki/display/CO/Tutorial+of+how+to+control+the+PaBiLegs)

### 6. Open the UI

```
# ONLY WITH ROOT RIGHTS: sudo -s
rosrun roboy_interface roboy_interface
```

For more information see [https://devanthro.atlassian.net/wiki/display/CO/Tutorial+of+how+to+control+the+PaBiLegs](https://devanthro.atlassian.net/wiki/display/CO/Tutorial+of+how+to+control+the+PaBiLegs)

### 7. Run the error detection code

E.g. `rosrun roboy_error_detection roboy_error_detection_presentation`

and check if there are some notifications: 

E.g. `rostopic echo /roboy/system_notification/warning`

