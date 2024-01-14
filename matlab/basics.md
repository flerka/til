## Manage Workspace

Save current workspace to file
```
save <workspace-name.mat>
```

Load from file to current workspace
```
load <workspace-name.mat>
```

Clear current workspace
```
clear
```

## Command Prompt
```
clear
```

## Create Vector

Creates vector [1, 2, 3]
```
x = 1:3
```

Creates vector [1, 3, 5, 7]
```
x = 1:2:7
```

Creates evenly spaced vector 
```
x = linspace(100, 1000, 10)
```

## Create Matrix

From function matrix 6x2
```
all-zero = zeros (6, 2)
all-one = ones (6, 2)
all-rand = rand (6, 2)
all-rand-int = randi (6, 2)
```

From code matrix 2x2
```
hard-code-m = [7, 7; 7, 7]
```

## Random Funcs
```
[x, y] = size([7, 7; 7, 7])
[min-val, index-of-min] = ([2, 7; 7, 7])
```

## IF ELSE FOR END
```
a = 0
if 7 > 3
    a = 3
else
    for b=1:3
        a = a + b
    end
end
```

## Plots

Basics
```
plot(x, y, "r--", LineWidth=1)
title("Title text")
legend("Legend text")
xlabel("x label text")
ylabel("y label text")
```

To draw several plots in one picture
```
hold on
hold off
```

## Indexation
```
x = a(:, end-1)
```