# Singularity container for ctools

### Building:

* copy the recipe
* `sudo singularity build container container.recipe`
  Note: the build process can require mins
* use it!

### What you can do?

* `singularity shell -H /place/where/work container`
* [ctools docs](http://cta.irap.omp.eu/ctools/index.html)

### Note

* the building process create a vendors dir in `/tmp` and download with the host
  `wget` the source file. This choice has a lot of implication.
  If you dislike this practice or the host has not the wget program, fix %setup
  and/or %files section.


