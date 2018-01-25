# Example Makefiles

## Table

### Basic 
1.1:    Simple, direct compile command
1.2:    adds macros
1.3:    uses wildcards to compile objs
1.4:    modifying headers leads to recompiling source; header is a dependency
1.5:    seperate files into folders; Makefile in src/
1.6:    seperate folders; Makefile in top level dir

### Sharedlib
2.1:    Compile shared library
2.2:    Compile .so, then compile executable linked against .so
