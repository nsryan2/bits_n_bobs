1. Go to your arfc folder and clone the repos
    1. `git clone git@github.com:cyclus/cyclus.git`
    1. `git clone git@github.com:cyclus/cycamore.git`
    1. `git clone git@github.com:cyclus/cymetric.git`
1. Make a [conda environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands) called Cyclus
    1. `echo 'export PATH="~/anaconda/bin:$PATH"' >> ~/.bashrc`
    1. `source ~/.bashrc`
    1. `conda config --add channels conda-forge`
    1. `conda create -n cyclus python=3.6`
    1. `conda activate cyclus`
    1. `conda install -y openssh gxx_linux-64 gcc_linux-64 cmake make docker-pycreds git xo python-json-logger glibmm glib=2.56 libxml2 libxmlpp libblas libcblas liblapack pkg-config coincbc=2.9 boost-cpp hdf5 sqlite pcre gettext bzip2 xz setuptools nose pytables pandas jinja2 cython==0.26 websockets pprintpp`
1. Follow the installation guides for each
    1. [Cyclus](https://github.com/cyclus/cyclus/blob/master/INSTALL.rst)
    1. [cycamore](https://github.com/cyclus/cycamore#quick-cycamore-installation)
    1. [cymetric](https://github.com/cyclus/cymetric#readme)