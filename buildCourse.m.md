# create gate
[[simulatorMain.m|parent]]

```matlab
gateType = buildGate(); % create gate template

gates(:,:,1) = gateType + ... % creates a gate labelled 1
gates(:,:,2) = gateType + ... % creates a gate labelled 2
...


gates(:,:,1) = gateType + [25,-10,sideLength/2 + 1]; % move gate right 25m, back
													 % 10m, up (one-half of 
													 % sideLength plus one)
gates(:,:,2) = gateType + [25,10,sideLength/2 + 1];
...
gates(:,:,n) = gateType*rotateVector3(theta) + [25,50,sideLength/2 + 1];
% rotate vector theta *degrees* normal to Z; 
% recall that theta is measured from the x-axis along QI and QIV
% and that a positive theta indicates anti-clockwise rotation
% see 'rotationMatrix' below; 
% move rotated gate right 25m, forward 50m, up...
```

## rotationMatrix
```matlab
rotationMatrix = [cosd(theta) sind(theta) 0; % parametrically defined XYZ coords
                 -sind(theta) cosd(theta) 0; % note that sind(theta) accepts degrees
                  0           0			  1];% and sin(theta) accepts radians
				  							 % pi may be called from anywhere 
											 % within matlab as it is written 
											 % here, e.g. sin(pi)
```
[matlab function reference](https://www.mathworks.com/help/matlab/referencelist.html?type=function)
[matlab pi reference](https://www.mathworks.com/help/matlab/ref/pi.html)

### questions
- [ ] `gateType` is 4x3, `rotationMatrix` is 3x3.  How does "multiplication" of multiplication between matrices of different dimensions

## figure(integer d)
Calls a new empty window with title "Figure `d`"

```matlab
fpvFigNum = 99; % figure number; must be integer>0
figure(fpvFigNum); % create new "figure", or blank plotting space
hold on; % window persist?
plotDroneCage
for ii = 1:length(gates)
	plotGateDetailed(gates(:,:,ii),num2str(ii))
end
view(30,15)
```
[[plotDroneCage.m|plotDroneCage]]

## [[plotGateDetailed.mi|plotGateDetailed]]



