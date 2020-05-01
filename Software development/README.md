![Logo](https://gitlab.com/custom_robots/spotmicroai/website/raw/master/docs/assets/logo.png)

# SpotMicroAI Inverse Kinematic notes

Inverse kinematics are not yet added to the basic-runtime software.

Nathan Kau has written the following notes to facilitate us the job: Inverse kinematics notes by Nathan Kau.pdf

Bob Wind commented on the document:

* @Nathan Kau There are a couple of details that would improve your IK model.  First, on Spotmicro, the axis associated with the beta angle does not intersect the axis for the alpha angle.  There is an offset of about 10 mm of the beta axis below the alpha axis.   Second, the Spotmicro foot has a curved surface which could be approximated as a sphere with radius of about 22 mm.  So it would be best to consider the lower end of the lower leg to be the center of that sphere, and the foot to be in contact with the ground when the end of the lower leg is 22 mm perpendicularly above the ground.
