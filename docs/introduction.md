# About fast_matched_filter (FMF)
An efficient seismic matched-filter search for both CPU and GPU architectures.

If you use FMF in research to be published, please reference the following article: Beaucé, Eric, W. B. Frank, and Alexey Romanenko (2017). Fast matched-filter (FMF): an efficient seismic matched-filter search for both CPU and GPU architectures.<br/>_Seismological Research Letters_, doi: [10.1785/0220170181](https://doi.org/10.1785/0220170181)

FMF is available @ https://github.com/beridel/fast_matched_filter
and can be downloaded with:

$ git clone https://github.com/beridel/fast_matched_filter.git

_Required software/hardware:_<br/>
- A C compiler that supports OpenMP (default Mac OS compiler clang does not support OpenMP; gcc can be easily downloaded via homebrew),<br/>
- CPU version: either Python (v2.7 or 3.x) or Matlab,<br/>
- GPU version: Python (v2.7 or 3.x) and a discrete Nvidia graphics card that supports CUDA C with CUDA toolkit installed.<br/>
FMF is known to run well with gcc 4.8.4 or 4.8.5, and cuda 7.5.

# Installation

A simple make + whichever implementation does the trick.  Possible make commands are:<br/>
```
$ make python_cpu
$ make python_gpu
$ make matlab
```

NB: Matlab compiles via mex, which needs to be setup before running. Any compiler can be chosen during the setup of mex, because it will be bypassed by the CC environment variable in the Makefile. Therefore CC must be set to an OpenMP-compatible compiler. Also, make sure the mex_extension variable in the Makefile corresponds to your OS (the different variables for each OS are listed in the Makefile).

Installation as a Python module is possible via setup tools or even pip (which supports clean uninstalling):<br/>
```
$ python setup.py build
$ python setup.py install
```
OR<br/>
```
$ python setup.py build
$ pip install
```

# Running

_Matlab_:<br/>
Matlab only supports the CPU version, which is called with the _fast_matched_filter_ function (provided in the fast_matched_filter.m file).

_Python_:<br/>
Both CPU and GPU versions are called with the _matched_filter_ function. If FMF was installed as a Python module, it can be imported via:<br/>
```python
import fast_matched_filter as fmf
```
