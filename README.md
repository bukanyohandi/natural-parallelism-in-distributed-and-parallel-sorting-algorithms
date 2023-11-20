Sorting algorithms are of great importance in computer science. Traditionally taught in data structure and algorithm courses, these algorithms have been foundational in organizing and managing data. However, the advent of multi-core processors and distributed computing brings a new dimension to these algorithms: the possibility of running them in parallel on multi-core CPUs or even distributing them across a computing cluster. This transition from a sequential to a parallel and distributed environment poses unique challenges. It is not just about sorting data efficiently but also about how to divide the entire task into different threads or processes. Moreover, in a distributed and parallel setting, the work of different threads or processes is no longer independent. This necessitates a sophisticated approach where these units must communicate with each other to synchronize their states and ensure the correctness of the algorithms.

The objective of this project is to explore the implementation of distributed and parallel sorting algorithms using the Message Passing Interface (MPI). It seeks to adapt classic sorting algorithms, traditionally executed in a sequential manner, into their parallel counterparts, thereby harnessing the computational power of multi-core and distributed systems. This entails addressing the complexities inherent in parallel computing, such as task division, inter-process communication, and data synchronization. The aim is to not only achieve an improvement in sorting performance but also to gain deeper insights into the nuances of parallel and distributed computing. This project is an opportunity to expand our understanding of how traditional algorithms can be transformed and optimized in a modern
computing paradigm.

Within the submitted zip file, a folder project can be found, this will be the main project folder.
1. Navigate to the folder
2. Run `run.sh` or simply paste the below sequence of commands:
```
scancel -u 120040025
mkdir build
cd build
cmake ..
make - j4
cd ..
sbatch sbatch.sh
sbatch sbatch-perf.sh
squeue -o "%.18i %.9P %.25j %.9u %.2t %.10M %.6D %R"
```

By default, the above commands will execute each of the sorting algorithms with a randomized vector sizing $10^8$, except for Odd-Even Sort for which the vector size is $2 \cddot 10^5$. If one wish to test other size of vectors, one can simply modify the appropriate scripts located in sbatch.sh . It is suggested to put few extension for the submitted batch job (at least 12 minutes). Upon completion, one can find out the correctness report along with the execution time of the sorting algorithm in the same directory.
