For generating the data in GNURadio Companion the following are the prequsites

1. GNU radio Companion v3.8 installed from source with python3 support
2. I am using a UBUNTU MATE 18.04 with KDE-DESKTOP
3. Two OOT modules gr-nrsc5 and gr-ham


GNURadio Companion v3.8 installation instruction under U18.04
1. Install the following dependencies
sudo apt install git cmake g++ libboost-all-dev libgmp-dev swig python3-numpy \
python3-mako python3-sphinx python3-lxml doxygen libfftw3-dev \
libsdl1.2-dev libgsl-dev libqwt-qt5-dev libqt5opengl5-dev python3-pyqt5 \
liblog4cpp5-dev libzmq3-dev python3-yaml python3-click python3-click-plugins \
python3-zmq python3-scipy

2. For v3.8 run the following consecutive commands
git clone https://github.com/gnuradio/gnuradio.git
cd gnuradio
git checkout maint-3.8
git submodule update --init --recursive
mkdir build
cd build
cmake ../
After running cmake scroll through the stdout and check for missing packages
At the end of cmake stdout check version and support and packages enabled
Now
make -j4
sudo make install

3. The next step is to set PYTHONPATH and LD_LIBRARY_PATH in ~/.bashrc
Till now out install prefix is the default /usr/bin prefix so,
in my case the path is (got from ~/.bashrc in the home directory)
	
Run sudo ldconfig 

4. Close terminal and open and run "gnuradio-companion"

5. OOT install instruction
gr-nrsc5 instructions
In the home directory in terminal run
https://github.com/argilo/gr-nrsc5.git
cd gr-nrsc5
mkdir build
cd build
cmake ../
make -j4
sudo ldconfig

gr-ham instructions
git clone https://github.com/argilo/gr-ham.git
cd gr-ham
mkdir build
cd build
cmake ../
make -j4
sudo ldconfig


For all other python files I have used
numpy, scipy, matplotlib, os, wavfile, skyfield
