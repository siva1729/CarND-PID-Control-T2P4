# CarND-Controls-PID   Self-Driving Car Engineer Nanodegree Program

## Project Description:
Goal is to "build a PID controller and tune the PID hyperparameters by applying the general processing flow as described in the lessons," and to "test your solution on the simulator!" 

The simulator will provide the cross track error (CTE) and the velocity (mph) in order to compute the appropriate steering angle. The PID (proportional/integral/differential) controller must respond with steering and throttle commands to drive the car reliably around the simulator track.

### Rubric Discussion Points
## Describe the effect each of the P, I, D components had in your implementation.
PID components describe the "P - proportional", component causes the car to steer proportional to the car's distance from the lane center and  - if the car is far to the right it steers to left, if it's slightly to the left it steers to the right. The D is the "differential", component counteracts the P component's tendency to ring and overshoot the center line. Tuning D parameter will cause the car to approach the center line smoothly without overshoot/ringing. The I "integral", component counteracts a bias in the CTE which prevents the P-D controller from reaching the center line and could be contributed by sensor_drift.

## Describe how the final hyperparameters were chosen.
Initially the hyperparameters are tuned manually first by changing the values of the parameters to small non-zero values. The track was was narrow and is sensitive to the parameters to start with. Initially the Proportional parameter is changed to small non-zero value (ex: 0.5) to check the deviation of the vehicle from center lane and then tuned manually to find a reasonable deviation. OAfter finding reasonable params that were getting car around track, then I fine tuned one parameter at a time. 

---

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

There's an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

Tips for setting up your environment can be found [here](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/f758c44c-5e40-4e01-93b5-1a82aa4e044f/concepts/23d376c7-0195-4276-bdf0-e02f1f3c665d)

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)



