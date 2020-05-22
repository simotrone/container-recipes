# Build a singularity container for SAO ds9

### Building / Installation:

* copy the recipe
* `sudo singularity build ds9 ds9.recipe`
  Note: the build process can require mins (t < 5 min)
* use it!

### What you can do?

* `singularity help ds9`
* [ds9 docs](https://sites.google.com/cfa.harvard.edu/saoimageds9/documentation)

### Note

* the building process create a vendors dir in `/tmp` and download with the host
  `wget` the source file. This choice has a lot of implication.
  If you dislike this practice or the host has not the program or I don't know
  what, comment `%setup` section, download file from here
  `http://ds9.si.edu/download/source/ds9.8.1.tar.gz`,
  finally point in the right place the directives in `%files` section.
* the container apps want to show the potential of ds9 as illustrated in
  [Gallery section](https://sites.google.com/cfa.harvard.edu/saoimageds9/gallery).
  The fits files are fetched from remote, so you need internet connection.

### Using the container

![The crab app](assets/crab_app.png)

![Analyzing a skymap](assets/using_ds9.png)

## Credits

Credits go to:

* people developed SAOImage DS9 software
* astro teams that provided the fits file (NASA and other, as stated in app
  help).
