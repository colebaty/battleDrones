# plotGateDetailed.m
[[buildCourse.m|parent]]

```matlab
center = mean(corners,1); % gate center is at mean of corner vectors
lookVector = [0 1 0]; % look vector is one meter straight ahead
poseVector = calcPose(corners); % vector normal to gate entrance; see calcPose.m
angularOffset = calcAngleBetweenVectors (lookVector, -poseVector); 
% negative poseVector because poseVector is pointing at us
width = 0.75;
thickness = 0.5;
```

honestly, i'd just use `plotGateSimple`.
- [ ] is `plotGateSimple` fully implemented?