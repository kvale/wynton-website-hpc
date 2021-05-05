<!--
WARNING: Do _not_ update this file; it is automatically generated from software-respository.md.rsp.
-->



# Software Repositories

In addition to the [core software] tools that are available by default, additional software is available via _environment modules_.  For example, although MATLAB is installed on the system, it is not available by default. Instead, we need to "load" its module first, e.g.

```sh
[alice@{{ site.devel.name }} ~]$ module load matlab
[alice@{{ site.devel.name }} ~]$ module list

Currently Loaded Modules:
  1) matlab/2020a
```
Then we can launch MATLAB using:
```sh
[alice@{{ site.devel.name }} ~]$ matlab -nosplash -nodesktop
```

To see what other "built-in" modules are available, use:

```sh
[alice@{{ site.devel.name }} ~]$ module avail
```


In additional a set of built-in environment modules, there are also modules for software tools that are installed and maintained by other users or research groups.  To access these, we first need to load the corresponding "Software Repository" module.  For example, to get access to the repository and the software shared by the UCSF Computation Biology and Informatics core (CBI), make sure to load ("enable") the repository first, e.g.

```sh
module load CBI
```

Then use `module avail` to list what modules and versions are available (or see below).  Next, to actually get access to one or more of the shared software modules, use `module load <name>` or `module load <name>/<version>`.  Here are a few examples:
```sh
module load bowtie2
module load bowtie2/2.2.6
module load r
```

It is possible to (i) enable a software repository and (ii) load a set of software tools in one call, e.g.
```sh
module load CBI r bwa bowtie2/2.2.6
```


Below are 3 software repositories, each providing a set of software tools.


<ul class="nav nav-pills">
  <li class="active"><a data-toggle="pill" href="#queues-built-in"><span style="font-weight: bold;">built-in</span>&nbsp;(7)</a></li>
  <li><a data-toggle="pill" href="#queues-CBI"><span style="font-weight: bold;">CBI</span>&nbsp;(65)</a></li>
  <li><a data-toggle="pill" href="#queues-Sali"><span style="font-weight: bold;">Sali</span>&nbsp;(118)</a></li>
</ul>

<div class="tab-content" style="margin-top: 1ex;">
<div id="queues-built-in" class="tab-pane fadein active">

<h2>Module Software Repository: built-in</h2>

Maintained by: {{ site.cluster.nickname }} Systems Administrators, <a href="{{ '/about/contact.html' | relative_url }}">{{ site.cluster.name }}</a><br>
Enable repository: <em>this software repository is always enabled</em><br>

<dl>
  <dt>amber</dt>
  <dd>
  Versions: <em>20</em><br>
  </dd>

  <dt>cuda</dt>
  <dd>
  Versions: 7.5, 8.0, 9.1, 9.2, 10.1, <em>11.0</em><br>
  </dd>

  <dt>julia</dt>
  <dd>
  Versions: 0.6.4, <em>1.6.0</em><br>
  </dd>

  <dt>matlab</dt>
  <dd>
  Versions: 2018b, 2019a, 2019b, 2020a, <em>2020b</em><br>
  </dd>

  <dt>matlab-runtime</dt>
  <dd>
  Versions: 2020a, <em>2020b</em><br>
  </dd>

  <dt>mpi</dt>
  <dd>
  Versions: openmpi-x86_64, <em>openmpi3-x86_64</em><br>
  </dd>

  <dt>openjdk</dt>
  <dd>
    <strong>openjdk-runtime: Open Java Development Kit</strong><br>
OpenJDK is a free and open-source implementation of the Java Platform, Standard Edition. It is the result of an effort Sun Microsystems began in 2006.<br>
    Example: <code>java -version</code> and <code>javac -version</code>.<br>
    URL: <a href="https://openjdk.java.net/">https://openjdk.java.net/</a><br>
  Versions: 1.8.0.282.b08-1, <em>11.0.10.0.9-0</em><br>
  </dd>

</dl>
</div> 

<div id="queues-CBI" class="tab-pane fade">

<h2>Module Software Repository: CBI</h2>

Maintained by: Henrik Bengtsson, <a href="http://cbi.ucsf.edu">Computational Biology and Informatics</a><br>
Enable repository: <code>module load CBI</code><br>

<div class="alert alert-warning" role="alert" style="margin-top: 3ex">
Please note that this software stacks is maintained and contributed by a research group on a voluntary basis. It is <em>not</em> maintained by the {{ site.cluster.name }} admins. Please reach out to the corresponding maintainer for bug reports, feedback, or questions.
</div>

<dl>
  <dt>asciigenome</dt>
  <dd>
    <strong>ASCIIGenome: Text Only Genome Viewer</strong><br>
ASCIIGenome is a genome browser based on command line interface and designed for running from console terminals. Since ASCIIGenome does not require a graphical interface it is particularly useful for quickly visualizing genomic data on remote servers while offering flexibility similar to popular GUI viewers like IGV.<br>
    Example: <code>ASCIIGenome --help</code>.<br>
    URL: <a href="https://github.com/dariober/ASCIIGenome">https://github.com/dariober/ASCIIGenome</a><br>
  Versions: 1.15.0, <em>1.16.0</em><br>
  </dd>

  <dt>bamutil</dt>
  <dd>
    <strong>bamUtil: Programs for Working on SAM/BAM Files</strong><br>
bamUtil is a repository that contains several programs that perform operations on SAM/BAM files. All of these programs are built into a single executable, <code>bam</code>.<br>
    Example: <code>bam help</code>.<br>
    URL: <a href="https://genome.sph.umich.edu/wiki/BamUtil">https://genome.sph.umich.edu/wiki/BamUtil</a>, <a href="https://github.com/statgen/bamUtil">https://github.com/statgen/bamUtil</a><br>
  Versions: <em>1.0.14</em><br>
  </dd>

  <dt>bat</dt>
  <dd>
    <strong>bat: A cat(1) Clone with Syntax Highlighting and Git Integration</strong><br>
A cat(1) clone with syntax highlighting and Git integration.<br>
    Example: <code>bat README.md</code>, <code>bat scripts/*.sh</code>, and <code>bat src/*.c</code>.<br>
    URL: <a href="https://github.com/sharkdp/bat">https://github.com/sharkdp/bat</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>0.17.1</em><br>
  </dd>

  <dt>bcftools</dt>
  <dd>
    <strong>BCFtools: Utilities for Variant Calling and Manipulating VCFs and BCFs</strong><br>
BCFtools is a set of utilities that manipulate variant calls in the Variant Call Format (VCF) and its binary counterpart BCF. All commands work transparently with both VCFs and BCFs, both uncompressed and BGZF-compressed.<br>
    Example: <code>bcftools --version</code><br>
    URL: <a href="http://www.htslib.org/">http://www.htslib.org/</a><br>
  Versions: 1.9, 1.10, 1.11, <em>1.10.2</em><br>
  </dd>

  <dt>bcl2fastq</dt>
  <dd>
    <strong>bcl2fastq: Illumina Conversion Software</strong><br>
bcl2fastq Conversion Software both demultiplexes data and converts BCL files generated by Illumina sequencing systems to standard FASTQ file formats for downstream analysis.<br>
    Example: <code>bcl2fastq --version</code><br>
    URL: <a href="https://support.illumina.com/sequencing/sequencing_software/bcl2fastq-conversion-software.html">https://support.illumina.com/sequencing/sequencing_software/bcl2fastq-conversion-software.html</a><br>
  Versions: <em>2.20.0</em><br>
  </dd>

  <dt>bedops</dt>
  <dd>
    <strong>BEDOPS: The Fast, Highly Scalable and Easily-Parallelizable Genome Analysis Toolkit</strong><br>
BEDOPS is an open-source command-line toolkit that performs highly efficient and scalable Boolean and other set operations, statistical calculations, archiving, conversion and other management of genomic data of arbitrary scale. Tasks can be easily split by chromosome for distributing whole-genome analyses across a computational cluster.<br>
    Example: <code>bedops --version</code><br>
    URL: <a href="https://bedops.readthedocs.io/">https://bedops.readthedocs.io/</a>, <a href="https://github.com/bedops/bedops">https://github.com/bedops/bedops</a><br>
  Versions: 2.4.36, 2.4.37, 2.4.38, <em>2.4.39</em><br>
  </dd>

  <dt>bedtools2</dt>
  <dd>
    <strong>bedtools2: The Swiss Army Knife for Genome Arithmetic</strong><br>
Collectively, the bedtools utilities are a swiss-army knife of tools for a wide-range of genomics analysis tasks. The most widely-used tools enable genome arithmetic: that is, set theory on the genome. For example, bedtools allows one to intersect, merge, count, complement, and shuffle genomic intervals from multiple files in widely-used genomic file formats such as BAM, BED, GFF/GTF, VCF.<br>
    Example: <code>bedtools --version</code> and <code>ls $BEDTOOLS2_HOME/genomes/</code>.<br>
    URL: <a href="https://github.com/arq5x/bedtools2/">https://github.com/arq5x/bedtools2/</a><br>
  Versions: 2.28.0, 2.29.1, 2.29.2, <em>2.30.0</em><br>
  </dd>

  <dt>blast</dt>
  <dd>
    <strong>BLAST+: Basic Local Alignment Search Tool</strong><br>
BLAST finds regions of similarity between biological sequences. The program compares nucleotide or protein sequences to sequence databases and calculates the statistical significance.<br>
    Example: <code>blastx -version</code><br>
    URL: <a href="https://blast.ncbi.nlm.nih.gov/Blast.cgi">https://blast.ncbi.nlm.nih.gov/Blast.cgi</a><br>
  Versions: 2.9.0, 2.10.1, <em>2.11.0</em><br>
  </dd>

  <dt>blat</dt>
  <dd>
    <strong>BLAT: Fast Sequence Search Command Line Tool</strong><br>
BLAT - client and server combined into a single program, first building the index, then using the index, and then exiting.<br>
    Example: <code>blat</code><br>
    URL: <a href="https://genome.ucsc.edu/goldenPath/help/blatSpec.html">https://genome.ucsc.edu/goldenPath/help/blatSpec.html</a><br>
  Versions: <em>36x4</em><br>
  </dd>

  <dt>bowtie</dt>
  <dd>
    <strong>Bowtie: A Fast and Sensitive Gapped Read Aligner</strong><br>
Bowtie is an ultrafast, memory-efficient short read aligner.<br>
    Example: <code>bowtie --version</code> and <code>ls $BOWTIE_HOME/{genomes,indexes}</code><br>
    Note: This is Bowtie v1 - <em>not v2</em>.<br>
    URL: <a href="http://bowtie-bio.sourceforge.net/index.shtml">http://bowtie-bio.sourceforge.net/index.shtml</a><br>
  Versions: 1.2.3, <em>1.3.0</em><br>
  </dd>

  <dt>bowtie2</dt>
  <dd>
    <strong>Bowtie 2: A Fast and Sensitive Gapped Read Aligner</strong><br>
Bowtie 2 is an ultrafast and memory-efficient tool for aligning sequencing reads to long reference sequences.<br>
    Example: <code>bowtie2 --version</code><br>
    URL: <a href="http://bowtie-bio.sourceforge.net/bowtie2/index.shtml">http://bowtie-bio.sourceforge.net/bowtie2/index.shtml</a><br>
  Versions: 2.3.5, 2.3.5.1, 2.4.1, <em>2.4.2</em><br>
  </dd>

  <dt>bwa</dt>
  <dd>
    <strong>BWA: Burrows-Wheeler Aligner</strong><br>
Burrows-Wheeler Aligner (BWA) is a software package for mapping low-divergent sequences against a large reference genome, such as the human genome.<br>
    Example: <code>bwa</code>.<br>
    URL: <a href="http://bio-bwa.sourceforge.net/">http://bio-bwa.sourceforge.net/</a><br>
  Versions: <em>0.7.17</em><br>
  </dd>

  <dt>byobu</dt>
  <dd>
    <strong>byobu: Elegant Enhancement of the Otherwise Functional, Plain, Practical GNU Screen</strong><br>
Byobu is an elegant enhancement of the otherwise functional, plain, practical GNU Screen. Byobu includes an enhanced profile, configuration utilities, and system status notifications for the GNU screen window manager as well as the Tmux terminal multiplexer.<br>
    Example: <code>byobu --version</code>.<br>
    URL: <a href="http://byobu.org">http://byobu.org</a>, <a href="https://github.com/dustinkirkland/byobu">https://github.com/dustinkirkland/byobu</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>5.133</em><br>
  </dd>

  <dt>CBI-testing</dt>
  <dd>
    <strong>The Computational Biology and Informatics (CBI) Software Repository - TESTING ONLY!</strong><br>
This repository provides prototypical environment modules that can change at any time. They will live in this CBI-testing repository until they have proven to work and be stable - only then they will be considered for the main CBI repository.  WARNING: Use at your own risk.<br>
    URL: <a href="http://cbi.ucsf.edu/">http://cbi.ucsf.edu/</a><br>
  Versions: <br>
  </dd>

  <dt>cellranger</dt>
  <dd>
    <strong>Cell Ranger: 10x Genomics Pipeline for Single-Cell Data Analysis</strong><br>
Cell Ranger is a set of analysis pipelines that process Chromium Single Cell 3' RNA-seq output to align reads, generate gene-cell matrices and perform clustering and gene expression analysis.<br>
    Example: <code>cellranger</code>.<br>
    URL: <a href="https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/what-is-cell-ranger">https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/what-is-cell-ranger</a><br>
    Warning: To prevent a single Cell Ranger process from hijacking all CPU and RAM by default, this module sets environment variable <code>MROFLAGS='--localcores=1 --localmem=8 --limit-loadavg'</code> making those the default.<br>
  Versions: 2.1.0, 3.0.2, 3.1.0, 4.0.0, <em>5.0.1</em><br>
  </dd>

  <dt>cmake</dt>
  <dd>
    <strong>CMake: Open-source, Cross-platform Family of Tools Designed to Build, Test and Package Software</strong><br>
CMake is cross-platform free and open-source software for managing the build process of software using a compiler-independent method. It supports directory hierarchies and applications that depend on multiple libraries.<br>
    Example: <code>cmake --version</code>.<br>
    URL: <a href="https://cmake.org/">https://cmake.org/</a><br>
  Versions: 3.18.2, <em>3.19.2</em><br>
  </dd>

  <dt>control-freec</dt>
  <dd>
    <strong>Control FREEC: Control-FREE Copy Number and Genotype Caller</strong><br>
Prediction of copy numbers and allelic content using deep-sequencing data.<br>
    Example: <code>freec</code>.<br>
    URL: <a href="http://boevalab.com/FREEC/">http://boevalab.com/FREEC/</a>, <a href="https://github.com/BoevaLab/FREEC/">https://github.com/BoevaLab/FREEC/</a><br>
  Versions: 11.5, <em>11.6</em><br>
  </dd>

  <dt>cufflinks</dt>
  <dd>
    <strong>Cufflinks: Transcriptome Assembly and Differential Expression Analysis for RNA-Seq</strong><br>
Cufflinks assembles transcripts, estimates their abundances, and tests for differential expression and regulation in RNA-Seq samples. It accepts aligned RNA-Seq reads and assembles the alignments into a parsimonious set of transcripts. Cufflinks then estimates the relative abundances of these transcripts based on how many reads support each one, taking into account biases in library preparation protocols.<br>
    Example: <code>cufflinks</code>.<br>
    URL: <a href="http://cole-trapnell-lab.github.io/cufflinks/">http://cole-trapnell-lab.github.io/cufflinks/</a>, <a href="https://github.com/cole-trapnell-lab/cufflinks">https://github.com/cole-trapnell-lab/cufflinks</a><br>
  Versions: <em>2.2.1</em><br>
  </dd>

  <dt>emacs</dt>
  <dd>
    <strong>GNU Emacs: An Extensible, Customizable, Free/Libre Text Editor</strong><br>
At its core is an interpreter for Emacs Lisp, a dialect of the Lisp programming language with extensions to support text editing.<br>
    Example: <code>emacs --version</code> and <code>emacs -nw</code>.<br>
    URL: <a href="https://www.gnu.org/software/emacs/">https://www.gnu.org/software/emacs/</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: 26.3, <em>27.1</em><br>
  </dd>

  <dt>fastqc</dt>
  <dd>
    <strong>FastQC: A Quality Control Analysis Tool for High Throughput Sequencing Data</strong><br>
FastQC is a program designed to spot potential problems in high througput sequencing datasets. It runs a set of analyses on one or more raw sequence files in fastq or bam format and produces a report which summarises the results.<br>
    Example: <code>fastqc --version</code>.<br>
    URL: <a href="https://www.bioinformatics.babraham.ac.uk/projects/download.html#fastqc">https://www.bioinformatics.babraham.ac.uk/projects/download.html#fastqc</a>, <a href="https://github.com/s-andrews/FastQC/">https://github.com/s-andrews/FastQC/</a><br>
  Versions: 0.11.8, <em>0.11.9</em><br>
  </dd>

  <dt>fzf</dt>
  <dd>
    <strong>fzf - A Command-Line Fuzzy Finder</strong><br>
fzf is a general-purpose command-line fuzzy finder. It's an interactive Unix filter for command-line that can be used with any list; files, command history, processes, hostnames, bookmarks, git commits, etc.<br>
    Example: <code>fzf --version</code> and <code>emacs &quot;$(fzf)&quot;</code>.<br>
    Note: To install tab completions and key bindinds to your shell, call <code>$FZF_HOME/install</code>. To uninstall, use <code>$FZF_HOME/uninstall</code>.<br>
    URL: <a href="https://github.com/junegunn/fzf">https://github.com/junegunn/fzf</a>, <a href="https://github.com/junegunn/fzf/wiki">https://github.com/junegunn/fzf/wiki</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: 0.22.0, <em>0.25.1</em><br>
  </dd>

  <dt>gatk</dt>
  <dd>
    <strong>Genome Analysis Toolkit (GATK): Variant Discovery in High-Throughput Sequencing Data</strong><br>
Developed in the Data Sciences Platform at the Broad Institute, the toolkit offers a wide variety of tools with a primary focus on variant discovery and genotyping. Its powerful processing engine and high-performance computing features make it capable of taking on projects of any size.<br>
    Example: <code>gatk --help</code> and <code>gatk --list</code>.<br>
    URL: <a href="https://software.broadinstitute.org/gatk/">https://software.broadinstitute.org/gatk/</a>, <a href="https://github.com/broadinstitute/gatk/">https://github.com/broadinstitute/gatk/</a><br>
  Versions: 4.1.0.0, 4.1.2.0, 4.1.3.0, 4.1.4.0, 4.1.6.0, 4.1.7.0, <em>4.1.9.0</em><br>
  </dd>

  <dt>gcta</dt>
  <dd>
    <strong>GCTA: Genome-wide Complex Trait Analysis</strong><br>
A tool for Genome-wide Complex Trait Analysis (GCTA).<br>
    Example: <code>gcta64</code>.<br>
    URL: <a href="http://cnsgenomics.com/software/gcta/">http://cnsgenomics.com/software/gcta/</a><br>
  Versions: 1.26.0, 1.92.3beta3, 1.92.4beta, <em>1.93.2beta</em><br>
  </dd>

  <dt>gdal</dt>
  <dd>
    <strong>GDAL: Geospatial Data Abstraction Library</strong><br>
GDAL is an open source X/MIT licensed translator library for raster and vector geospatial data formats.<br>
    Example: <code>gdalinfo --version</code><br>
    URL: <a href="https://gdal.org/">https://gdal.org/</a>, <a href="https://github.com/OSGeo/gdal">https://github.com/OSGeo/gdal</a><br>
  Versions: 2.4.3, <em>2.4.4</em><br>
  </dd>

  <dt>geos</dt>
  <dd>
    <strong>GEOS: Geometry Engine, Open Source</strong><br>
GEOS (Geometry Engine - Open Source) is a C++ port of the JTS Topology Suite (JTS). It aims to contain the complete functionality of JTS in C++. This includes all the OpenGIS Simple Features for SQL spatial predicate functions and spatial operators, as well as specific JTS enhanced functions. GEOS provides spatial functionality to many other projects and products.<br>
    Example: <code>geos-config --version</code>.<br>
    URL: <a href="https://trac.osgeo.org/geos/">https://trac.osgeo.org/geos/</a><br>
  Versions: 3.5.2, 3.7.3, 3.8.1, <em>3.9.1</em><br>
  </dd>

  <dt>git-flow</dt>
  <dd>
    <strong>git-flow: Git Extension Git Flow (AVH Edition)</strong><br>
A collection of Git extensions to provide high-level repository operations for Vincent Driessen's branching model.<br>
    Example: <code>git flow</code>.<br>
    URL: <a href="https://github.com/petervanderdoes/gitflow-avh">https://github.com/petervanderdoes/gitflow-avh</a>, <a href="https://github.com/nvie/gitflow">https://github.com/nvie/gitflow</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>1.12.3</em><br>
  </dd>

  <dt>glow</dt>
  <dd>
    <strong>glow: Render Markdown on the CLI, with Pizzazz!</strong><br>
Glow is a terminal based markdown reader designed from the ground up to bring out the beauty—and power—of the CLI.  Use it to discover markdown files, read documentation directly on the command line and stash markdown files to your own private collection so you can read them anywhere. Glow will find local markdown files in subdirectories or a local Git repository.<br>
    Example: <code>glow README.md</code>, <code>glow --pager README.md</code>.<br>
    URL: <a href="https://github.com/charmbracelet/glow">https://github.com/charmbracelet/glow</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>1.3.0</em><br>
  </dd>

  <dt>gsl</dt>
  <dd>
    <strong>GSL: Gnu Scientific Library</strong><br>
The GNU Scientific Library (GSL) is a numerical library for C and C++ programmers. It is free software under the GNU General Public License. The library provides a wide range of mathematical routines such as random number generators, special functions and least-squares fitting. There are over 1000 functions in total with an extensive test suite.<br>
    Example: <code>gsl-config --version</code><br>
    URL: <a href="https://www.gnu.org/software/gsl/">https://www.gnu.org/software/gsl/</a><br>
  Versions: <em>2.6</em><br>
  </dd>

  <dt>hdf5</dt>
  <dd>
    <strong>hdf5: A General Purpose Library and File Format for Storing Scientific Data</strong><br>
Hierarchical Data Format (HDF) is a set of file formats (HDF4, HDF5) designed to store and organize large amounts of data. The HDF5 format is designed to address some of the limitations of the HDF4 library, and to address current and anticipated requirements of modern systems and applications.<br>
    Example: <code>h5cc --version</code><br>
    URL: <a href="https://www.hdfgroup.org/downloads/hdf5/">https://www.hdfgroup.org/downloads/hdf5/</a><br>
  Versions: 1.10.6, <em>1.12.0</em><br>
  </dd>

  <dt>hisat2</dt>
  <dd>
    <strong>HISAT2: Graph-based Alignment of Next Generation Sequencing Reads to a Population of Genomes</strong><br>
HISAT2 is a fast and sensitive alignment program for mapping next-generation sequencing reads (both DNA and RNA) to a population of human genomes (as well as to a single reference genome). Based on an extension of BWT for graphs [Sirén et al. 2014], we designed and implemented a graph FM index (GFM), an original approach and its first implementation to the best of our knowledge. In addition to using one global GFM index that represents a population of human genomes, HISAT2 uses a large set of small GFM indexes that collectively cover the whole genome (each index representing a genomic region of 56 Kbp, with 55,000 indexes needed to cover the human population). These small indexes (called local indexes), combined with several alignment strategies, enable rapid and accurate alignment of sequencing reads. This new indexing scheme is called a Hierarchical Graph FM index (HGFM).<br>
    Example: <code>hisat2 --version</code>.<br>
    URL: <a href="https://daehwankimlab.github.io/hisat2/">https://daehwankimlab.github.io/hisat2/</a>, <a href="https://github.com/DaehwanKimLab/hisat2/">https://github.com/DaehwanKimLab/hisat2/</a><br>
  Versions: 2.1.0, <em>2.2.0</em><br>
  </dd>

  <dt>htop</dt>
  <dd>
    <strong>htop: An Interactive Process Viewer for Unix</strong><br>
<code>htop</code> is an interactive process viewer for Unix systems. It is a text-mode application (for console or X terminals) and requires ncurses.<br>
    Example: <code>htop</code>.<br>
    URL: <a href="https://htop.dev">https://htop.dev</a>, <a href="https://github.com/htop-dev/htop">https://github.com/htop-dev/htop</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: 3.0.4, <em>3.0.5</em><br>
  </dd>

  <dt>htslib</dt>
  <dd>
    <strong>HTSlib: C Library for High-Throughput Sequencing Data Formats</strong><br>
HTSlib is an implementation of a unified C library for accessing common file formats, such as SAM, CRAM and VCF, used for high-throughput sequencing data, and is the core library used by samtools and bcftools. HTSlib also provides the bgzip, htsfile, and tabix utilities.<br>
    Example: <code>bgzip --version</code>, <code>htsfile --version</code>, and <code>tabix --version</code>.<br>
    URL: <a href="http://www.htslib.org/">http://www.htslib.org/</a><br>
  Versions: 1.9, 1.11, <em>1.10.2</em><br>
  </dd>

  <dt>igv</dt>
  <dd>
    <strong>IGV: The Integrative Genomics Viewer</strong><br>
The Integrative Genomics Viewer (IGV) is a high-performance visualization tool for interactive exploration of large, integrated genomic datasets. It supports a wide variety of data types, including array-based and next-generation sequence data, and genomic annotations.<br>
    Example: <code>igv</code>.<br>
    Note: IGV (&gt;= 2.5.0) requires Java 11. Coincidentally, <code>igvtools</code> is integrated with IGV (&gt;= 2.5.0).<br>
    URL: <a href="https://software.broadinstitute.org/software/igv/">https://software.broadinstitute.org/software/igv/</a><br>
  Versions: 2.4.19, 2.7.0, 2.7.2, 2.8.2, 2.8.6, 2.8.13, <em>2.9.1</em><br>
  </dd>

  <dt>igvtools</dt>
  <dd>
    <strong>IGVTools: Tools for Pre-processing HT-Seq Data Files</strong><br>
The igvtools utility provides a set of tools for pre-processing data files. Note, <code>igvtools</code> moved to IGV as of IGV (&gt;= 2.5.0).<br>
    Example: <code>igvtools help</code>.<br>
    URL: <a href="https://software.broadinstitute.org/software/igv/igvtools">https://software.broadinstitute.org/software/igv/igvtools</a><br>
  Versions: <em>2.4.19</em><br>
  </dd>

  <dt>jags</dt>
  <dd>
    <strong>JAGS: Just Another Gibbs Sampler</strong><br>
JAGS is Just Another Gibbs Sampler.  It is a program for analysis of Bayesian hierarchical models using Markov Chain Monte Carlo (MCMC) simulation not wholly unlike BUGS.<br>
    Example: <code>jags</code> and <code>man jags</code>.<br>
    URL: <a href="http://mcmc-jags.sourceforge.net/">http://mcmc-jags.sourceforge.net/</a><br>
  Versions: <em>4.3.0</em><br>
  </dd>

  <dt>kallisto</dt>
  <dd>
    <strong>kallisto: Near-optimal RNA-Seq Quantification</strong><br>
kallisto is a program for quantifying abundances of transcripts from RNA-Seq data, or more generally of target sequences using high-throughput sequencing reads. It is based on the novel idea of pseudoalignment for rapidly determining the compatibility of reads with targets, without the need for alignment.<br>
    Example: <code>kallisto version</code>.<br>
    URL: <a href="https://pachterlab.github.io/kallisto/about.html">https://pachterlab.github.io/kallisto/about.html</a>, <a href="https://github.com/pachterlab/kallisto">https://github.com/pachterlab/kallisto</a><br>
  Versions: 0.45.0, 0.45.1, 0.46.0, 0.46.1, <em>0.46.2</em><br>
  </dd>

  <dt>mc</dt>
  <dd>
    <strong>mc: Midnight Commander</strong><br>
GNU Midnight Commander is a visual file manager. It's a feature rich full-screen text mode application that allows you to copy, move and delete files and whole directory trees, search for files and run commands in the subshell. Internal viewer and editor are included.<br>
    Example: <code>mc</code> and <code>mc --version</code>.<br>
    URL: <a href="http://www.midnight-commander.org/">http://www.midnight-commander.org/</a>, <a href="https://github.com/MidnightCommander/mc">https://github.com/MidnightCommander/mc</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>4.8.26</em><br>
  </dd>

  <dt>pandoc</dt>
  <dd>
    <strong>Pandoc: A Universal Document Converter</strong><br>
Pandoc is a Haskell library and software tool for converting from one markup format to another, and a command-line tool that uses this library.<br>
    Example: <code>pandoc --version</code>.<br>
    URL: <a href="https://pandoc.org/">https://pandoc.org/</a>, <a href="https://github.com/jgm/pandoc">https://github.com/jgm/pandoc</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>2.11.4</em><br>
  </dd>

  <dt>picard</dt>
  <dd>
    <strong>Picard: Command-line tools for Manipulating High-throughput Sequencing Data and Formats</strong><br>
Picard is a set of command line tools for manipulating high-throughput sequencing (HTS) data and formats such as SAM/BAM/CRAM and VCF.<br>
    Example: <code>picard -h</code>, which is an alias for <code>java -jar $PICARD_HOME/picard.jar -h</code><br>
    URL: <a href="http://broadinstitute.github.io/picard/">http://broadinstitute.github.io/picard/</a>, <a href="https://github.com/broadinstitute/picard">https://github.com/broadinstitute/picard</a><br>
  Versions: 2.21.1, 2.21.4, 2.22.2, 2.23.1, <em>2.24.0</em><br>
  </dd>

  <dt>pindel</dt>
  <dd>
    <strong>pindel: Detection of Indels and Structural Variations</strong><br>
Pindel can detect breakpoints of large deletions, medium sized insertions, inversions, tandem duplications and other structural variants at single-based resolution from next-gen sequence data. It uses a pattern growth approach to identify the breakpoints of these variants from paired-end short reads.<br>
    Example: <code>pindel</code>.<br>
    URL: <a href="https://www.sanger.ac.uk/science/tools/pindel">https://www.sanger.ac.uk/science/tools/pindel</a>, <a href="https://github.com/genome/pindel">https://github.com/genome/pindel</a><br>
  Versions: <em>0.2.5b8</em><br>
  </dd>

  <dt>plink</dt>
  <dd>
    <strong>PLINK: Whole Genome Association Analysis Toolset</strong><br>
PLINK is a free, open-source whole genome association analysis toolset, designed to perform a range of basic, large-scale analyses in a computationally efficient manner. The focus of PLINK is purely on analysis of genotype/phenotype data, so there is no support for steps prior to this (e.g. study design and planning, generating genotype or CNV calls from raw data).<br>
    Example: <code>plink --help</code>.<br>
    URL: <a href="https://www.cog-genomics.org/plink/">https://www.cog-genomics.org/plink/</a><br>
  Versions: 1.07, 1.90b6.10, 1.90b6.16, 1.90b6.18, <em>1.90b6.21</em><br>
  </dd>

  <dt>plink2</dt>
  <dd>
    <strong>PLINK2: Whole Genome Association Analysis Toolset</strong><br>
PLINK is a free, open-source whole genome association analysis toolset, designed to perform a range of basic, large-scale analyses in a computationally efficient manner. The focus of PLINK is purely on analysis of genotype/phenotype data, so there is no support for steps prior to this (e.g. study design and planning, generating genotype or CNV calls from raw data).<br>
    Example: <code>plink2 --help</code>.<br>
    URL: <a href="https://www.cog-genomics.org/plink/2.0/">https://www.cog-genomics.org/plink/2.0/</a>, <a href="https://github.com/chrchang/plink-ng">https://github.com/chrchang/plink-ng</a><br>
  Versions: 2.00a2LM, 2.00a2.3, <em>2.00a3LM</em><br>
  </dd>

  <dt>proj</dt>
  <dd>
    <strong>PROJ: PROJ Coordinate Transformation Software Library</strong><br>
PROJ is a generic coordinate transformation software that transforms geospatial coordinates from one coordinate reference system (CRS) to another. This includes cartographic projections as well as geodetic transformations. PROJ includes command line applications for easy conversion of coordinates from text files or directly from user input. In addition to the command line utilities PROJ also exposes an application programming interface, or API in short. The API lets developers use the functionality of PROJ in their own software without having to implement similar functionality themselves.<br>
    Example: <code>proj</code> and <code>man proj</code>.<br>
    URL: <a href="https://trac.osgeo.org/geos/">https://trac.osgeo.org/geos/</a><br>
  Versions: <em>4.9.3</em><br>
  </dd>

  <dt>qtop</dt>
  <dd>
    <strong>qtop: Monitor the State of Queueing Systems, Along with Related Information Relevant on HPC &amp; Grid Clusters</strong><br>
<code>qtop</code> (pronounced queue-top) is a tool written in order to monitor the state of Queueing Systems, along with related information relevant on HPC &amp; grid clusters. At present it supports PBS, SGE &amp; OAR families. Please help to increase that list in the Python version of the tool, qtop.py!<br>
    Example: <code>qtop</code> and <code>qtop -FGW</code>.<br>
    URL: <a href="https://github.com/qtop/qtop">https://github.com/qtop/qtop</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>0.9.20161222</em><br>
  </dd>

  <dt>r</dt>
  <dd>
    <strong>R: The R Programming Language</strong><br>
The R programming language.<br>
    Example: <code>R --version</code> and <code>Rscript --version</code>.<br>
    URL: <a href="https://www.r-project.org/">https://www.r-project.org/</a><br>
  Versions: 2.12.2, 2.13.0, 2.14.0, 2.15.0, 3.0.0, 3.1.0, 3.2.0, 3.3.0, 3.4.0, 3.5.0, 3.5.3, 3.6.0, 3.6.1, 3.6.2, 3.6.3, 4.0.0, 4.0.1, 4.0.2, 4.0.3, 4.0.4, <em>4.0.5</em><br>
  </dd>

  <dt>r-siteconfig</dt>
  <dd>
    <strong>R Site Configuration: Tweaks to R for the Current Compute Environment</strong><br>
Sets R options and environment variables customized for the current compute environment. Notably, it configures R to install packages from local CRAN and Bioconductor mirrors without the need for internet access.<br>
    Example: In R, <code>install.packages(&quot;ggplot2&quot;)</code>.<br>
  Versions: 0.1, <em>0.2</em><br>
  </dd>

  <dt>rclone</dt>
  <dd>
    <strong>rclone: Rsync for Cloud Storage and More</strong><br>
Rclone is a command line program to sync files and directories to and from a large number of end points on the local file system, or remote file systems, and in the cloud.<br>
    Example: <code>rclone --version</code>, <code>rclone --help</code>, <code>rclone config</code>, and <code>info rclone</code>.<br>
    URL: <a href="https://rclone.org/">https://rclone.org/</a>, <a href="https://github.com/rclone/rclone">https://github.com/rclone/rclone</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: 1.53.3, <em>1.54.0</em><br>
  </dd>

  <dt>ripgrep</dt>
  <dd>
    <strong>ripgrep - Recursively Searches Directories for a Regex Pattern</strong><br>
ripgrep is a line-oriented search tool that recursively searches your current directory for a regex pattern. By default, ripgrep will respect your .gitignore and automatically skip hidden files/directories and binary files. ripgrep is similar to other popular search tools like The Silver Searcher, ack and grep.<br>
    Example: <code>rg --version</code> and <code>rg -i 'lorem ipsum'</code>.<br>
    URL: <a href="https://github.com/BurntSushi/ripgrep">https://github.com/BurntSushi/ripgrep</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>12.1.1</em><br>
  </dd>

  <dt>rstudio</dt>
  <dd>
    <strong>rstudio: RStudio Desktop</strong><br>
The RStudio Desktop is an integrated development environment (IDE) for R, a programming language for statistical computing and graphics.<br>
    Example: <code>rstudio</code>. If you get blank window, retry with <code>QMLSCENE_DEVICE=softwarecontext rstudio</code>.<br>
    URL: <a href="https://rstudio.com/products/rstudio/#rstudio-desktop">https://rstudio.com/products/rstudio/#rstudio-desktop</a><br>
    Warning: This software works only on the development nodes and requires that X11 Forwarding or NX is enabled. For best performance, use SSH compression when using X11 Forwarding, i.e. <code>ssh -X -C ...</code>.<br>
  Versions: <em>1.4.1103</em><br>
  </dd>

  <dt>salmon</dt>
  <dd>
    <strong>salmon: Salmon Provides Fast and Bias-Aware Quantification of Transcript Expression</strong><br>
Highly-accurate &amp; wicked fast transcript-level quantification from RNA-seq reads using selective alignment.<br>
    Example: <code>salmon --version</code>.<br>
    URL: <a href="https://combine-lab.github.io/salmon/">https://combine-lab.github.io/salmon/</a>, <a href="https://github.com/COMBINE-lab/salmon">https://github.com/COMBINE-lab/salmon</a><br>
  Versions: 1.3.0, <em>1.4.0</em><br>
  </dd>

  <dt>samtools</dt>
  <dd>
    <strong>SAMtools: Tools (written in C using htslib) for Manipulating Next-Generation Sequencing Data</strong><br>
SAMtools is a suite of programs for interacting with high-throughput sequencing data.<br>
    Example: <code>samtools --version</code>.<br>
    URL: <a href="http://www.htslib.org/">http://www.htslib.org/</a><br>
  Versions: 1.9, 1.11, <em>1.10</em><br>
  </dd>

  <dt>scl-devtoolset</dt>
  <dd>
    <strong>SCL Developer Toolset: GNU Compiler Collection, GNU Debugger, etc.</strong><br>
Enables the CentOS Software Collection (SCL) <code>devtoolset-9</code> in the current environment.  This is an alternative to calling <code>source scl_source enable devtoolset-9</code>, which is an approach that is not officially supported by RedHat/CentOS.<br>
    Example: <code>gcc --version</code>.<br>
    URL: <a href="https://www.softwarecollections.org/en/scls/rhscl/devtoolset-9/">https://www.softwarecollections.org/en/scls/rhscl/devtoolset-9/</a><br>
  Versions: 4, 6, 7, 8, <em>9</em><br>
  </dd>

  <dt>scl-python (part of CBI-testing)</dt>
  <dd>
    <strong>SCL Python: Python with Additional Utilities via CentOS Software Collections [DEPRECATED]</strong><br>
Enables the CentOS Software Collection (SCL) <code>rh-python36</code> in the current environment.  This is an alternative to calling <code>source scl_source enable rh-python36</code>, which is not officially supported by RedHat/CentOS.<br>
    Example: <code>python --version</code> and <code>pip --version</code>.<br>
    URL: <a href="https://www.softwarecollections.org/en/scls/rhscl/rh-python36/">https://www.softwarecollections.org/en/scls/rhscl/rh-python36/</a><br>
    Warning: This module is DEPRECATED and should no longer be used because Python SCLs are deprecated, which in turn is because Python 3 is now available directly by CentOS.<br>
  Versions: 3.3, 3.4, <em>3.6</em><br>
    Note: <em>To use this module, call <code>module load CBI CBI-testing</code> first.</em>
  </dd>

  <dt>shellcheck</dt>
  <dd>
    <strong>ShellCheck: A Shell Script Static Analysis Tool</strong><br>
ShellCheck finds bugs in your shell scripts.<br>
    Example: <code>shellcheck --version</code> and <code>shellcheck -x ~/.bashrc</code>.<br>
    URL: <a href="https://www.shellcheck.net/">https://www.shellcheck.net/</a>, <a href="https://github.com/koalaman/shellcheck/">https://github.com/koalaman/shellcheck/</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>0.7.1</em><br>
  </dd>

  <dt>snpeff</dt>
  <dd>
    <strong>SnpEff: Genetic Variant Annotation and Effect Prediction Toolbox</strong><br>
SnpEff is a variant annotation and effect prediction tool. It annotates and predicts the effects of variants on genes (such as amino acid changes).<br>
    Example: <code>snpEff -help</code>, <code>SnpSift -help</code>,  and <code>ClinEff -help</code>, which are aliases for <code>java -jar $SNPEFF_HOME/snpEff/snpEff.jar -help</code>, <code>java -jar $SNPEFF_HOME/snpEff/SnpSift.jar -help</code>, and <code>java -jar $SNPEFF_HOME/clinEff/ClinEff.jar -help</code>.<br>
    URL: <a href="http://snpeff.sourceforge.net/">http://snpeff.sourceforge.net/</a><br>
  Versions: 4.3t, <em>5.0c</em><br>
  </dd>

  <dt>sratoolkit</dt>
  <dd>
    <strong>SRA Toolkit: Tools and Libraries for Using Data in the INSDC Sequence Read Archives</strong><br>
The SRA Toolkit and SDK from NCBI is a collection of tools and libraries for using data in the INSDC Sequence Read Archives.<br>
    Example: <code>fastq-dump --help</code>.<br>
    URL: <a href="https://ncbi.github.io/sra-tools/">https://ncbi.github.io/sra-tools/</a>, <a href="https://github.com/ncbi/sra-tools">https://github.com/ncbi/sra-tools</a><br>
    Warning: To work around a bug where <code>fasterq-dump</code> crashes the local machine, it has been tweaked such that it uses <code>$TMPDIR</code> rather than <code>$PWD</code> as the default temporary folder.<br>
  Versions: 2.10.0, 2.10.4, 2.10.5, 2.10.7, 2.10.8, 2.10.9, <em>2.11.0</em><br>
  </dd>

  <dt>star</dt>
  <dd>
    <strong>STAR: Spliced Transcripts Alignment to a Reference</strong><br>
STAR (Spliced Transcripts Alignment to a Reference) is a fast NGS read aligner for RNA-seq data.<br>
    Example: <code>STAR --help</code>.<br>
    URL: <a href="https://github.com/alexdobin/STAR">https://github.com/alexdobin/STAR</a><br>
  Versions: 2.7.0e, 2.7.0f, 2.7.1a, 2.7.2b, 2.7.3a, 2.7.5a, 2.7.5c, <em>2.7.7a</em><br>
  </dd>

  <dt>tmux</dt>
  <dd>
    <strong>tmux: A Terminal Multiplexer</strong><br>
tmux is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more.<br>
    Example: <code>tmux</code> and <code>man tmux</code>.<br>
    URL: <a href="https://github.com/tmux/tmux/wiki">https://github.com/tmux/tmux/wiki</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>2.8</em><br>
  </dd>

  <dt>tophat</dt>
  <dd>
    <strong>TopHat: A Spliced Read Mapper for RNA-Seq</strong><br>
TopHat is a fast splice junction mapper for RNA-Seq reads. It aligns RNA-Seq reads to mammalian-sized genomes using the ultra high-throughput short read aligner Bowtie, and then analyzes the mapping results to identify splice junctions between exons.<br>
    Example: <code>tophat --version</code>.<br>
    URL: <a href="https://ccb.jhu.edu/software/tophat/index.shtml">https://ccb.jhu.edu/software/tophat/index.shtml</a>, <a href="https://github.com/infphilo/tophat">https://github.com/infphilo/tophat</a><br>
  Versions: <em>2.1.1</em><br>
  </dd>

  <dt>tree</dt>
  <dd>
    <strong>tree: List Content of Directories in a Tree-like Format</strong><br>
Tree is a recursive directory listing command that produces a depth indented listing of files, which is colorized ala dircolors if the <code>LS_COLORS</code> environment variable is set and output is to tty.<br>
    Example: <code>tree --help</code>.<br>
    URL: <a href="http://mama.indstate.edu/users/ice/tree/">http://mama.indstate.edu/users/ice/tree/</a>,<br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>1.8.0</em><br>
  </dd>

  <dt>up</dt>
  <dd>
    <strong>up: The Ultimate Plumber</strong><br>
A tool for writing Linux pipes in a terminal-based UI interactively, with instant live preview of command results. Interactively and incrementally explore textual data in Linux using text-processing utils such as grep, sort, cut, paste, awk, wc, perl, etc.  When done, press Ctrl-C to view final pipe commands, or Ctrl-X to save it to file.<br>
    Example: <code>up --help</code>, <code>ls | up</code> (exit with Ctrl-C).<br>
    URL: <a href="https://github.com/akavel/up">https://github.com/akavel/up</a><br>
    Warning: Only the most recent version of this software will be kept.<br>
  Versions: <em>0.4</em><br>
  </dd>

  <dt>varscan</dt>
  <dd>
    <strong>VarScan: Variant Detection in Massively Parallel Sequencing Data</strong><br>
VarScan is a platform-independent mutation caller for targeted, exome, and whole-genome resequencing data generated on Illumina, SOLiD, Life/PGM, Roche/454, and similar instruments.<br>
    Example: <code>varscan</code>, which is an alias to <code>java -jar $VARSCAN_HOME/VarScan.jar</code>.<br>
    URL: <a href="https://dkoboldt.github.io/varscan/">https://dkoboldt.github.io/varscan/</a><br>
  Versions: <em>2.4.2</em><br>
  </dd>

  <dt>vcf-validator</dt>
  <dd>
    <strong>vcf-validator: Validation Suite for Variant Call Format (VCF) Files</strong><br>
Validator for the Variant Call Format (VCF) implemented using C++11. It includes all the checks from the vcftools suite, and some more that involve lexical, syntactic and semantic analysis of the VCF input.<br>
    Example: <code>vcf_validator --help</code>, <code>vcf-debugulator --help</code>, and <code>vcf-assembly-checker --help</code>.<br>
    URL: <a href="https://github.com/EBIvariation/vcf-validator">https://github.com/EBIvariation/vcf-validator</a><br>
  Versions: 0.9.2, 0.9.3, <em>0.9.4</em><br>
  </dd>

  <dt>vcftools</dt>
  <dd>
    <strong>VCFtools: Tools Written in Perl and C++ for Working with VCF Files</strong><br>
VCFtools is a program package designed for working with VCF files, such as those generated by the 1000 Genomes Project. The aim of VCFtools is to provide easily accessible methods for working with complex genetic variation data in the form of VCF files.<br>
    Example: <code>vcftools --version</code>.<br>
    URL: <a href="https://vcftools.github.io/">https://vcftools.github.io/</a><br>
  Versions: <em>0.1.16</em><br>
  </dd>

  <dt>wynton-tools (part of CBI-testing)</dt>
  <dd>
    <strong>Wynton Tools: Tools for the Wynton HPC Environment</strong><br>
A command-line tool for common Wynton HPC queries.<br>
    Example: <code>wynton --help</code>.<br>
    URL: <a href="https://github.com/UCSF-HPC/wynton-tools/">https://github.com/UCSF-HPC/wynton-tools/</a><br>
  Versions: <em>latest</em><br>
    Note: <em>To use this module, call <code>module load CBI CBI-testing</code> first.</em>
  </dd>

</dl>
</div> 

<div id="queues-Sali" class="tab-pane fade">

<h2>Module Software Repository: Sali</h2>

Maintained by: Ben Webb, <a href="https://salilab.org/">Sali Lab Software Repository</a><br>
Enable repository: <code>module load Sali</code><br>

<div class="alert alert-warning" role="alert" style="margin-top: 3ex">
Please note that this software stacks is maintained and contributed by a research group on a voluntary basis. It is <em>not</em> maintained by the {{ site.cluster.name }} admins. Please reach out to the corresponding maintainer for bug reports, feedback, or questions.
</div>

<dl>
  <dt>allosmod</dt>
  <dd>
AllosMod utility library<br>
    URL: <a href="https://github.com/salilab/allosmod-lib/">https://github.com/salilab/allosmod-lib/</a><br>
  Versions: <br>
  </dd>

  <dt>amber</dt>
  <dd>
Amber11, for 64-bit<br>
    URL: <a href="http://ambermd.org/">http://ambermd.org/</a><br>
  Versions: <em>11</em><br>
  </dd>

  <dt>anaconda</dt>
  <dd>
Anaconda Python distribution<br>
    URL: <a href="https://www.anaconda.com/">https://www.anaconda.com/</a><br>
  Versions: <br>
  </dd>

  <dt>blast</dt>
  <dd>
Basic Local Alignment Search Tool<br>
    URL: <a href="https://blast.ncbi.nlm.nih.gov">https://blast.ncbi.nlm.nih.gov</a><br>
  Versions: <em>2.2.26</em><br>
  </dd>

  <dt>blast+</dt>
  <dd>
Basic Local Alignment Search Tool<br>
    URL: <a href="https://blast.ncbi.nlm.nih.gov/">https://blast.ncbi.nlm.nih.gov/</a><br>
  Versions: 2.2.25, <em>2.2.28</em><br>
  </dd>

  <dt>boost (part of gcc/10.2.1)</dt>
  <dd>
The free peer-reviewed portable C++ source libraries<br>
    URL: <a href="https://www.boost.org/">https://www.boost.org/</a><br>
  Versions: 1.68.0, <em>1.73.0</em><br>
    Note: <em>To use this module, call <code>module load CBI CBI-testing</code> first.</em>
  </dd>

  <dt>cgal</dt>
  <dd>
Computational Geometry Algorithms Library<br>
    URL: <a href="https://www.cgal.org/">https://www.cgal.org/</a><br>
  Versions: 4.12.1, <em>5.1</em><br>
  </dd>

  <dt>cmake</dt>
  <dd>
Cross-platform make system<br>
    URL: <a href="https://cmake.org/">https://cmake.org/</a><br>
  Versions: 3.12.2, <em>3.18.3</em><br>
  </dd>

  <dt>concavity</dt>
  <dd>
Ligand binding site prediction from protein sequence and structure<br>
    URL: <a href="https://compbio.cs.princeton.edu/concavity/">https://compbio.cs.princeton.edu/concavity/</a><br>
  Versions: <em>0.1</em><br>
  </dd>

  <dt>cryptosite</dt>
  <dd>
CryptoSite utility library<br>
    URL: <a href="https://github.com/salilab/cryptosite/">https://github.com/salilab/cryptosite/</a><br>
  Versions: <br>
  </dd>

  <dt>cuda</dt>
  <dd>
NVIDIA CUDA Toolkit libraries<br>
    URL: <a href="https://developer.nvidia.com/cuda-downloads">https://developer.nvidia.com/cuda-downloads</a><br>
  Versions: 6.0.37, 7.5.18, 8.0.61, 9.0.176, <em>10.0.130</em><br>
  </dd>

  <dt>Cython</dt>
  <dd>
A language for writing Python extension modules<br>
    URL: <a href="https://cython.org/">https://cython.org/</a><br>
  Versions: 0.25.2, <em>0.29.14</em><br>
  </dd>

  <dt>doxygen</dt>
  <dd>
A documentation system for C/C++<br>
    URL: <a href="http://www.doxygen.org/index.html">http://www.doxygen.org/index.html</a><br>
  Versions: 1.8.6, <em>1.8.15</em><br>
  </dd>

  <dt>dssp</dt>
  <dd>
Secondary structure assignment<br>
    URL: <a href="https://swift.cmbi.umcn.nl/gv/dssp/">https://swift.cmbi.umcn.nl/gv/dssp/</a><br>
  Versions: 2.0.4, <em>2.2.1</em><br>
  </dd>

  <dt>eigen</dt>
  <dd>
A lightweight C++ template library for vector and matrix math<br>
    URL: <a href="http://eigen.tuxfamily.org">http://eigen.tuxfamily.org</a><br>
  Versions: <em>3.3.5</em><br>
  </dd>

  <dt>eman</dt>
  <dd>
Single Particle Analysis and Electron Micrograph Analysis<br>
    URL: <a href="https://blake.bcm.edu/emanwiki/EMAN2">https://blake.bcm.edu/emanwiki/EMAN2</a><br>
  Versions: 2.12, <em>2.2</em><br>
  </dd>

  <dt>featuresketch</dt>
  <dd>
Ursula's featuresketch script; run feature_sketch.sh then feature_sketch.py<br>
  Versions: <em>3.0</em><br>
  </dd>

  <dt>fpocket</dt>
  <dd>
Protein pocket (cavity) detection algorithm<br>
    URL: <a href="https://github.com/Discngine/fpocket">https://github.com/Discngine/fpocket</a><br>
  Versions: <em>2.0</em><br>
  </dd>

  <dt>gcc</dt>
  <dd>
Various compilers (C, C++, Objective-C, Java, ...)<br>
    URL: <a href="https://gcc.gnu.org/">https://gcc.gnu.org/</a><br>
  Versions: 5.1.1, 6.4.1, 7.3.1, <em>10.2.1</em><br>
  </dd>

  <dt>ghostscript</dt>
  <dd>
A PostScript interpreter and renderer<br>
    URL: <a href="https://www.ghostscript.com/">https://www.ghostscript.com/</a><br>
  Versions: <em>8.70</em><br>
  </dd>

  <dt>gnuplot</dt>
  <dd>
A program for plotting mathematical expressions and data<br>
    URL: <a href="http://www.gnuplot.info/">http://www.gnuplot.info/</a><br>
  Versions: <em>5.0.5</em><br>
  </dd>

  <dt>hdf5</dt>
  <dd>
A general purpose library and file format for storing scientific data<br>
    URL: <a href="https://support.hdfgroup.org/HDF5/">https://support.hdfgroup.org/HDF5/</a><br>
  Versions: 1.8.14, 1.8.17, 1.10.1, 1.10.5, <em>1.10.6</em><br>
  </dd>

  <dt>ifort</dt>
  <dd>
Intel Fortran compiler<br>
    URL: <a href="http://software.intel.com/content/www/us/en/develop/tools/oneapi/components/fortran-compiler.html">http://software.intel.com/content/www/us/en/develop/tools/oneapi/components/fortran-compiler.html</a><br>
  Versions: <em>10.1.022</em><br>
  </dd>

  <dt>ImageMagick</dt>
  <dd>
An X application for displaying and manipulating images<br>
    URL: <a href="https://imagemagick.org/">https://imagemagick.org/</a><br>
  Versions: <em>6.8.8.10</em><br>
  </dd>

  <dt>imp</dt>
  <dd>
Integrative Modeling Platform (version 2.14.0, with only usage checks turned on)<br>
    URL: <a href="https://integrativemodeling.org/">https://integrativemodeling.org/</a><br>
  Versions: last_ok_build, nightly, 2.7.0, 2.8.0, 2.9.0, 2.10.0, 2.10.1, 2.11.0, 2.11.1, 2.12.0, 2.13.0, <em>2.14.0</em><br>
  </dd>

  <dt>imp-fast</dt>
  <dd>
Integrative Modeling Platform (version 2.14.0, fast build)<br>
    URL: <a href="https://integrativemodeling.org/">https://integrativemodeling.org/</a><br>
  Versions: last_ok_build, nightly, 2.7.0, 2.8.0, 2.9.0, 2.10.0, 2.10.1, 2.11.0, 2.11.1, 2.12.0, 2.13.0, <em>2.14.0</em><br>
  </dd>

  <dt>itcell</dt>
  <dd>
Integrative T-cell epitope prediction<br>
    URL: <a href="https://github.com/salilab/itcell-lib">https://github.com/salilab/itcell-lib</a><br>
  Versions: <br>
  </dd>

  <dt>libtau</dt>
  <dd>
Code from the SAMBA group at TAU<br>
    URL: <a href="https://integrativemodeling.org/libTAU.html">https://integrativemodeling.org/libTAU.html</a><br>
  Versions: <em>1.0.1</em><br>
  </dd>

  <dt>main</dt>
  <dd>
Dusan Turk's MAIN program<br>
    URL: <a href="https://stef.ijs.si/">https://stef.ijs.si/</a><br>
  Versions: <em>2013</em><br>
  </dd>

  <dt>matlab</dt>
  <dd>
Language for technical computing<br>
    URL: <a href="https://www.mathworks.com/products/matlab.html">https://www.mathworks.com/products/matlab.html</a><br>
  Versions: <em>9.5.0.944444</em><br>
  </dd>

  <dt>mist</dt>
  <dd>
MiST - Mass spectrometry interaction STatistics<br>
    URL: <a href="https://github.com/salilab/mist/">https://github.com/salilab/mist/</a><br>
  Versions: <br>
  </dd>

  <dt>modeller</dt>
  <dd>
MODELLER comparative modeling<br>
    URL: <a href="https://salilab.org/modeller/">https://salilab.org/modeller/</a><br>
  Versions: 9.10, 9.11, 9.12, 9.13, 9.14, 9.15, 9.16, 9.17, 9.18, 9.19, 9.20, 9.21, 9.22, 9.23, 9.24, 9.25, 10.0, 10.1, <em>SVN</em><br>
  </dd>

  <dt>modpipe</dt>
  <dd>
ModPipe (sets $MODPIPE; only works on the cluster)<br>
    URL: <a href="https://salilab.org/modpipe/">https://salilab.org/modpipe/</a><br>
  Versions: 2.0.1, 2.0.2, 2.1.0, 2.1.1, 2.1.2, 2.1.3, 2.2.0, <em>2.3.0</em><br>
  </dd>

  <dt>muscle</dt>
  <dd>
Multiple alignment program for protein sequences<br>
    URL: <a href="http://www.drive5.com/muscle/">http://www.drive5.com/muscle/</a><br>
  Versions: <em>3.8.31</em><br>
  </dd>

  <dt>ninja</dt>
  <dd>
A small build system with a focus on speed<br>
    URL: <a href="https://ninja-build.org/">https://ninja-build.org/</a><br>
  Versions: 1.6.0, <em>1.8.2</em><br>
  </dd>

  <dt>opencv (part of gcc/10.2.1)</dt>
  <dd>
Collection of algorithms for computer vision<br>
    URL: <a href="https://opencv.org/">https://opencv.org/</a><br>
  Versions: 3.4.3, <em>4.3.0</em><br>
    Note: <em>To use this module, call <code>module load CBI CBI-testing</code> first.</em>
  </dd>

  <dt>openeye</dt>
  <dd>
OpenEye products (work on any 64-bit node)<br>
    URL: <a href="https://www.eyesopen.com/">https://www.eyesopen.com/</a><br>
  Versions: <em>2012</em><br>
  </dd>

  <dt>patch_dock</dt>
  <dd>
Molecular Docking Based on Shape Complementarity Principles<br>
    URL: <a href="https://bioinfo3d.cs.tau.ac.il/PatchDock/">https://bioinfo3d.cs.tau.ac.il/PatchDock/</a><br>
  Versions: <em>1.3</em><br>
  </dd>

  <dt>pcss</dt>
  <dd>
Peptide Classification using Sequence and Structure<br>
    URL: <a href="https://github.com/salilab/pcss">https://github.com/salilab/pcss</a><br>
  Versions: <br>
  </dd>

  <dt>phenix</dt>
  <dd>
Python-based Hierarchical ENvironment for Integrated Xtallography<br>
    URL: <a href="https://www.phenix-online.org/">https://www.phenix-online.org/</a><br>
  Versions: 1.10.1.2155, 1.18.2.3874, <em>1.19.1.4122</em><br>
  </dd>

  <dt>profit</dt>
  <dd>
ProFit, a protein least squares fitting program<br>
    URL: <a href="http://www.bioinf.org.uk/software/profit/">http://www.bioinf.org.uk/software/profit/</a><br>
  Versions: <em>3.1</em><br>
  </dd>

  <dt>psipred</dt>
  <dd>
Accurate protein secondary structure prediction<br>
    URL: <a href="http://bioinf.cs.ucl.ac.uk/psipred/">http://bioinf.cs.ucl.ac.uk/psipred/</a><br>
  Versions: <em>4.0</em><br>
  </dd>

  <dt>python2/biopython</dt>
  <dd>
  Versions: 1.68, 1.69, <em>1.70</em><br>
  </dd>

  <dt>python2/bottleneck</dt>
  <dd>
  Versions: 1.2.0, <em>1.2.1</em><br>
  </dd>

  <dt>python2/cycler</dt>
  <dd>
  Versions: <em>0.10.0</em><br>
  </dd>

  <dt>python2/dateutil</dt>
  <dd>
  Versions: 1.5, <em>2.6.1</em><br>
  </dd>

  <dt>python2/decorator</dt>
  <dd>
  Versions: 4.0.11, <em>4.2.1</em><br>
  </dd>

  <dt>python2/functools32</dt>
  <dd>
  Versions: <em>3.2.3</em><br>
  </dd>

  <dt>python2/h5py</dt>
  <dd>
  Versions: 2.6.0, 2.7.0, <em>2.7.1</em><br>
  </dd>

  <dt>python2/ihm</dt>
  <dd>
  Versions: <em>0.11</em><br>
  </dd>

  <dt>python2/lru_cache</dt>
  <dd>
  Versions: <em>1.5</em><br>
  </dd>

  <dt>python2/matplotlib</dt>
  <dd>
  Versions: 2.0.0, 2.0.2, <em>2.1.2</em><br>
  </dd>

  <dt>python2/mdp</dt>
  <dd>
  Versions: <em>2.6</em><br>
  </dd>

  <dt>python2/msgpack</dt>
  <dd>
  Versions: 0.5.6, <em>0.6.2</em><br>
  </dd>

  <dt>python2/networkx</dt>
  <dd>
  Versions: <em>1.11</em><br>
  </dd>

  <dt>python2/nose</dt>
  <dd>
  Versions: <em>1.3.7</em><br>
  </dd>

  <dt>python2/numexpr</dt>
  <dd>
  Versions: 2.6.2, <em>2.6.4</em><br>
  </dd>

  <dt>python2/numpy</dt>
  <dd>
  Versions: 1.12.0, 1.13.0, <em>1.14.1</em><br>
  </dd>

  <dt>python2/pandas</dt>
  <dd>
  Versions: 0.19.2, 0.20.2, <em>0.22.0</em><br>
  </dd>

  <dt>python2/pkgconfig</dt>
  <dd>
  Versions: <em>1.2.2</em><br>
  </dd>

  <dt>python2/protobuf</dt>
  <dd>
  Versions: 2.3.0, <em>2.5.0</em><br>
  </dd>

  <dt>python2/pymc</dt>
  <dd>
  Versions: <em>2.3.6</em><br>
  </dd>

  <dt>python2/pyparsing</dt>
  <dd>
  Versions: <em>2.1.10</em><br>
  </dd>

  <dt>python2/pyrmsd</dt>
  <dd>
  Versions: <em>4.1.git48ab119</em><br>
  </dd>

  <dt>python2/pytz</dt>
  <dd>
  Versions: <em>2016.10</em><br>
  </dd>

  <dt>python2/scikit</dt>
  <dd>
  Versions: 0.12, 0.18.1, <em>0.19.1</em><br>
  </dd>

  <dt>python2/scipy</dt>
  <dd>
  Versions: 0.18.1, 0.19.0, <em>1.0.0</em><br>
  </dd>

  <dt>python2/six</dt>
  <dd>
  Versions: <em>1.10.0</em><br>
  </dd>

  <dt>python2/tables</dt>
  <dd>
  Versions: 3.3.0, 3.4.2, <em>3.5.2</em><br>
  </dd>

  <dt>python3/attrs</dt>
  <dd>
Classes Without Boilerplate<br>
    URL: <a href="https://www.attrs.org/">https://www.attrs.org/</a><br>
  Versions: <em>20.3.0</em><br>
  </dd>

  <dt>python3/biopython</dt>
  <dd>
Python tools for computational molecular biology<br>
    URL: <a href="https://biopython.org/">https://biopython.org/</a><br>
  Versions: <em>1.75</em><br>
  </dd>

  <dt>python3/bottleneck</dt>
  <dd>
Collection of fast NumPy array functions written in Cython<br>
    URL: <a href="https://github.com/pydata/bottleneck">https://github.com/pydata/bottleneck</a><br>
  Versions: <em>1.3.1</em><br>
  </dd>

  <dt>python3/cycler</dt>
  <dd>
Composable style cycles<br>
    URL: <a href="https://github.com/matplotlib/cycler">https://github.com/matplotlib/cycler</a><br>
  Versions: <em>0.10.0</em><br>
  </dd>

  <dt>python3/dateutil</dt>
  <dd>
Powerful extensions to the standard datetime module<br>
    URL: <a href="https://dateutil.readthedocs.io/en/stable/">https://dateutil.readthedocs.io/en/stable/</a><br>
  Versions: <em>2.8.1</em><br>
  </dd>

  <dt>python3/decorator</dt>
  <dd>
Module to simplify usage of decorators<br>
    URL: <a href="https://github.com/micheles/decorator">https://github.com/micheles/decorator</a><br>
  Versions: <em>4.4.1</em><br>
  </dd>

  <dt>python3/flake8</dt>
  <dd>
The modular source code checker: pep8 pyflakes and co<br>
    URL: <a href="https://gitlab.com/pycqa/flake8">https://gitlab.com/pycqa/flake8</a><br>
  Versions: <em>3.8.4</em><br>
  </dd>

  <dt>python3/h5py</dt>
  <dd>
Python interface to the Hierarchical Data Format library<br>
    URL: <a href="https://www.h5py.org/">https://www.h5py.org/</a><br>
  Versions: <em>2.10.0</em><br>
  </dd>

  <dt>python3/ihm</dt>
  <dd>
Python package for handling IHM mmCIF files<br>
    URL: <a href="https://github.com/ihmwg/python-ihm">https://github.com/ihmwg/python-ihm</a><br>
  Versions: <em>0.15</em><br>
  </dd>

  <dt>python3/importlib-metadata</dt>
  <dd>
Read metadata from Python packages<br>
    URL: <a href="https://github.com/python/importlib_metadata">https://github.com/python/importlib_metadata</a><br>
  Versions: <em>3.3.0</em><br>
  </dd>

  <dt>python3/iniconfig</dt>
  <dd>
Brain-dead simple parsing of ini files<br>
    URL: <a href="https://github.com/RonnyPfannschmidt/iniconfig">https://github.com/RonnyPfannschmidt/iniconfig</a><br>
  Versions: <em>1.1.1</em><br>
  </dd>

  <dt>python3/joblib</dt>
  <dd>
Lightweight pipelining: using Python functions as pipeline jobs<br>
    URL: <a href="https://joblib.readthedocs.io/en/latest/">https://joblib.readthedocs.io/en/latest/</a><br>
  Versions: 0.14.0, <em>0.17.0</em><br>
  </dd>

  <dt>python3/kiwisolver</dt>
  <dd>
A fast implementation of the Cassowary constraint solver<br>
    URL: <a href="https://github.com/nucleic/kiwi">https://github.com/nucleic/kiwi</a><br>
  Versions: <em>1.1.0</em><br>
  </dd>

  <dt>python3/matplotlib</dt>
  <dd>
Python 2D plotting library<br>
    URL: <a href="https://matplotlib.org/">https://matplotlib.org/</a><br>
  Versions: <em>3.1.2</em><br>
  </dd>

  <dt>python3/mccabe</dt>
  <dd>
McCabe checker, plugin for flake8<br>
    URL: <a href="https://github.com/pycqa/mccabe">https://github.com/pycqa/mccabe</a><br>
  Versions: <em>0.6.1</em><br>
  </dd>

  <dt>python3/msgpack</dt>
  <dd>
A Python MessagePack (de)serializer<br>
    URL: <a href="https://msgpack.org/">https://msgpack.org/</a><br>
  Versions: <em>0.6.2</em><br>
  </dd>

  <dt>python3/networkx</dt>
  <dd>
Creates and Manipulates Graphs and Networks<br>
    URL: <a href="https://networkx.github.io/">https://networkx.github.io/</a><br>
  Versions: <em>2.4</em><br>
  </dd>

  <dt>python3/nose</dt>
  <dd>
Discovery-based unittest extension for Python3<br>
    URL: <a href="https://nose.readthedocs.io/en/latest/">https://nose.readthedocs.io/en/latest/</a><br>
  Versions: <em>1.3.7</em><br>
  </dd>

  <dt>python3/numexpr</dt>
  <dd>
Fast numerical array expression evaluator for Python and NumPy<br>
    URL: <a href="https://github.com/pydata/numexpr">https://github.com/pydata/numexpr</a><br>
  Versions: <em>2.7.0</em><br>
  </dd>

  <dt>python3/numpy</dt>
  <dd>
A fast multidimensional array facility for Python<br>
    URL: <a href="https://numpy.org/">https://numpy.org/</a><br>
  Versions: <em>1.17.4</em><br>
  </dd>

  <dt>python3/packaging</dt>
  <dd>
Core utilities for Python packages<br>
    URL: <a href="https://github.com/pypa/packaging">https://github.com/pypa/packaging</a><br>
  Versions: <em>20.8</em><br>
  </dd>

  <dt>python3/pandas</dt>
  <dd>
Python Data Analysis Library<br>
    URL: <a href="https://pandas.pydata.org/">https://pandas.pydata.org/</a><br>
  Versions: <em>0.25.3</em><br>
  </dd>

  <dt>python3/pkgconfig</dt>
  <dd>
A Python interface to the pkg-config command line tool<br>
    URL: <a href="https://github.com/matze/pkgconfig">https://github.com/matze/pkgconfig</a><br>
  Versions: <em>1.5.1</em><br>
  </dd>

  <dt>python3/pluggy</dt>
  <dd>
A minimalist production ready plugin system<br>
    URL: <a href="https://github.com/pytest-dev/pluggy">https://github.com/pytest-dev/pluggy</a><br>
  Versions: <em>0.13.1</em><br>
  </dd>

  <dt>python3/protobuf (part of gcc/10.2.1)</dt>
  <dd>
Protocol Buffers - Google's data interchange format<br>
    URL: <a href="https://developers.google.com/protocol-buffers/">https://developers.google.com/protocol-buffers/</a><br>
  Versions: <em>3.11.2</em><br>
    Note: <em>To use this module, call <code>module load CBI CBI-testing</code> first.</em>
  </dd>

  <dt>python3/py</dt>
  <dd>
Cross-python path, ini-parsing, io, code, log facilities<br>
    URL: <a href="https://py.readthedocs.io/en/latest/">https://py.readthedocs.io/en/latest/</a><br>
  Versions: <em>1.10.0</em><br>
  </dd>

  <dt>python3/pycodestyle</dt>
  <dd>
Python style guide checker<br>
    URL: <a href="https://pycodestyle.readthedocs.io/">https://pycodestyle.readthedocs.io/</a><br>
  Versions: <em>2.6.0</em><br>
  </dd>

  <dt>python3/pyflakes</dt>
  <dd>
Passive checker of Python programs<br>
    URL: <a href="https://github.com/PyCQA/pyflakes">https://github.com/PyCQA/pyflakes</a><br>
  Versions: <em>2.2.0</em><br>
  </dd>

  <dt>python3/pyparsing</dt>
  <dd>
An object-oriented approach to text processing<br>
    URL: <a href="https://github.com/pyparsing/pyparsing/">https://github.com/pyparsing/pyparsing/</a><br>
  Versions: <em>2.4.5</em><br>
  </dd>

  <dt>python3/pyrmsd</dt>
  <dd>
Way of performing RMSD calculations of large sets of structures<br>
    URL: <a href="https://github.com/salilab/pyRMSD">https://github.com/salilab/pyRMSD</a><br>
  Versions: <em>4.1.gita558b8a</em><br>
  </dd>

  <dt>python3/pytest</dt>
  <dd>
Simple powerful testing with Python<br>
    URL: <a href="https://docs.pytest.org/en/latest/">https://docs.pytest.org/en/latest/</a><br>
  Versions: <em>6.2.1</em><br>
  </dd>

  <dt>python3/pytest-flake8</dt>
  <dd>
pytest plugin to check FLAKE8 requirements<br>
    URL: <a href="https://github.com/tholo/pytest-flake8">https://github.com/tholo/pytest-flake8</a><br>
  Versions: <em>1.0.7</em><br>
  </dd>

  <dt>python3/pytz</dt>
  <dd>
World Timezone Definitions for Python<br>
    URL: <a href="https://pythonhosted.org/pytz/">https://pythonhosted.org/pytz/</a><br>
  Versions: <em>2019.3</em><br>
  </dd>

  <dt>python3/scikit</dt>
  <dd>
A set of python modules for machine learning and data mining<br>
    URL: <a href="https://scikit-learn.org/stable/index.html">https://scikit-learn.org/stable/index.html</a><br>
  Versions: <em>0.21.3</em><br>
  </dd>

  <dt>python3/scipy</dt>
  <dd>
Scipy: Scientific Tools for Python<br>
    URL: <a href="https://www.scipy.org/">https://www.scipy.org/</a><br>
  Versions: <em>1.3.2</em><br>
  </dd>

  <dt>python3/six</dt>
  <dd>
Python 2 and 3 compatibility utilities<br>
    URL: <a href="https://github.com/benjaminp/six">https://github.com/benjaminp/six</a><br>
  Versions: <em>1.13.0</em><br>
  </dd>

  <dt>python3/tables</dt>
  <dd>
Hierarchical datasets in Python<br>
    URL: <a href="http://www.pytables.org/">http://www.pytables.org/</a><br>
  Versions: <em>3.6.1</em><br>
  </dd>

  <dt>python3/toml</dt>
  <dd>
Python Library for Tom's Obvious, Minimal Language<br>
    URL: <a href="https://github.com/uiri/toml">https://github.com/uiri/toml</a><br>
  Versions: <em>0.10.2</em><br>
  </dd>

  <dt>python3/typing-extensions</dt>
  <dd>
Backported and Experimental Type Hints for Python 3.5+<br>
    URL: <a href="https://pypi.org/project/typing-extensions/">https://pypi.org/project/typing-extensions/</a><br>
  Versions: <em>3.7.4.3</em><br>
  </dd>

  <dt>python3/zipp</dt>
  <dd>
Backport of pathlib-compatible object wrapper for zip files<br>
    URL: <a href="https://github.com/jaraco/zipp">https://github.com/jaraco/zipp</a><br>
  Versions: <em>3.4.0</em><br>
  </dd>

  <dt>relion</dt>
  <dd>
Electron cryo-microscopy refinement<br>
    URL: <a href="https://github.com/3dem/relion">https://github.com/3dem/relion</a><br>
  Versions: 1.4, 2.0.6, <em>3.0.git9a02562</em><br>
  </dd>

  <dt>rosetta</dt>
  <dd>
Computational modeling and analysis of protein structures<br>
    URL: <a href="https://www.rosettacommons.org/">https://www.rosettacommons.org/</a><br>
  Versions: 3.5, <em>3.10</em><br>
  </dd>

  <dt>sali-libraries</dt>
  <dd>
Makes available libraries usually only present on the Sali interactive nodes<br>
  Versions: <br>
  </dd>

  <dt>scwrl</dt>
  <dd>
Protein side-chain conformation prediction program<br>
    URL: <a href="http://dunbrack.fccc.edu/SCWRL4.php">http://dunbrack.fccc.edu/SCWRL4.php</a><br>
  Versions: <em>4.0</em><br>
  </dd>

  <dt>svm_light</dt>
  <dd>
Support Vector Machine<br>
    URL: <a href="http://svmlight.joachims.org/">http://svmlight.joachims.org/</a><br>
  Versions: <em>6.0.2</em><br>
  </dd>

  <dt>swig</dt>
  <dd>
Connects C/C++/Objective C to some high-level programming languages<br>
    URL: <a href="http://www.swig.org/">http://www.swig.org/</a><br>
  Versions: 3.0.12, <em>4.0.2</em><br>
  </dd>

  <dt>usearch</dt>
  <dd>
High-throughput search and clustering tool<br>
    URL: <a href="http://www.drive5.com/usearch/">http://www.drive5.com/usearch/</a><br>
  Versions: 4.0.43, <em>10.0.240</em><br>
  </dd>

  <dt>web_service</dt>
  <dd>
Command line interface (web_service.py) to most lab web services<br>
    URL: <a href="https://github.com/salilab/saliweb">https://github.com/salilab/saliweb</a><br>
  Versions: <br>
  </dd>

  <dt>zdock</dt>
  <dd>
Rigid body docking<br>
    URL: <a href="http://zdock.umassmed.edu/">http://zdock.umassmed.edu/</a><br>
  Versions: <em>3.0.2</em><br>
  </dd>

</dl>
</div> 


</div> 

<ul class="nav nav-pills">
  <li class="active"><a data-toggle="pill" href="#queues-built-in"><span style="font-weight: bold;">built-in</span>&nbsp;(7)</a></li>
  <li><a data-toggle="pill" href="#queues-CBI"><span style="font-weight: bold;">CBI</span>&nbsp;(65)</a></li>
  <li><a data-toggle="pill" href="#queues-Sali"><span style="font-weight: bold;">Sali</span>&nbsp;(118)</a></li>
</ul>

_The above information was automatically generated on 2021-05-05 11:17:23 from querying `module avail` and `module spider`._


<style>
dl {
  display: block;
}
dt {
  font-family: Menlo, Monaco, Consolas, "Courier New", monospace;
  font-weight: bold;
  font-size: 120%;
  margin-top: 1ex;
  text-decoration: underline;
}
dt:after {
  content: "";
}
</style>

[core software]: {{ '/software/core-software.html' | relative_url }}
