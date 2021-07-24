# What is PID Controller

A **proportional–integral–derivative controller** (**PID controller**) is a control loop feedback mechanism widely used in industrial control systems and a variety of other applications requiring continuously modulated control. The distinguishing feature of the PID controller is the ability to use the three control terms of ***proportional***, ***integral*** and ***derivative*** influence on the controller output.

[1]: https://en.wikipedia.org/wiki/PID_controller

# PID Parameters

The PID controller is one of the most common and fundamental controllers. The **proportional**, **integral**, and **derivative** terms are summed to calculate the output of the PID controller.

<table style="width:100%">
  <tr>
    <th>
      <p align="center">
       <img src="./gif/No Control1.gif" alt="Overview" width="100%">
      </p>
    </th>
    <th>
      <p align="center">
       <img src="./gif/P Control1.gif" alt="Overview" width="100%">
      </p>
    </th>
    <th>
      <p align="center">
       <img src="./gif/PID Control1.gif" alt="Overview" width="100%">
      </p>
    </th>
  </tr>
  </table>

- **The term P** (Kp in my code) is proportional to the **cross track error** (cte in the code), which is the lateral distance between the vehicle and the so-called reference trajectory. 

In this project, the reference trajectory is the center of the lane. Using **P-Control** alone will result in an error between the vehicle and lane center, as we can see from the video. A high proportional gain results in a large change in the output for a given change in the error. If the proportional gain is too high, the system can become unstable. But tuning theory and industrial practice indicate that the proportional term should contribute the bulk of the output change.

- **The term I**(Ki in the code) accounts for the sum of  cross track errors over time. If there is still residual error after applying P-Control, the integrate term seeks to eliminate the residual error by adding a control on accumulating the past errors. However, since the integral term responds to accumulated errors from the past, it can cause the present value to overshoot the reference trajectory.

- **The term D**(Kd in my code) bases on the temporal derivative of the cross track error. That is the current change rate of error. The more rapid the change, the greater the controlling. Derivative action can help improving stability of the system.


# Tuning parameters

At first, I attempted to utilize the Twiddle to optimize the parameters.  In Twiddle application of the lessons, we make a new trajectory according to every parameters' change. But in the final project,  I don't know how to generate a vehicle trajectory. At last,  I choose to tune the parameters manually based on the vehicle behavior in response to parameters' change  in simulator. 

# Running the Program

1. Download the simulator and open it. In the main menu screen select : Path Planning.
2. The [PID README](https://github.com/lilyhappily/Udacity-Project3-CarND-PID-Control-and-notes/blob/master/CarND-PID-Control-Project/README.md)  has more detailed instructions for installing and using c++ uWebScoketIO.

