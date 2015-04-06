# MASA-Core
<p align="justify">
<b>Multi-Platform Architecture for Sequence Aligner (MASA)</b> is a flexible software framework that simplifies the creation of DNA sequence alignment applications in multiple hardware/software platforms. This framework supports the alignment of huge DNA sequences with more than 200 million base pairs (MBP). We intend to release its source code soon.
</p>

<img src="https://raw.githubusercontent.com/edanssandes/masa-core/master/images/masa-core-puzzle.png" align="left" height="180" hspace="50">

<p align="justify">
The MASA-Core library is based on CUDAlign, that is a tool able to align huge sequences in CUDA capable GPUs. The MASA-Core contains 90% of the original CUDAlign source code, isolating the platform-independent features. Thus, any developer may create "aligners" for different hardware/software platforms, reimplementing only 10% (or even less) of the original code and linking it against the portable MASA-Core library. Furthermore, new platform-independet optimizations may be deployed into the MASA-Core, leading to a wider contribution to all the specific aligners implementations. Platform-specific aligners will be maintained in separate repositories, with a static copy of the masa-core source.
</p>

### Features:

The MASA-Core contains the following main features:
* Produces optimal alignments for DNA sequences of any length (even greater than 200 MBP);
* Local, Semi-Global and Global alignment types;
* Multi-node support for homogeneous [CCGRID2014] and heterogeneous hardware [PPOPP2014];
* Block Pruning optimization [TPDS2012];
* Portable C/C++ code. Compiled in Linux and MacOS X, for 32 and 64 bit platforms.

### Supported Platforms:

Each project that supplies a different Aligner linked with MASA-Core is called a MASA-Extension. Here is a list with some MASA-Extensions for some supported platforms.
* **MASA-Serial**: This is a simple extension that runs with serial CPU code.
* **MASA-CUDAlign**: Extension that uses CUDA NVidia GPUs (based on the original CUDAlign code) 
* **MASA-OpenMP**: Uses OpenMP to computes many blocks in parallel using CPU or Intel Phi cores.
* **MASA-OmpSs**: Uses the OmpSs programming model to runs parallel tasks with data dependencies.

### License:

MASA-Core is an open source project with public license (GPLv3). A copy of the [LICENSE](https://raw.githubusercontent.com/edanssandes/masa-core/master/LICENSE) is maintained in this repository. 

---

### References:

<table border="0">
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
</tr>
<td><a href="http://dx.doi.org/10.1145/1693453.1693473"><font size=1>[PPOPP2012]</font></a></td>
<td><sub>CUDAlign: using GPU to accelerate the comparison of megabase genomic sequences. PPOPP 2010: 137-146. Edans Sandes, Alba Melo</sub></td>
</tr>
<tr>
<td><a href="http://dx.doi.org/10.1109/IPDPS.2011.114"><font size=1>[IPDPS2011]</font></a></td>
<td><sub>Smith-Waterman Alignment of Huge Sequences with GPU in Linear Space. IPDPS 2011: 1199-1211. Edans Sandes, Alba Melo</sub></td>
</tr>
</table>
