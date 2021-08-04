# Missing Software?

Don't find the software you need for your analysis?
<!--
Did you make sure it is not in one of the [software repositories]({{ '/software/software-repositories.html' | relative_url }})?
-->
If so, you have a few options:

1. Install it yourself to your own account
   - Download a pre-built binary
   - Build software from source (traditional, e.g. `./configure --prefix ~/software`, `make`, and `make install`)
<!-- - Build software from source (using Spack, e.g. `spack list` and `spack install pango`) -->
   <br><br>

2. Use [Singularity]({{ '/software/singularity.html' | relative_url }}) to run it via a Linux container
   - Create your own Linux containers
   - Pull down an existing image from public repositories such as Singularity Hub, Docker Hub, and Biocontainers (e.g. `singularity pull shub://nextflow-io/rnatoy` and `singularity shell nextflow-io-rnatoy-master.sif`)
   <br><br>
  
3. Reach out to the [{{ site.cluster.name }} user community]({{ '/support/index.html' | relative_url }})
   - It could be that someone else has already installed it,
     is interested in also installing it, or is willing to help
   <br><br>

4. Missing core software or missing SCL?
   - If a [CentOS core software]({{ '/software/core-software.html' | relative_url }}) or a [CentOS Software Collection (SCL)]({{ '/software/scl.html' | relative_url }}) is missing, it is likely that the [the system administrators]({{ '/about/contact.html' | relative_url }}) are willing to add it - please let us know
