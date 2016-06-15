# MASA-Core
<p align="justify">
<b>Multi-Platform Architecture for Sequence Aligner (MASA)</b> is a flexible software framework that simplifies the creation of DNA sequence alignment applications in multiple hardware/software platforms. This framework supports the alignment of huge DNA sequences with more than 200 million base pairs (MBP). 
</p>

<img src="https://raw.githubusercontent.com/edanssandes/masa-core/master/images/masa-core-puzzle.png" align="left" height="180" hspace="50">

<p align="justify">
The MASA-Core library is based on CUDAlign, a tool able to align huge sequences in CUDA capable GPUs. The MASA-Core contains 90% of the original CUDAlign source code, isolating the platform-independent features. Thus, any developer may create "aligners" for different hardware/software platforms, reimplementing only some methods of the original code and linking it against the portable MASA-Core library. Furthermore, new platform-independent optimizations may be deployed into the MASA-Core, leading to a wider contribution to all the specific aligners implementations. Platform-specific aligners will be maintained in separate repositories, with a static copy of the masa-core source.
</p>

### Main Features:

The MASA-Core contains the following features:
* Produces optimal alignments for DNA sequences of any length (even greater than 200 MBP)
* Based on Smith-Waterman and Needleman-Wunsch algorithms
* Uses Myers-Miller strategy during the matrix computation (linear memory complexity)<sup>[IPDPS2011](#references)</sup>
* Produces Local, Semi-Global and Global optimal alignments
* Multi-node support for homogeneous<sup>[CCGRID2014](#references)</sup> and heterogeneous hardware<sup>[PPOPP2014](#references)</sup>
* Block Pruning optimization<sup>[TPDS2012](#references)</sup>
* Portable C/C++ code. Compiled in Linux and MacOS X, for 32 and 64 bit platforms

### Download

Latest Version: [masa-core-1.3.9.1024.tar.gz](releases/masa-core-1.3.9.1024.tar.gz?raw=true)

### Compiling the static library (libmasa.a)

```
tar -xvzf masa-core-1.3.9.1024.tar.gz
cd masa-core-1.3.9.1024
./configure
make
```
To create MASA executable files, download one of the extensions listed below. Each extensions project contains a copy of the MASA-Core source.


### Supported Platforms:

Each project that supplies a different Aligner linked with MASA-Core is called a MASA-Extension. Here is a list with some MASA-Extensions for some supported platforms.
* [**MASA-CUDAlign**](https://github.com/edanssandes/MASA-CUDAlign): Extension that uses [CUDA](http://www.nvidia.com/object/cuda_home_new.html) NVidia GPUs (based on the original CUDAlign code)
* [**MASA-OpenMP**](https://github.com/edanssandes/MASA-OpenMP): Uses [OpenMP](http://openmp.org/) to computes many blocks in parallel using CPU or Intel Phi cores
* [**MASA-OmpSs**](https://github.com/edanssandes/MASA-OmpSs): Uses [OmpSs](https://pm.bsc.es/ompss) to run parallel tasks respecting dependencies
* [**MASA-Serial**](https://github.com/edanssandes/MASA-Serial): This is a simple extension that runs with serial CPU code


### Executing a MASA extension

```
./masa-extension [options] seq1.fasta seq2.fasta
```
All the command line arguments can be retrieved using the --help parameter. See the [wiki](https://github.com/edanssandes/MASA-Core/wiki/Command-line-examples) for a list of command line examples.

### Documentation

See the [doxygen](http://edanssandes.github.io/MASA-Core/docs) pages.

### License:

MASA-Core is an open source project with public license (GPLv3). A copy of the [LICENSE](https://raw.githubusercontent.com/edanssandes/masa-core/master/LICENSE) is maintained in this repository.

---

### References:

<table border="0">
<tr>
<td><a href="http://dx.doi.org/10.1145/2858656"><font size=1>[TOPC2016]</font></a></td>
<td><sub>MASA: a Multi-Platform Architecture for Sequence Aligners with Block Pruning. TOPC:2(4):28. Edans Sandes, Guillermo Miranda, Xavier Martorell, Eduard Ayguadé, George Teodoro, Alba Melo.
</tr>
<tr>
<td><a href="http://dx.doi.org/10.1109/TPDS.2016.2515597"><font size=1>[TPDS2016]</font></a></td>
<td><sub>Genome Wide Alignment in GPU Cluster with Incremental Speculative Traceback. TPDS 2016. Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé.</sub>
</td>
</tr>
<tr>
<td><a href="http://dx.doi.org/10.1109/CCGrid.2014.18"><font size=1>[CCGRID2014]</font></a></td>
<td><sub>CUDAlign 3.0: Parallel Biological Sequence Comparison in Large GPU Clusters. CCGRID 2014:160-169. Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé.</sub>
</td>
</tr>
<tr>
<td><a href="http://dx.doi.org/10.1145/2555243.2555280"><font size=1>[PPOPP2014]</font></a></td>
<td><sub>Fine-grain parallel megabase sequence comparison with multiple heterogeneous GPUs. PPOPP 2014:383-384. Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé
</sub></td>
</tr>
<tr>
<td><a href="http://dx.doi.org/10.1109/TPDS.2012.194"><font size=1>[TPDS2013]</font></a></td>
<td><sub>Retrieving Smith-Waterman Alignments with Optimizations for Megabase Biological Sequences using GPU. TPDS:24:5:1009-1021. Edans Sandes, Alba Melo</sub></td>
<tr>
<td><a href="http://dx.doi.org/10.1109/IPDPS.2011.114"><font size=1>[IPDPS2011]</font></a></td>
<td><sub>Smith-Waterman Alignment of Huge Sequences with GPU in Linear Space. IPDPS 2011: 1199-1211. Edans Sandes, Alba Melo</sub></td>
</tr>
</tr>
<td><a href="http://dx.doi.org/10.1145/1693453.1693473"><font size=1>[PPOPP2010]</font></a></td>
<td><sub>CUDAlign: using GPU to accelerate the comparison of megabase genomic sequences. PPOPP 2010: 137-146. Edans Sandes, Alba Melo</sub></td>
</tr>
</table>
