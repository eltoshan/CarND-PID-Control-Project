# Describe the effect each of the P, I, D components had in your implementation.

### Proportional (P) component
The P component is the instantaneous contribution to the control proportional to the current
CTE. This is the main factor moving the vehicle towards the center of the lane.

### Integral (I) component
The I component contributes to the control in proportion to the total cumulative CTE. 
This means that it is able to overcome control bias, like improper alignments and 
crowned road surfaces.

### Derivative (D) component
The D component is proportional to the instananeous slope of the CTE. So it adds a damping
effect to curb overshooting the target.

# Describe how the final hyperparameters were chosen.

I used manual tuning to achieve the desired results. First thing I realized was that there
were not any noticeable control bias, so the I component factor was for the most part
kept very low. Then the next thing I noticed was the car was overshooting the target 
and oscillating a lot, so I increased the D factor to damp that motion. And finally, 
I needed a large enough P factor to negotiate the tighter corners.
