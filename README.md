# TYUTSummerCourseDesignScripts

## What is this?

After preprocessing the fMRI data, we will get some matrix data based on the brain nodes, especially the Pearson correlation matrix between points. This script can be used for matrix classification processing and further work of composition.

## Why create this?

In the processing of matrix data, with the increasing number of template nodes and processing samples, it will cost a lot of time and even appear some low-level errors if manual or general software is simply used for screening, processing and analysis. So we created this script to make it easier and more efficient.

## What functions does it have?

1. Processing data matrix to realize data visualization. You can extract and filter the part above a certain value from the matrix, output a specific matrix image, and output the corresponding coordinates and names of the corresponding nodes to a specific table (this script is output to Excel).
2. All object images are compared to output a specified matrix image with a certain number of repetitions as the standard.
3. Import specified node coordinates, which can realize the original matrix data screening function, and output corresponding files (. Node and. Edge) according to Power264 matrix, which can be directly imported into BrainNet for use.
4. Most of the generated files are MATLAB compatible, you can use them in MATLAB directly, incompatible files are used for human reading directly, you can open them easily with Excel or any image viewer you like. In fact, we use this script to genrate files to plot in MATLAB, it will be too effectiveless if we do it manually.

## How to use it?

### Prepare reequirements

It is very simple to use it. As it is a python script, you have to install Python at [there](https://python.org), then, please ensure you have `pip` command and the working directory of your terminal is this project's folder, install requirements by executing `pip install -r requirements.txt` in your terminal. This script is coded and tested on Python 3.9.6 on Windows x64, but other environments should be ok.

#### Special tips for non-Windows users

You can install requirements through your system's package manager and we recommend to do so that you can keep your packages latest.

Ubuntu/Debian:

```shell

sudo apt-get install -y python3-numpy python3-matplotlib python3-openpyxl

```

Unfortunately, there is no `python3-PyQt6` package for Ubuntu, so you have to install it from PyPi by executing `pip install PyQt6` in the terminal. If it have this package in the future, feel free to install throgh `apt-get`

Arch Linux/Manjaro Linux:

```shell
sudo pacman -S python-numpy python-matplotlib python-openpyxl python-pyqt6
```

Fedora/RedHat/Cent OS:

```shell
sudo dnf install -y python3-numpy python3-openpyxl
```

Unfortunately `matplotlib`, `openpyxl` and `pyqt6` are not provided in its repo, so please manually install them by executing `pip install matplotlib openpyxl pyqt6`.

Mac OS X:

```shell
brew install numpy pyqt
```

Unfortunately, `matplotlib` and `openpyxl` are not included in brew Formula, so you have to install them manually through `pip install matplotlib openpyxl`.

NOTE: Please avoid as possible using `sudo` with `pip` as this option may add many files not managed by your system's package manager.

## Run the script

After such a hard work, we can run this script directly by double-clicking it. As its extension name is `.pyw`, Windows and MAC OS X may recognize it and run it with `pythonw` to provide full GUI experience without terminal. Linux user can run it in terminal and the GUI should also appears if you installed Graphic Environment.

## Use this script

After started the script, we will create two files: `config.json` and a `*.log` file. The former is used for storing config, the latter is used for recording log.  
Once you have seen the UI, the left-up corner is used for minimizing the window or closing the script, the center is used for log outputting, below it is a progress bar to show progress, below the progress bar is start button to start processing, the bottom have two buttons, the left one is setting button for configuring the script, the right one is used for creating or editing process info file. If you click start button directly, it will failed to run because you don't set process info file. You can set one in the setting dialog by clicking setting button.  
The setting dialog has two extra option: debug mode and minimize to tray. Debug mode means enable the script's debug mode for debugging, Minimize to tray means th script will minimize to tray if you enabled it, you can show it by double-clicking its tray icon.  
Now it is the most important part of this script, the script's process info editor. You can enter it by clicking the editor button at the right of the setting button. Most of the elements in the editor have their tooltip to explain what are they. You can use this tool to create or edit process info, after you save one, you can let script use it at the setting dialog.  
You must have finished creating a process info file, right? Use it breavely and hit start button, the process will start immidiately. All the processes should be automatical, so why not have a break or prepare for other things which are more important? After process finishes we will send a system notification to let you know.
