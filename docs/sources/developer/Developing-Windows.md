# Developing on Windows

## Git
To download the latest version of Plaso you'll need to install the 
[git tools](http://git-scm.com/downloads).

Checkout the plaso source from the git repo:
```
git clone https://github.com/log2timeline/plaso.git
```

**If you intend to submit code make sure to configure git to use convert to the 
Unix-style end-of-line characters (linefeed) on submission and not have the 
Windows-style end-of-line characters (carriage return + linefeed).** 

We recommend to configure your editor of choice to use linefeed only and turn 
off git's autocrlf:
```
git config --global core.autocrlf false
```

## Dependencies

Install the dependencies, using the 
[prepackaged dependencies](Development-Dependencies.html#Windows).

Check if you have all the dependencies installed and have the right minimum 
version:
```
C:\Python27\python.exe utils\check_dependencies.py
```

**Note that some dependencies are actively under development and can be 
frequently updated, therefore we recommend checking the status of the 
dependencies regularly.**

## Running the development code
To run the development code directly from source make sure Python can find the 
Plaso source files by setting PYTHONPATH correspondingly.
```
set PYTHONPATH=C:\plaso-build\plaso
```

To run a tool, for example `pinfo`:
```
C:\Python37\python.exe C:\plaso-build\plaso\plaso\frontend\pinfo.py test.plaso
```

## Development tools
If you intend to do development on plaso you'll also need to install some 
development tools:

* PyLint
* Python Mock

### PyLint
At the moment Plaso development requires PyLint 1.9.x.

**TODO: describe building pylint 1.9.x**

For pylint 1.9.x the following additional dependencies are required:
* [astroid](https://pypi.python.org/pypi/astroid)
* [lazy-object-proxy](https://pypi.python.org/pypi/lazy-object-proxy)
* [logilab-common](https://pypi.python.org/pypi/logilab-common)
* [wrapt](https://pypi.python.org/pypi/wrapt)

### Python Mock
Download the latest source package from: https://pypi.python.org/pypi/mock

To build the MSI file run the following commands from the build root directory:
```
tar xvf mock-1.0.1.tar.gz
cd mock-1.0.1\
C:\Python37\python.exe setup.py bdist_msi
cd ..
```

This will create a MSI in the dist sub directory e.g.:
```
dist\mock-1.0.1.win32.msi
```

Install the MSI.
