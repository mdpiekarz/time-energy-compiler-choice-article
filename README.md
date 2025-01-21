# time-energy-compiler-choice-article
The repository contains experimental data for the article: "Importance of C/C++ compiler choice for performance and energy consumption of multithreaded WZ factorization"
====

Testing was conducted on a system equipped with two Intel® Xeon® Gold 5218R processors, each containing 20 cores. The evaluation encompassed the multithreaded WZ factorization, implemented both without optimization techniques and with strip-mining. The experiments were executed using the DVFS technique across various clock speeds and with different compilers.

The `basic`` and basic-sm` directories contain the experimental results of WZ factoring algorithms without optimization techniques and with strip-mining, respectively. Within each directory, there are subdirectories for GCC, ICC, and OneAPI compilers, presenting results for GCC compiler, Intel ICC, and Intel OneAPI, respectively. Each compiler subdirectory includes experiments conducted at clock frequencies of 0.8 GHz, 1.0 GHz, 1.2 GHz, 1.4 GHz, 1.6 GHz, 1.8 GHz, 2.0 GHz, and 2.1 GHz, located in subdirectories labeled `f800`, `f1000`, `f1200`, `f1400`, `f1600`, `f1800`, `f2000`, and `f2100`, respectively. Each frequency is tested five times, with test results for a single experiment located in subdirectories labeled with sample numbers "1", "2", "3", "4", and "5".

In the directory with a single experiment there is a file with energy data (measurement was performed every second and saved in subsequent lines): `energy1` contains measurements of the algorithm's performance with 40 threads running for matrix size nxn, n=32768 . In the next columns we have: sequence number (`n`), timestamp (`timestamp`), energy consumed by 1 processor in joules (`:0/package-0/CumulEn[J]`), current processor power consumption of the first processor in watts (`:0/package- 0/InstPow[W]`), memory power consumption of the first processor (`:0:0/dram/CumulEn[J]`), instantaneous memory power consumption of the first processor (`: 0:0/dram/InstPow[W]`), the next 4 columns describe the data for the second processor in a similar way.
Additionally, in the single test directory there is a file `t_40_n_32768__S` with the start and stop timestamps of the algorithms, in the case of `basic-sm` for blocks 128, 256 and 512, respectively.
In the directory with a single test there is also a file `t_40_n_32768__T` with the running time of the algorithms.
In some cases, in the `f***` directories there is a `energy.zip` file containing energy measurements for all 5 repetitions of the same test.

Data for Intel Xeon Platinum 8358 and AMD EPYC 9654 Processors
The results for Intel Xeon Platinum and AMD EPYC processors are stored in directories named `IntelXeonPlatinum` and `AMDEPYC`, respectively. These directories follow the same structure described above for Intel Xeon Gold, providing results for analogous experiments across compilers, clock speeds, and test repetitions.


