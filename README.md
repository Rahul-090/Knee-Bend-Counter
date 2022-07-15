#				 Knee Bend Exercise


## STEPS:
* [Configuring the Media Pipe](#Configuring the Media Pipe)
* [Estimating poses](#Estimating poses)
* [Extracting joint coordinates](#Extraction of Joint Coordinates)
* [Calculating angles between joints](#Calculating angles between joints)
* [Counter,Time holder(8 seconds)](#Counter,Time holder(8 seconds))



## 1.Configuring the Media Pipe:
First, install and import Mediapipe,
Mediapipe is a cross-platform library developed by Google that provides amazing, ready-to-use ML solutions for computer vision tasks.
Along with Mediapipe, install and import some other dependencies such as OpenCV, numpy and time.

## 2. Estimating poses:
In this step, we will be estimating all the different joints and parts within our body.
First, we will capture the video feed from the video file provided.
We will recolor our image because when we pass the image to mediapipe it should be in RGB format, which is the default BGR when we read it.
Use the Pose estimation model to detect the pose.
Then recolor the image back to the default BGR format.
After that, we will perform detections, i.e., draw landmarks from the video feed (e.g., nose, eyes, ears, shoulders, elbows, wrists).

## 3. Extraction of Joint Coordinates:
In the third step, we will extract our joint coordinates for the eyes, elbow, wrist, ankle, knee, etc.
Use the pose estimation model to extract landmarks using detected pose estimation, as we did in the previous step.
Landmarks = results.pose_landmarks.landmark
And then we will extract the landmarks for the main 3 joints that we need to calculate the rep count for knee-bending exercises which are hip, knee, and ankle.

## 4.Calculating angles between joints:
We are going to calculate the angle between the hip, knee, and ankle to identify whether the leg is straight or bent.
 To calculate the angle, we are going to calculate the radians with the help of three parameters passed to the function calculateAngle(), which are hip, knee, and ankle, by using a trigonometric function and then converting radian to angle.
          

## 5. Inserting a timer (8 seconds), a stage (bent or straight), and a counter:
If the calculated angle is less than or equal to 140, then the stage of the leg will be "bent", and if the calculated angle is greater than 160 and the stage is "bent", then the stage will be "straight".
And for the time holder timeit library is used to measure the start time in starting when the stage changes from straight to bent stage, and the end time is measured when the stages changes from bent to straight stage,duration is calculated by subtracting the end time from the start time. If a user can hold the leg in the bent stage for the duration of 8 or more than 8 seconds, then the flag will print "good work". If the user is unable to stay in the bent stage for more than 8 seconds, the flag will print "keep the leg bent".
The rep will be counted only when the user is able to do full repetitions, i.e., both straight stage and bent stage, and hold the leg in the bent stage for 8 or more seconds.
                                


