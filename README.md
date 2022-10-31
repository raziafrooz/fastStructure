# fastStructure
setting up factStructure conda environment 


# Create a conda environemtn with python 2.7.13
conda create --name faststructre python=2.7.13

# Install the correct verison of dependensies:
conda install numpy==1.16.5
conda install cython==0.27.3
conda install scipy==1.2.1

# Download fastStructure
mkdir ~/proj
cd ~/proj
git clone https://github.com/rajanil/fastStructure

# Make sure these are set correctly:
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
export CFLAGS="-I/usr/local/include"
export LDFLAGS="-L/usr/local/lib"

# Build extensions:
cd ~/proj/fastStructure/vars
python setup.py build_ext --inplace

cd ~/proj/fastStructure
python setup.py build_ext --inplace
