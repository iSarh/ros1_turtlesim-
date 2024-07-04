# What Is Turtlesim?
**Turtlesim** is a simple turtle simulator with a graphical window showing a turtle robot. The turtle can be moved using ROS commands or the keyboard.

# Gettin Started Wit Turtlesim
Start ROS in the terminal using the command:

```bash
$ roscore
 ```

**_Open New Terminal_**

Start the turtlesim node on a new terminal using the command:

``` $ sudo apt install ros-noetic-turtlesim ```

Run turtlesim:

``` $ rosrun turtlesim turtlesim_node ```


![Screenshot 2024-07-04 004723](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/4261c90b-3a01-48a7-a0a9-39925fb9e1a2)


## Control Turtle Movement

> [!IMPORTANT]  
> From now on, open a new terminal to execute the command.

There is a built-in feature that takes the user's keyboard input and converts it into a ROS message that controls the turtle's position.

To control the turtle's position from your keyboard:

```$ rosrun turtlesim turtle_teleop_key```


![Screenshot 2024-07-04 010223](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/85fea155-d7a5-4dc7-892e-9ad549621be7)


The ```turtlesim_node``` and the ```turtle_teleop_key``` node are communicating with each other over a ROS Topic. ```turtle_teleop_key``` is **publishing** the keystrokes on a topic, while turtlesim **subscribes** to the same topic to receive the keystrokes. 

Let's see the nodes and topics currently running.

```$ rosrun rqt_graph rqt_graph```
```rqt_graph``` creates a dynamic graph of what's going on in the system.


![Screenshot 2024-07-04 012431](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/4dedfaf6-7caf-4da4-9624-26f7f021a916)




