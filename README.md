# Collection of ACT benchmarking results

This repository is an *unofficial* collection of benchmarking results for various SSDs with [Aerospike Certification Tool (ACT)](https://github.com/aerospike/act) meant to help deciding on certain SSD models as deployment candidates. Please consider contributing if you can add further results.


### Tested devices
------------
Full benchmarking data (latency tables, raw output & test config files) is currently available for the following devices:
- [Samsung 845DC PRO (400GB)](https://github.com/ArwedSchmidt/act-ssd-benchmarking-results/tree/master/Samsung_845DC_PRO_400GB_@DXV80X3Q/)
- Intel DC S3710 (200GB)
- *... more to come in future*

### Folder structure & naming convention
------------
We split data by vendor, device model, capacity and firmware revision. Inside these folders you can find  3 files (for every single benchmarking run):
- the configuration file used to run the test in **/configs/**
- the raw output of ACT for self-analyzing in **/raw-act-output/** 
- compact results (latency tables) & conclusions in **/results/**

The filename contains information about simulated record size, simulate load ('1x' equals to 1000 writes and 2000 reads), duration, benchmarking system and whether drive was configured with additional over-provisioning. If OP was applied, you will find the capacity in [GibiBytes](https://en.wikipedia.org/wiki/Gibibyte) after over-provisioning mentioned. *Example:* the value 294.4G GiB on a 400GB device *(=376.4GiB)* mean that 21% additional over-provisioning was applied (1-($available_cap/$capacity)).

### How to contribute
------------
If you have run tests and want to share the results with community, please do so by sending a pull request. We would love to add more results! Because enterprise grade solid state disks tend to have very low latency, please add **microsecond-histograms: yes** and **report-interval-sec: 1** to your act config files if possible. Raw output of a 48h run might is around 160mb in size but easily compresses to a feasible size and allows for a much deeper analysis than default millisecond precision. Sticking to 1.5kb record size helps with compareable results.

Contact me if you would like to contribute but need some assistance!