# buildGate()
Builds gate centered on XZ plane.

```matlab
gateType = [0,0,0; % lower left corner X, Y, Z
		0,0,1; % upper left corner
		1,0,1; % upper right corner
		1,0,0]*sideLength; % bottom right corner, all multiplied by scalar 
						   % sideLength
```

Creates a `gateType` with bottom left corner at the origin.

-----

```matlab
corners = gateType  - [1;1;1;1]*[1,0,1]*sideLength/2;

corners =

   -0.5000         0   -0.5000
   -0.5000         0    0.5000
    0.5000         0    0.5000
    0.5000         0   -0.5000
```

Translates `gateType` such that the center of the gate is at the origin, e.g.

```matlab
temp = gateType - [1;1;1;1]*[1,0,1]
						   %[X,Y,Z]
temp =

    -1     0    -1
    -1     0     0
     0     0     0
     0     0    -1
	 
temp = gateType - [1;1;1;1]*[1,0,1]*sideLength/2

temp =

   -0.5000         0   -0.5000
   -0.5000         0    0.5000
    0.5000         0    0.5000
    0.5000         0   -0.5000

```

[[buildCourse.m|parent]]