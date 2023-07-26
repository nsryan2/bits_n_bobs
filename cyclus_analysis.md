1. For analysis install [Pyne](https://anaconda.org/conda-forge/pyne)
   1. If you have trouble with HDF5, follow these [instructions](https://askubuntu.com/questions/1340411/installing-hdf5) with [HDF5-1.8.4](https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.8/hdf5-1.8.4/src/hdf5-1.8.4.tar.gz)
   1. If you're having trouble upgrading your conda install from 23.5.1 to 23.5.2 follow [these steps](https://github.com/conda/conda/issues/9469#issuecomment-1635769137)
1. Install [transition-scenarios](https://github.com/arfc/transition-scenarios)
1. When you're running a notebook and want to use one of the scripts, you have to run:
```
import sys
sys.path.insert(0, '/home/nsryan/Desktop/arfc/transition-scenarios/scripts')
```
1. Some tables will be too big to analyze, so you can export them as a csv by using
```
sqlite3 -header -csv your_database_name "select * from TABLE_NAME;" > TABLE_NAME.csv
```
