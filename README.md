# MASA-Core
<p align="justify">
<b>Multi-Platform Architecture for Sequence Aligner (MASA)</b> is a flexible software framework that simplifies the creation of DNA sequence alignment applications in multiple hardware/software platforms. This framework supports the alignment of huge DNA sequences with more than 200 million base pairs (MBP). We intend to release its source code soon.
</p>

<img src="https://raw.githubusercontent.com/edanssandes/masa-core/master/images/masa-core-puzzle.png" align="left" height="180" hspace="50">

<p align="justify">
The MASA-Core library is based on CUDAlign, that is a tool able to align huge sequences in CUDA capable GPUs. The MASA-Core contains 90% of the original CUDAlign source code, isolating the platform-independent features. Thus, any developer may create "aligners" for different hardware/software platforms, reimplementing only 10% (or even less) of the original code and linking it against the portable MASA-Core library. Furthermore, new platform-independet optimizations may be deployed into the MASA-Core, leading to a wider contribution to all the specific aligners implementations. Platform-specific aligners will be maintained in separate repositories, with a static copy of the masa-core source.
</p>

The MASA-Core contains the following main features:
* Full Alignment for huge sequences (we successfully aligned sequences with more than 200 MBP);
* Multi-node support [CCGRID2014] with heterogeneous platforms [PPOPP2014];
* Block Pruning optimization [TPDS2012];
* Local, Semi-Global and Global Alignments;
* OpenMP support for parallel block processing;


---

## References:

* [CCGRID2014] Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé: CUDAlign 3.0: Parallel Biological Sequence Comparison in Large GPU Clusters. CCGRID 2014:160-169
* [PPOPP2014]  Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé: Fine-grain parallel megabase sequence comparison with multiple heterogeneous GPUs. PPOPP 2014:383-384
* [TPDS2013]   Edans Sandes, Alba Melo: Retrieving Smith-Waterman Alignments with Optimizations for Megabase Biological Sequences using GPU. IEEE Transactions on Parallel and Distributed Systems, vol 24, issue 5, 1009-1021
* [PPOPP2012]  Edans Sandes, Alba Melo: CUDAlign: using GPU to accelerate the comparison of megabase genomic sequences. PPOPP 2010: 137-146
* [IPDPS2011]  Edans Sandes, Alba Melo: Smith-Waterman Alignment of Huge Sequences with GPU in Linear Space. IPDPS 2011: 1199-1211
