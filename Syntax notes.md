# matlab syntax notes

## ranges
`[1:n]` will create an integer range from 1 to n

## loops
### general syntax
```matlab
objectives = [1:10] % integer range from 1 to 10

for gateID = objectives % objectives is declared as range; gateID assumes each 
						% value in objectives
	
	doStuffTo(gateID)
	
end % endfor - required
```

### loop index
`ii` used for `for` loop indices because `i` is matlab reference to imaginary number, e.g. `sqrt(-1)`

```matlab
K>> i

ans =

   0.0000 + 1.0000i
```

## multi-line parameter lists
```matlab
function (param expression 1,...
		  param expression 2,...
		  param expression 3,...
		  param expression n)
```
Whitespace must be parsed somehow so we might have to explicitly declare that the next line belongs to the same expression