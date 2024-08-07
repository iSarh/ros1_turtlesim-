# What Is Turtlesim?
**Turtlesim** is a simple turtle simulator with a graphical window showing a turtle robot. The turtle can be moved using ROS commands or the keyboard.

# Gettin Started Wit Turtlesim
Start ROS in the terminal using the command:

```bash
$ roscore
 ```

**_Open New Terminal_**

Start the turtlesim node on a new terminal using the command:

```bash
$ sudo apt install ros-noetic-turtlesim
```

Run turtlesim:

```bash
$ rosrun turtlesim turtlesim_node
```


![Screenshot 2024-07-04 004723](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/4261c90b-3a01-48a7-a0a9-39925fb9e1a2)


## Control Turtle Movement

> [!IMPORTANT]  
> From now on, open a new terminal to execute each command.

There is a built-in feature that takes the user's keyboard input and converts it into a ROS message that controls the turtle's position.

To control the turtle's position from your keyboard:

```bash 
$ rosrun turtlesim turtle_teleop_key
```


![Screenshot 2024-07-04 010223](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/85fea155-d7a5-4dc7-892e-9ad549621be7)


Let's look at the command velocity data published by the ```turtle_teleop_key node```.

This data is published on the ```/turtle1/cmd_vel```

```bash
$ rostopic echo /turtle1/cmd_vel
```

You probably won't see anything happen because no data is being published on the topic. 

Let's make ```turtle_teleop_key``` publish data by pressing the arrow keys. 

> [!NOTE]  
> **If the turtle isn't moving you need to select the ```turtle_teleop_key``` terminal again.**

You should now see the following when you press the up key:


![Screenshot 2024-07-04 012241](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/c79678f2-8570-434a-ba9a-b205a96e6f42)


The ```turtlesim_node``` and the ```turtle_teleop_key``` node are communicating with each other over a ROS Topic.

```turtle_teleop_key``` is **publishing** the keystrokes on a topic, while ```turtlesim``` **subscribes** to the same topic to receive the keystrokes. 


Let's see the nodes and topics currently running.

```bash
$ rosrun rqt_graph rqt_graph
```

```rqt_graph``` creates a dynamic graph of what's happening in the system.


![Screenshot 2024-07-04 012431](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/4dedfaf6-7caf-4da4-9624-26f7f021a916)

**Last but not least, let's make the turtle draw a square on its own.**

```bash
$ rosrun turtlesim draw_square
```

![Screenshot 2024-07-04 004317](https://github.com/iSarh/ros1_turtlesim-/assets/63901303/ba66592b-d598-460f-80a5-cdf295cc1e63)


