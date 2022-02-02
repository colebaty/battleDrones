# original given algorithm
```
fly through gates in sequence as quickly as possible
	launch
	while there are more gates
		acquire gate
			identify gates in FOV
			if any gates in FOV is target gate
				return projected corner locations of target gate
			else search for target gate
				if no target gate specified
					turn drone 10 degrees ccw
				else
					calculate turn angle to target gate
				turn drone toward target gate
		fly to gate offset point
		align with gate
		pass through gate to overshoot
```