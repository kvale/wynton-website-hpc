# News

2022-06-01: Added support for transferring files between Wynton and UCSF Box via [Globus]({{ site.baseurl }}/hpc/transfers/globus.html).

2022-05-02: Added a PHI-compliant endpoint to [Globus]({{ site.baseurl }}/hpc/transfers/globus.html).

[Wynton PHI]({{ site.baseurl }}/hpc/about/wynton-phi.html) is now available to all UCSF researchers and affiliates to process computing jobs involving PHI.

2021-12-17: [Wynton PHI]({{ site.baseurl }}/hpc/about/wynton-phi.html) is now available to all UCSF researchers and affiliates to process computing jobs involving PHI.

2021-10-01: Added four [communal GPU nodes]({{ site.baseurl }}/hpc/about/specs.html) each with four Nvidia A40 GPUs (48 GiB GPU RAM) and a 32-core CPU and 512 GB RAM

2021-09-22: Added 2,048 cores (+20%) via 16 huge-memory nodes (128 cores and 1 TiB of RAM)

2021-05-28: GPU development node gpudev1 has been upgraded to a machine with 32 CPU cores, 128 GiB RAM, and Nvidia Tesla K80 (was 12 cores, 48 GiB RAM, and GeForce GTX 980 Ti)

2021-05-28: Development node dev1 has been upgraded to a machine with 72 CPU cores and 384 GiB RAM (was 8 cores and 16 GiB RAM)

2021-04-05: We have improved the purchasing and accounting workflow for [lab storage orders]({{ site.baseurl }}/hpc/support/pricing-storage.html) resulting in shorter waiting times.

2021-03-12: Zsh is now also available in addition to the officially supported Bash, our default shell, Csh, and Tcsh.

2021-01-25: We now offer weekly [Office Hours]({{ site.baseurl }}/hpc/support/index.html).

2020-10-29: Access to Wynton's login and data-transfer nodes [requires 2FA authentication]({{ site.baseurl }}/hpc/get-started/duo-signup.html).

2020-08-21: Deployed four BeeGFS storage bricks for the group storage `/wynton/group` to 5.6 PB (was 3.8 PB).  Groups who purchased storage have had their new group quotas updated.

2020-08-21: Increased global `/wynton/scratch` to 615 TiB (was 492 TiB).

2020-08-21: Prefix qb3- has been dropped from the development node names, which are now named dev1, dev2, dev3, and gpudev1.

2020-05-22: Added 2,016 cores (+27%) via 48 standard nodes (36 cores and 384 GiB of RAM), 4 high-memory nodes (36 cores and 756 GiB of RAM), and 4 huge-memory nodes (36 cores and 1.5 TiB of RAM).

2020-04-14: Progress until the next round of storage purchase can be found on [About -> Storage Pricing]({{ site.baseurl }}/hpc/about/pricing-storage.html).

2020-04-03: Added support for [file transfers via the Globus service]({{ site.baseurl }}/hpc/transfers/globus.html).

2020-02-26: Website moved to <{{ site.organization.url }}{{ site.baseurl }}/hpc/>.

2020-02-05: The QB3-legacy NetApp storage (`/netapp/`), deprecated with a deadline on December 2019, crashed on 2020-02-05 and was declared non-recoverable without further resource/funding.

2019-12-13: Status page now include [GPU queue metrics]({{ site.baseurl }}/hpc/status/index.html).

2019-11-12: Added support for [email notifications]({{ site.baseurl }}/hpc/scheduler/email-notifications.html) when a job starts running or ends.

2019-09-20: New [GPU policy]({{ site.baseurl }}/hpc/scheduler/queues.html) in place. All GPU nodes, communal and contributed, are now available to all users. Run time is two weeks, unless for jobs running on a contributed nodes that was not contributed by you in which case the run time is limited to 2 hours.

2019-09-13: Added another three [communal GPU nodes with a total of 12 GPUs]({{ site.baseurl }}/hpc/about/specs.html).

2019-09-12 Added a second [data transfer node]({{ site.baseurl }}/hpc/about/specs.html).

2019-08-15 Legacy NetApp storage locations `/scrapp` and `/scrapp2` used for global scratch have been removed - use `/wynton/scratch` instead.

2019-07-27 Legacy NetApp storage locations `/scrapp` and `/scrapp2` used for global scratch are now deprecated - use `/wynton/scratch` instead.  The deprecated mounts will become read-only on 2019-08-01 and removed on 2019-08-09.

2019-06-13: [Contributed Software Repositories]({{ site.baseurl }}/hpc/software/software-repositories.html) are now available and documented.

2019-04-30: [Contributing Member Shares]({{ site.baseurl }}/hpc/about/shares.html) are now explained and listed online.

2019-04-15: Added a dedicated GPU development node (after having been in beta testing for several months).

2019-04-12: Added another two communal GPU nodes available to all users.  There are now four communal GPU nodes with a total of 12 GPUs.

2019-04-12: Migrated another [24 nodes (396 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-04-09: Added the first two communal GPU nodes available to all users.

2019-03-21: To decrease the number of stray shells, any shell session that has been idle for more than eight hours will timeout and exit automatically.

2019-03-17: The majority (136 nodes; 3680 cores) of the QB3 nodes has now been migrated to {{ site.cluster.name }}.

2019-03-15: Migrated another [8 nodes (224 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-03-12: Migrated another [19 nodes (532 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-03-08: Migrated another [10 nodes (264 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-03-07: Migrated another [11 nodes (292 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-03-06: Migrated another [15 nodes (392 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-03-05: Migrated another [15 nodes (392 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-03-01: Migrated [48 nodes (1344 cores)]({{ site.baseurl }}/hpc/about/specs.html) from QB3 to {{ site.cluster.name }}.

2019-02-14: Added [SGE resource `eth_speed`]({{ site.baseurl }}/hpc/scheduler/submit-jobs.html) for requesting minimum network speeds.

2019-01-31: Added two more [development nodes]({{ site.baseurl }}/hpc/about/specs.html).

2019-01-18: It is now possible to [purchase additional storage]({{ site.baseurl }}/hpc/about/pricing-storage.html).

2018-11-05: Nightly cleanup of [scratch spaces]({{ site.baseurl }}/hpc/about/specs.html#scratch-storage) now respects also when files were "added" - not just when they were last modified.  This fixes the problem where files with old timestamps were extracted from an archive just to be wiped by the next nightly cleanup.

2018-10-02: Added a [Roadmap].

2018-08-20: [Global scratch storage]({{ site.baseurl }}/hpc/about/specs.html#scratch-storage) on BeeGFS Parallel File System is live - validation and testing completed.

2018-08-02: Added a dedicate [10 Gbps transfer node]({{ site.baseurl }}/hpc/about/specs.html#data-transfer-nodes) for faster file transfers in to and out from {{ site.cluster.nickname }}.

2018-07-25: [BeeGFS Parallel File System/Storage]({{ site.baseurl }}/hpc/about/specs.html#scratch-storage): Validation completed - user beta testing started.

2017-09-07: {{ site.cluster.name }} is live.


For upcoming features and improvements, please see the [Roadmap].


[Roadmap]: {{ site.baseurl }}/hpc/about/roadmap.html