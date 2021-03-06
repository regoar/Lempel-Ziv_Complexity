# Python implementation of Lempel-Ziv Complexity

This repository contains a small, simple and efficient implementation of the [Lempel-Ziv complexity](https://en.wikipedia.org/wiki/Lempel-Ziv_complexity) algorithm.

## Examples
### Simple usage
If the [`lempel_ziv_complexity.py`](src/lempel_ziv_complexity.py) file is accessible in your PATH or in Python's path:

```python
>>> from lempel_ziv_complexity import lempel_ziv_complexity
>>> s = '1001111011000010'
>>> lempel_ziv_complexity(s)  # 1 / 0 / 01 / 1110 / 1100 / 0010
6
```

### Documentation
See [this file](https://naereen.github.io/Lempel-Ziv_Complexity/doc/index.html).

> If you are really interested about the details of how the algorithm works, please see [this GIF screencast](https://github.com/Naereen/Lempel-Ziv_Complexity/issues/2#issuecomment-312421968) from [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit).

- Reference: [this short lecture note by Peter Shor (Oct.2005)](https://math.mit.edu/~shor/PAM/lempel_ziv_notes.pdf).

### With the C extension
If the [`lempel_ziv_complexity.so`](src/lempel_ziv_complexity.pyx) file is accessible in your PATH or in Python's path:


### Small benchmark
There is also a Cython version, to have a faster implementation:
```python
$ ipython
...
>>> s = '1001111011000010'
>>> %timeit lempel_ziv_complexity(s)
6.1 µs ± 33.6 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
>>> %timeit lempel_ziv_complexity_cython(s)
132 ns ± 2.55 ns per loop (mean ± std. dev. of 7 runs, 10000000 loops each)
```
The speedup is typically between ×50 and ×100.

## Demo on a [Jupyter notebook](https://www.Jupyter.org/)
See this notebook: [on nbviewever](https://nbviewer.jupyter.org/github/Naereen/Lempel-Ziv_Complexity/blob/master/Short_study_of_the_Lempel-Ziv_complexity.ipynb), which also compares with the [Julia version](https://github.com/Naereen/LempelZiv.jl).

----

## Install and build
### Manually ?
Easy!

Clone this repository, go in the folder, compile, test, and if it works, install it.

```bash
cd /tmp/
git clone https://GitHub.com/Naereen/Lempel-Ziv_Complexity
cd Lempel-Ziv_Complexity/src/
make build
make test     # should pass
make install  # mv the build/lib*/*.so files where you need them
```

Be sure to include the dynamic library when you need it, or in a folder accessible by your Python interpreter (somewhere in `sys.path`).
The file is `lempel_ziv_complexity_cython.so` (for Python 2) or the `lempel_ziv_complexity_cython.cpython-35m-x86_64-linux-gnu.so` (for Python 3.5, or higher, adapt the name).

## With pip ?
This project is hosted on [the Pypi package repository](https://pypi.org/project/Lempel-Ziv_Complexity/).

```bash
sudo pip install lempel_ziv_complexity
# test it
python -c "from lempel_ziv_complexity import lempel_ziv_complexity; print(lempel_ziv_complexity('1001111011000010') == 6)"  # test
```

[![lempel_ziv_complexity in pypi](https://img.shields.io/pypi/v/lempel_ziv_complexity.svg)](https://pypi.org/project/Lempel-Ziv_Complexity/)
![PyPI implementation](https://img.shields.io/pypi/implementation/lempel_ziv_complexity.svg)
![PyPI pyversions](https://img.shields.io/pypi/pyversions/lempel_ziv_complexity.svg)

----

## Julia implementation ?
[I was curious](https://github.com/Naereen/Lempel-Ziv_Complexity/issues/1) and wanted to write the same algorithm in [Julia](http://julialang.org).
Here it is: [lempel_ziv_complexity.jl](https://github.com/Naereen/Lempel-Ziv_Complexity/blob/master/src/lempel_ziv_complexity.jl).
See [this part of the notebook](https://nbviewer.jupyter.org/github/Naereen/notebooks/blob/master/Short_study_of_the_Lempel-Ziv_complexity.ipynb#%28Experimental%29-Julia-implementation) for a benchmark between Julia and Python.

The Julia package is published here: [Naereen/LempelZiv.jl](https://github.com/Naereen/LempelZiv.jl),
and see [here for its documentation](https://naereen.github.io/LempelZiv.jl/doc/index.html).

----

## About
### Language?
Python v2.7+ or Python v3.1+.

- [Numba](http://numba.pydata.org/) can be used to speed up the pure Python version.
- [Cython](http://cython.org/) is *needed* to build the C extension (faster).

### :scroll: License ? [![GitHub license](https://img.shields.io/github/license/Naereen/Lempel-Ziv_Complexity.svg)](https://github.com/Naereen/badges/blob/master/LICENSE)
[MIT Licensed](https://lbesson.mit-license.org/) (file [LICENSE](LICENSE)).
© [Lilian Besson](https://GitHub.com/Naereen), 2017.

[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/Lempel-Ziv_Complexity/graphs/commit-activity)
[![Ask Me Anything !](https://img.shields.io/badge/Ask%20me-anything-1abc9c.svg)](https://GitHub.com/Naereen/ama)
[![Analytics](https://ga-beacon.appspot.com/UA-38514290-17/github.com/Naereen/Lempel-Ziv_Complexity/README.md?pixel)](https://GitHub.com/Naereen/Lempel-Ziv_Complexity/)

[![ForTheBadge uses-badges](http://ForTheBadge.com/images/badges/uses-badges.svg)](http://ForTheBadge.com)
[![ForTheBadge uses-git](http://ForTheBadge.com/images/badges/uses-git.svg)](https://GitHub.com/)

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)
[![ForTheBadge built-with-science](http://ForTheBadge.com/images/badges/built-with-science.svg)](https://GitHub.com/Naereen/)
