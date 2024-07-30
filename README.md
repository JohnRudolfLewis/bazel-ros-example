Example of using ros with bazel.

Reproduces the issue mentioned in mvukov/rules_ros#35 "ModuleNotFoundError: No module named 'rospy'"

```
$ bazel run //chatter:chatter
INFO: Analyzed target //chatter:chatter (1 packages loaded, 16 targets configured).
INFO: Found 1 target...
Target //chatter:chatter up-to-date:
  bazel-bin/chatter/chatter
  bazel-bin/chatter/chatter_launch.py
INFO: Elapsed time: 0.945s, Critical Path: 0.03s
INFO: 1 process: 1 internal.
INFO: Build completed successfully, 1 total action
INFO: Running command line: bazel-bin/chatter/chatter
... logging to /home/vscode/.ros/log/a64df9b8-4eb5-11ef-b119-bf9446a06087/roslaunch-edfa49feca88-51089.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

started roslaunch server http://edfa49feca88:37901/

SUMMARY
========

NODES
  /
    listener (chatter/listener)
    listenerpy (chatter/listener.py)
    talker (chatter/talker)

auto-starting new master
process[master]: started with pid [51800]
ROS_MASTER_URI=http://localhost:11311/

setting /run_id to a64df9b8-4eb5-11ef-b119-bf9446a06087
process[rosout-1]: started with pid [51811]
started core service [/rosout]
process[talker-2]: started with pid [51816]
process[listener-3]: started with pid [51817]
process[listenerpy-4]: started with pid [51818]
Traceback (most recent call last):
  File "/home/vscode/.cache/bazel/_bazel_vscode/0cd11761e4a882ffd46b0cb0705acf1d/execroot/_main/bazel-out/k8-fastbuild/bin/chatter/chatter.runfiles/_main/chatter/listener.py", line 6, in <module>
    import rospy
ModuleNotFoundError: No module named 'rospy'
[listenerpy-4] process has died [pid 51818, exit code 1, cmd chatter/listener.py __name:=listenerpy __log:=/home/vscode/.ros/log/a64df9b8-4eb5-11ef-b119-bf9446a06087/listenerpy-4.log].
log file: /home/vscode/.ros/log/a64df9b8-4eb5-11ef-b119-bf9446a06087/listenerpy-4*.log
```
