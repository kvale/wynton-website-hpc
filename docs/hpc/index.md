<div class="alert alert-warning" role="alert" markdown="1">
2020-03-16: We will do our best to keep the {{ site.cluster.name }} environment up and running within the restrictions imposed by UCSF and local governments. Minor issues (like node crashes) will be dealt with at a later date.  Major issues will be dealt with on a best-effort basis and may result in longer than normal outages (especially if they require someone to be on site). Email response times are likely to be slower, as well, as we all struggle to adapt to the impacts of COVID-19.
</div>

<div class="alert alert-info" role="alert" markdown="1">
**NEWS**: (_For upcoming and current incidents, see the [Status]({{ site.baseurl }}/hpc/status/index.html) page_)

2022-06-01: Added support for transferring files between Wynton and UCSF Box via [Globus]({{ site.baseurl }}/hpc/transfers/globus.html).

2022-05-02: Added a PHI-compliant endpoint to [Globus]({{ site.baseurl }}/hpc/transfers/globus.html).

2021-12-17: [Wynton PHI]({{ site.baseurl }}/hpc/about/wynton-phi.html) is now available to all UCSF researchers and affiliates to process computing jobs involving PHI.

2021-10-01: Added four [communal GPU nodes]({{ site.baseurl }}/hpc/about/specs.html) each with four Nvidia A40 GPUs (48 GiB GPU RAM) and a 32-core CPU and 512 GB RAM

2021-09-22: Added 2,048 cores (+20%) via 16 huge-memory nodes (128 cores and 1 TiB of RAM)

[More ...]({{ site.baseurl }}/hpc/about/news.html)
</div>


# {{ site.cluster.name }} - UCSF Research Computing at Scale

{{ site.cluster.name }} is a large, shared high-performance compute (HPC) cluster underlying UCSF's Research Computing Capability. Funded and administered cooperatively by UCSF campus IT and key research groups, it is available to all UCSF researchers, and consists of different profiles suited to various biomedical and health science computing needs.  Researchers can participate using the "co-op" model of resource contribution and sharing.

**The {{ site.cluster.name }} environment is available for _free_ to all UCSF researchers**.  To join, please follow the [instructions for requesting an account]({{ site.baseurl }}/hpc/about/join.html).

The {{ site.cluster.name }} environment keeps growing as more users discover it and more groups buy into the co-op model.  [Each contributing member brings more resources and compute power for everyone based on a fair-share model where contributors get higher access priority than non-contributing members]({{ site.baseurl }}/hpc/about/shares.html).  **Contributions to the {{ site.cluster.name }} environment are non-expiring and valid for life!**  In addition, several UCSF centers have joined by contributing a large amount of their compute hardware to the cluster, e.g. Memory and Aging Center and QB3.  For more details on where we are heading, please see the [{{ site.cluster.name }} Roadmap]({{ site.baseurl }}/hpc/about/roadmap.html).

**Please note**: The {{ site.cluster.name }} environment is *not* certified for use with Protected Health Information (PHI) _unless you have a Wynton PHI account_.  Data containing PHI must not be transferred to, mounted on, or processed with any {{ site.cluster.name }} cluster resources other than in the Wynton PHI environment.  For more information or to apply for a PHI account, see [Protected Health Information (PHI) on Wynton].


[UCSF Privacy Office]: https://hipaa.ucsf.edu/
[Protected Health Information (PHI) on Wynton]: {{ site.baseurl }}/hpc/about/wynton-phi.html