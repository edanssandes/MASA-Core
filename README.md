# MASA-Core
**Multi-Platform Architecture for Sequence Aligner (MASA)** is a flexible software framework that simplifies the creation of DNA sequence alignment applications in multiple hardware/software platforms. This framework supports the alignment of huge DNA sequences with more than 200 million base pairs (MBP). We intend to release its source code soon.

The MASA-Core library is based on CUDAlign, that is a tool able to align huge sequences in CUDA capable GPUs. The MASA-Core contains 90% of the original CUDAlign source code, with only the platform-independent features. Thus, any developer may create "aligners" for different hardware/software platforms, reimplementing only 10% (or less) of the platform-specific code and linking against the portable MASA-Core library. Furthermore, platform-independet optimizations in the MASA-Core can be applied to all the specific aligners implementation, leading to a wider contribution. Platform-specific aligners will be maintained in separate repositories, with a static copy of the masa-core.

The MASA-Core contains the following main features:
* Full Alignment for huge sequences (we successfully aligned sequences with more than 200 MBP);
* Multi-node support [CCGRID2014] with heterogeneous platforms [PPOPP2014];
* Block Pruning optimization [TPDS2012];
* Local, Semi-Global and Global Alignments;
* OpenMP support for parallel block processing;




References:


* [CCGRID2014] Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé: CUDAlign 3.0: Parallel Biological Sequence Comparison in Large GPU Clusters. CCGRID 2014:160-169</font>
* [PPOPP2014]  Edans Sandes, Guillermo Miranda, Alba Melo, Xavier Martorell, Eduard Ayguadé: Fine-grain parallel megabase sequence comparison with multiple heterogeneous GPUs. PPOPP 2014:383-384
* [TPDS2012]   Edans Sandes, Alba Melo: Retrieving Smith-Waterman Alignments with Optimizations for Megabase Biological Sequences using GPU. IEEE Transactions on Parallel and Distributed Systems, vol. 99, PrePrints, 2012
* [IPDPS2011]  Edans Sandes, Alba Melo: Smith-Waterman Alignment of Huge Sequences with GPU in Linear Space. IPDPS 2011: 1199-1211
* [PPOPP2012]  Edans Sandes, Alba Melo: CUDAlign: using GPU to accelerate the comparison of megabase genomic sequences. PPOPP 2010: 137-146
