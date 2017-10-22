# Compilation Chain

## CMake

### Add define
```
In CMakeLists.txt
ADD_DEFINITIONS(-DLOCAL_BUILD=1)
```

## Makefile

### Don't stop on error
```
-mv file1 file2
```

### Don't print error on line
```
@mv file1 file2
-@mv file1 file2 # Can combine both
```

### Disable the output print of a command
```
@ devant la commande
```

### Use the result of a shell command (as a variable)
```
 $(shell <command>)
```

### Get all the files depending a specific pattern
```
 $(wildcard *.c)
```

### Get all the files recursively
```
 $(shell find <location> -type f -name '*.c')
```

### Replace an occurrence
```
$(patsubst pattern_from, pattern_to, text)
```

### Take each value in values and load action with value
```
$(foreach var, values, action)
# Note: action contains $(var)
```

### Makefile function
```
$(call func,param1,param2 ...)
# Note: func is an object like func=
```

## GCC

### Add define
```
g++ -D<blabla> <rest>
```
