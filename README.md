### Forked ROS Package: tabletop_collision_map_processing

This is a fork of the ROS Fuerte release of tabletop_collision_map_processing, <br>
from the pr2_object_manipulation stack: <br>
https://code.ros.org/svn/wg-ros-pkg/stacks/pr2_object_manipulation/branches/0.6-branch/perception/tabletop_collision_map_processing/

The ROS Wiki is incorrect, and the Trunk (Groovy-devel) is now at: <br>
https://github.com/ros-interactive-manipulation/pr2_object_manipulation/tree/groovy-devel/perception/tabletop_collision_map_processing

These fixes & modifications are for using this node as part of the ROS Manipulation Pipeline, for robots other than the PR2. These changes have been tested to not break the simulated PR2 robot in ROS Fuerte Gazebo. <br>
-- David Butterworth, PAL Robotics S.L.
<br>

<br>
**Changelist:**

 - CRITICAL: Fixed bug that can cause segfault. Added an extra check, so if request_models=false when calling tabletop_object_detector, this node will not try to read the null cluster_model_indices and segfault.

 - Fixed empty field in the response message. The collision name was not being included for each graspable object in the response message.

 - Removed hard-coded confidence threshold for models. The confidence value is read from the min_marker_quality param, as used by the tabletop_object_recognition node. If the database returns a lower confidence value, then the model fitment is good.

 - Optional enhancement for recognized objects. This code, when enabled, will add the object mesh of recognized objects to the Collision Map, instead of a bounding box. This is useful for testing, and looks good in Rviz, but may add extra overhead for collision checking.


