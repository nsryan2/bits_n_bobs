1. Go to your arfc folder and clone the repos
    1. `git clone git@github.com:cyclus/cyclus.git`
    1. `git clone git@github.com:cyclus/cycamore.git`
    1. `git clone git@github.com:cyclus/cymetric.git`
    1. `git remote add nathan git@github.com:nsryan2/cycamore.git`
    1. `git remote add nathan git@github.com:nsryan2/cymetric.git`
    1. `git remote add nathan git@github.com:nsryan2/cyclus.git`
1. Make a [conda environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands) called Cyclus
    1. `echo 'export PATH="~/anaconda/bin:$PATH"' >> ~/.bashrc`
    1. `source ~/.bashrc`
    1. `conda config --add channels conda-forge`
    1. `conda create -n cyclus python=3.11.9`
    1. `conda activate cyclus`
    1. `conda install -y openssh gxx_linux-64 gcc_linux-64 cmake make docker-pycreds git xo python-json-logger glibmm glib=2.80.2 libxml2 libxmlpp libxmlpp-4.0 libblas libcblas liblapack pkg-config coincbc=2.9 boost-cpp hdf5 sqlite pcre gettext bzip2 xz setuptools nose pytables pandas jinja2 cython==0.26 websockets pprintpp`
1. Follow the installation guides for each
    1. [Cyclus](https://github.com/cyclus/cyclus/blob/master/INSTALL.rst)
    1. [cycamore](https://github.com/cyclus/cycamore#quick-cycamore-installation)
    1. [cymetric](https://github.com/cyclus/cymetric#readme)
1. Build the docker image:
    1. Start the docker deamon (`sudo launchctl start docker` for mac and `sudo systemctl start docker` for linux)
    2. Build the dependencies `docker build -t cyclus-local -f docker/cyclus-deps/Dockerfile .`
    3. Build the install image `docker build -t cyclus-local-install -f docker/cyclus-ci/Dockerfile .`
    **Don’t tag the dependency and actual images the same thing (that’s what the -t does)**
1. Run the docker image `docker run -it cyclus-local-install /bin/bash`
1. Install [auto tag complete](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
1. Run `cyclus -a` to see which archeytypes are installed.
