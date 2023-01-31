# open_manipulator_kinect

# open_manipulator_kinect

1. sudo apt-get install --reinstall ros-melodic-openni-camera ros-melodic-openni-launch
sudo apt-get install ros-melodic-rviz ros-melodic-rqt_reconfigure ros-melodic-openni*

roslaunch openni_launch openni.launch
rosrun rviz rviz

Set the Fixed Frame (top left of the RViz window) to /camera_depth_optical_frame. Add a PointCloud2 display, and set the topic to /camera/depth/points. Turning the background to light gray can help with viewing. This is the unregistered point cloud in the frame of the depth (IR) camera. It is not matched with the RGB camera images. Now let’s look at a registered point cloud, aligned with the RGB data. Open the dynamic reconfigure GUI:

rosrun rqt_reconfigure rqt_reconfigure

And select /camera/driver from the drop-down menu. Enable the depth_registration checkbox. Now go back to RViz, and change your PointCloud2 topic to /camera/depth_registered/points. Set Color Transformer to RGB8. You should see a color, 3D point cloud of your scene.


add camera on rviz too


http://wiki.ros.org/fiducials







change ros param -> sudo emacs -nw create_markers.py line 43 fid_len to 14 from 140

rosparam set fiducial_len  0.014


roslaunch aruco_detect aruco_detect.launch camera:=/camera/rgb image:=image_color transport:=compressed


roslaunch open_manipulator_controller open_manipulator_controller.launch usb_port:=/dev/ttyACM0 baud_rate:=1000000

roslaunch open_manipulator_gazebo open_manipulator_gazebo.launch
