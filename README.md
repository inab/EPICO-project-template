# EPICO project template

This template project shows how to start your own project, based on all the EPICO libraries.

Dependencies are listed at [cpanfile](cpanfile).
Those dependencies are available at [BSC INB DarkPAN](https://gitlab.bsc.es/inb/darkpan/).

Next commands will install all the dependencies at `local` subdirectory
using [cpm](https://metacpan.org/pod/App::cpm), and the execution in the
sandbox of dependencies with [Carton](https://metacpan.org/pod/Carton).


```bash
# This command is optional, but helps setting up a clean, healthy installation environment
eval $(perl -Mlocal::lib="$PWD/.plenv")
# Next command install both cpm and Carton (in case you do not have them already)
cpan App::cpm
# This one installs the dependencies used by several programs
cpm install --resolver 02packages,https://gitlab.bsc.es/inb/darkpan/raw/master/ --resolver metadb
# And optional last, deactivation of the clean installation environment
eval $(perl -Mlocal::lib=--deactivate,"$PWD/.plenv")
```

Now you should have a `local` directory, with all the scripts and needed
tools from the dependencies. As you also need a data model itself, next command will fetch one known:

```bash
git clone -b 20190711 https://github.com/inab/EPICO-data-model.git model
```
