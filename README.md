# Polychronization: Computation With Spikes

*Neural Computation* (2006) 18:245-282

Eugene M. Izhikevich

*The Neurosciences Institute,*
*10640 John Jay Hopkins Drive,*
*San Diego, CA, 92121.*

## Abstract

We present a minimal spiking network that can polychronize, i.e., exhibit reproducible time-locked but not synchronous firing patterns with millisecond precision, as in synfire braids. The network consists of cortical spiking neurons with axonal conduction delays and spike-timing-dependent plasticity (STDP); a ready-to-use MATLAB [program](http://www.izhikevich.org/publications/spnet.m) and C++ [program](http://www.izhikevich.org/publications/spnet.cpp) code is included. It exhibits sleep-like oscillations, gamma (40 Hz) rhythms, conversion of firing rates to spike-timings, and other interesting regimes. Due to the interplay between the delays and STDP, the spiking neurons spontaneously self-organize into groups and generate patterns of stereotypical polychronous activity. To our surprise, the number of co-existing polychronous groups far exceeds the number of neurons in the network, resulting in an unprecedented memory capacity of the system. We speculate on the significance of polychrony to the theory of neuronal group selection (TNGS, Neural Darwinism), cognitive neural computations, binding and gamma rhythm, mechanisms of attention, and consciousness as "attention to memories".

Full text in [PDF file](http://www.izhikevich.org/publications/spnet.pdf).

## Files for simulation

### Simulation files:

- [spnet.m](http://www.izhikevich.org/publications/spnet.m) - MATLAB program to simulate the dynamics of spiking network with delays and STDP
- [spnet.cpp](http://www.izhikevich.org/publications/spnet.cpp) - C program to simulate the dynamics of spiking network with delays and STDP

### Simulation files to explore polychronous groups:

- [spnet.m](http://www.izhikevich.org/publications/spnet.m) - the same as above
- [polygroup.m](http://www.izhikevich.org/publications/polygroup.m) - MATLAB file that finds a polychronous group starting with specified anchor neurons
- [polychron.m](http://www.izhikevich.org/publications/polychron.m) - MATLAB file that tries various anchor neurons and calls polygroup.m.
- [poly_spnet.cpp](http://www.izhikevich.org/publications/poly_spnet.cpp) - C program that combines all of the above MATLAB functionality

To find polychronous groups, first run spnet.m for sufficiently long period of time and then save the workspace in a file, e.g., write 'save 18000'. Then, use this file name in the program polychron.m to find all groups. Uncomment the line that shuffles excitatory->excitatory connections and run polychron.m again to see how many groups are expected by chance.

For example, the program spnet.m was run for 18000 seconds and the workspace was saved in the file [18000.mat](http://www.izhikevich.org/publications/18000.mat). Then, polychron.m found 1973 groups (only 211 for shuffled synapses). Using less stringent requirement for groups (i.e., setting min_group_path=6 in polychron.m) results in 6071 groups.

**Note:** The MATLAB and C programs are similar but not equivalent. MATLAB program misses some of the groups.

The quickest way to start is to download polychron.m, polygroup.m, and [18000.mat](http://www.izhikevich.org/publications/18000.mat) into the same folder. Then, run polychron.m and enjoy the show.

---

[home](http://www.izhikevich.org/index.htm)
[research](http://www.izhikevich.org/interest/index.htm)
[publications](http://www.izhikevich.org/publications/index.htm)
[cv](http://www.izhikevich.org/cv/index.htm)

---

2025-06-02: Converted README to Markdown.