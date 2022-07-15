# Knee-Bend-Counter
knee bend exercise detector that counts the successful rep count only if the user bends the knee for more than 8 seconds by using Mediapipe and OpenCV . The condition for the knee to be in a bent stage is that the angle between the hip, knee, and ankle should be smaller than 140 degree. If angle is greater than 140 degrees then knee is said to be in a straight stage. If the user is unable to hold the knee in the bent stage, then a flag will appear, printing "keep your knee bent!" If the user holds the knee in the bent stage for more than 8 seconds, then the flag will print "good work!".
