# UR10 Chess Robot

Project by the Foothill Engineering club to play chess against a Universal Robots UR10.

`src` hosts the currently working files used to run the UR10.

See our [project Notion site](https://splendid-eel-64f.notion.site/UR10-Chess-Robot-eca1ce190f8b4982b52d836f1d4e0b59) for more information.

![Photo of the UR10 chess robot](/assets/images/UR10_4_26_24.jpg)

## Requirements

- Python 3.9 or 3.10 (3.10 recommended)

- [stockfish](https://pypi.org/project/stockfish/), [python-chess](https://pypi.org/project/chess/), [colorama](https://pypi.org/project/colorama/) and [ur_rtde](https://pypi.org/project/ur-rtde/)

  - Installable with `pip install -r requirements.txt`
  - ur_rtde and stockfish require additional steps for installation, see [Setup](#setup) for details

- Stockfish [executable](#setup)

- [Svg preview for VS code](https://marketplace.visualstudio.com/items?itemName=jock.svg)

### MacOS specific

- [Homebrew](https://brew.sh/)

## Instructions

- Preview chess.svg in VS code

- Confirm the robot IP listed in `src/main.py`

- Run `main.py` and input your move in SAN format (e.g. b2b4 or e2e4)

## Setup

[Stockfish](https://stockfishchess.org/download/)

[ur_rtde (MacOS or Linux recommended)](https://sdurobotics.gitlab.io/ur_rtde/installation/installation.html)

### MacOS

`brew install stockfish`

`brew install cmake`  
`brew install boost`  
Install tkinter:  
`brew install tcl-tk`  
`echo 'export PATH="/usr/local/opt/tcl-tk/bin:$PATH"' >> ~/.zshrc`  
`source ~/.zshrc`  
`echo $PATH | grep --color=auto tcl-tk`  
`export LDFLAGS="-L/usr/local/opt/tcl-tk/lib"`  
`export CPPFLAGS="-I/usr/local/opt/tcl-tk/include"`  
`export PKG_CONFIG_PATH="/usr/local/opt/tcl-tk/lib/pkgconfig"`  
`python -m tkinter -c "tkinter._test()"`

If `pip install -r requirements.txt` does not correctly install ur_rtde, run `pip install ur-rtde --use-pep517`

### Linux _(Ubuntu 22.04 recommended)_

<!-- Download the latest 64-bit version of stockfish [here](https://stockfishchess.org/download/linux/)
`tar -xvf stockfish-ubuntu-x86-64.tar`
Add to path: `mv stockfish-ubuntu-x86-64 /usr/bin/stockfish` -->

`sudo apt-get install stockfish`
`sudo apt-get install libboost-all-dev`  
`sudo apt install cmake`  
`sudo add-apt-repository ppa:sdurobotics/ur-rtde`  
`apt-get install python3-tk`  
`sudo apt-get install libusb-1.0-0-dev libudev-dev`  
`sudo apt-get update`  
`sudo apt install librtde librtde-dev`  
If `pip install -r requirements.txt` does not correctly install ur_rtde, run `pip install ur-rtde --use-pep517`

### Windows

Run the `install.bat` file to install the required dependencies.

`pip install -r requirements.txt`

## Resources

[UR Real-Time Communication Guide](https://www.universal-robots.com/articles/ur/interface-communication/real-time-data-exchange-rtde-guide/)

[ur_rtde Documentation](https://sdurobotics.gitlab.io/ur_rtde/index.html)

[Python Stockfish](https://github.com/zhelyabuzhsky/stockfish)

[python-chess documentation](https://python-chess.readthedocs.io/en/latest/index.html)

[Stockfish and python-chess tutorial](https://github.com/rogerfitz/tutorials/blob/master/python_chess/0_Chess_Basics.ipynb)

[Chess elo levels](https://en.wikipedia.org/wiki/Chess_rating_system)

[Azure Kinect DK Hardware](https://learn.microsoft.com/en-us/azure/kinect-dk/hardware-specification)

[OpenCV troubleshooting](https://stackoverflow.com/questions/27953069/opencv-error-215size-width0-size-height0-in-function-imshow)

[hidapi documentation](https://blog.thea.codes/talking-to-gamepads-without-pygame/)

[hidapi repository](https://github.com/trezor/cython-hidapi#install)
