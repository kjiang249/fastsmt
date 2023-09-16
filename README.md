This is a fork of [FastSMT](https://github.com/eth-sri/fastsmt) that is compatible with Z3 4.12.2. 

## Setup Instructions

Clone this repository

```bash
$ git clone https://github.com/kjiang249/fastsmt.git
$ cd fastsmt
```

Download Z3 4.12.2

```bash
$ git clone https://github.com/Z3Prover/z3.git z3
$ cd z3

# Checkout Z3 version 4.12.2 that we tested against
$ git checkout tags/z3-4.12.2
```

Install and compile Z3 4.12.2 (with cpp bindings):

```bash
$ python scripts/mk_make.py 
$ cd build
$ make # (optional) use `make -j4` where 4 is the number of threads used to compile Z3, will likely take couple of minutes
$ sudo make install
$ cd ../..
``` 

Setup python virtual environment.

```bash
$ virtualenv -p python3 --system-site-packages venv
$ source venv/bin/activate
install the following packages in venv:'numpy', 'scipy', 'scikit-learn', 'torch', 'matplotlib', 'tensorboardX','seaborn'
(venv) $ python setup.py install
```

Install and compile Z3 (with Python bindings):

```bash
(venv) $ cd z3
# To generate correct python bindings make sure you activated the virtual env before Z3 compilation
(venv) $ python scripts/mk_make.py --python
(venv) $ cd build
(venv) $ make # (optional) use `make -j4` where 4 is the number of threads used to compile Z3, will likely take couple of minutes
(venv) $ sudo make install
(venv) $ cd ../..
``` 

Finally, compile C++ runner: 
```bash
$ cd fastsmt/cpp
$ make -f make_z3
$ cd ..
```

Please run the tests to make sure installation was successful:

```bash
$ ./test/run_tests.sh 
OK!
```
## Reproduce the learning strategies for [Z3alpha](https://github.com/JohnLu1990/z3alpha) AAAI24 Student Program Submission 
Go to the experiements folder, following the Readme










