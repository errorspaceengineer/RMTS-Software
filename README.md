RMTS-Software
==========

Overview
--------
This application allows users to conduct tests of solid rocket motors with their RMTS hardware, process the resulting data, and output files for further analysis and simulation.  

Running from Source
--------------------
The program is currently being developed using Python 3.10. The dependencies are listed in `requirements.txt`. Because the PyQt5 bindings are used for the GUI, Qt5 must also be installed.

The easiest way to build/run from source code is to clone the repository and install the required dependencies into a virtual enviornment:
```
$ git clone https://github.com/errorspaceengineer/RMTS-Software
$ cd RMTS-Software
$ python3 -m venv .venv
$ source .venv/bin/activate
$ pip install -r requirements.txt
```

#### UI Files:
This application's UI is laid out in QT Designer, which generates `.ui` files describing the user interface. We use `pyuic5` to compile these files into Python source code which is then included in the program as ordinary source code.

Because these autogenerated files are not committed to the source tree, you must build them by running:
```
$ python setup.py build_ui
```
Note that if you make changes to the UI using the `.ui` forms, you must re-build using the same command.

Once everything is set up, you can start the software by running: `python main.py`
###### Note: On some systems, Python 2 and 3 are installed simultaneously, so you may have to specify which version to run when creating the venv. After the venv has been activated, the programs `python` and `pip` are aliased to the python runtime specific for your venv, so use those (instead of `pip3` and `python3`, on e.g. Debian Linux)
