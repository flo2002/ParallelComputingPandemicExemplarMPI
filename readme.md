# A Parallel Computing roject

# Get started
`make`<br>
`make run` or `mpirun -np 6 ./Pandemic.c-mpi` <br>
if you change something: make sure to use `make clean` and then run it

# Experiments
## PandemicWithRandomInfections 
The idea in this experiment is that people also can get infected by contact to objects of infected people. (or some other influence we cannot see here) So, people could also get infected randomly (without contact).
To add this to this scenario the last part of the `susceptible` method in `Core.h` was added:
```
if((random() % 100000) <= 1) 
{
    // The thread changes person1’s state to infected
    our_states[my_current_person_id] = INFECTED;
    // The thread updates the counters
    our->our_num_infected++;
    our->our_num_susceptible--;
    // The thread updates stats counter
    #ifdef SHOW_RESULTS
    stats->our_num_infections++;
    #endif
}
```


# Notes
- Changed screen size in: `Defaults.h` from 30 to 70 in: `DEFAULT_ENVIRO_SIZE`


# Resources
- Original Project: https://selkie.macalester.edu/csinparallel/modules/PandemicWithMPI/build/html/index.html
- Display with WSL2: https://stackoverflow.com/questions/61110603/how-to-set-up-working-x11-forwarding-on-wsl2

