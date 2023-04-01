Install
------------------------

sudo apt install libxtables-dev libip6tc-dev libip4tc-dev

cd /usr/src
git clone https://github.com/Valew17/ndpi-netfilter-custom-ubuntu-20.04.git
cd ndpi-netfilter-custom-ubuntu-20.04
tar xvfz nDPI.tar.gz
cd nDPI
./autogen.sh
make
make install

cd ..
NDPI_PATH=/usr/src/ndpi-netfilter-custom-ubuntu-20.04/nDPI make

make modules_install
cp /usr/src/ndpi-netfilter/ipt/libxt_ndpi.so /lib/xtables/
