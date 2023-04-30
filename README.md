# A Fake ROS Package to Keep Various Data of the Robot

## How to Use

1. Clone this repository to your catkin workspace's `src` folder.
2. Assume you need to create a folder to save some data, e.g. `YOUR_DATA_DIR`.
3. Create a new folder named `YOUR_DATA_DIR` in `data_base` folder. Naming convention: use all simple alphanumerics, no spaces, no special characters, no underscores .
4. Empty folders are not tracked by git, so you need to create a file named `.gitkeep` in `YOUR_DATA_DIR` folder, for others to see that you have created a new folder for some data.
5. However, what is in `YOUR_DATA_DIR` folder will be tracked by git, so you need to add `YOUR_DATA_DIR/` to `.gitignore` file (open it and see previous cases), if you don't want to upload your data to github (may be data is specific to a particular runtime and does not need to be shared).

## Inside the Codes you can use below code to get the path of the data folder/ file

```cpp
#include <ros/package.h>

std::string filePath = ros::package::getPath("data_base") + "/<YOUR_DATA_DIR>/<YOUR_FILE>.txt"; // whatever file extension you want
```

## Use Cases

1. Saving data from a ROS node to a file, e.g. a text file, a csv file, a json file, etc.
    1. Global 3D map: `data_base/map3d/`
    2. PRM graph: `data_base/prmgraph/`
2. Special robot positions, e.g. home position, charging position, etc.
    1. Home position: `data_base/homepos/`
    2. Charging position: `data_base/chargingpos/`
    3. Initial position: `data_base/initpos/`