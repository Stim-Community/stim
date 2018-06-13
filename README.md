<img src="https://github.com/STM0x0/stim/blob/master/share/pixmaps/stim337.png" halign="center" valign="center" hspace="250px">


<h3><strong>Stim is an ASIC-resistant digital cryptocurrency based on an improved Dash blockchain.  Stim’s database network uses key technologies to encrypt, store, retrieve and distribute data across the network. Instant payments and quick confirmations will be much faster than Bitcoin. Your payments will be processed anywhere in the world at any time, as quickly as possible.  All transactions are stored in a unit of cost and can be accessed by any user at any time.
Stim is a self-reliant established on a Proof of Work and Masternode system.  Everyone can participate in Stim’s growth, to make Stim more decentralized while helping keep the integrity and the stability of network.  The Stim community hopes to be a sharing economy that incentivizes consumers and resource contributors alike.</strong></h3>


https://stimco.in/

https://bitcointalk.org/index.php?topic=4422894

https://discord.gg/A4Ck9Pt



System requirements
--------------------

C++ compilers are memory-hungry. It is recommended to have at least 3 GB of
memory available when compiling Stim Core. With 1GB of memory or less
compilation will fail. On a system with 1GB or less you will need to create a swapfile.

To create a temporary 2GB swapfile for compile:


<p>cd /</p>
<p>sudo dd if=/dev/zero of=/var/swapfile1 bs=1024k count=2000</p>
<p>sudo mkswap /var/swapfile1</p>
<p>sudo chmod 0600 /var/swapfile1</p>
<p>sudo swapon /var/swapfile1</p>
<p>cd --</p>    
  

Dependency Build Instructions: Ubuntu & Debian
----------------------------------------------
Build requirements:

    sudo apt-get install software-properties-common build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    
On at least Ubuntu 14.04+ and Debian 7+ there are generic names for the
individual boost development packages, so the following can be used to only
install necessary parts of boost:

    sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

If that doesn't work, you can install all boost development packages with:

    sudo apt-get install libboost-all-dev

BerkeleyDB is required for the wallet. db4.8 packages are available [here](https://launchpad.net/~bitcoin/+archive/bitcoin).
You can add the repository and install using the following commands:

    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

Ubuntu and Debian have their own libdb-dev and libdb++-dev packages, but these will install
BerkeleyDB 5.1 or later, which break binary wallet compatibility with the distributed executables which
are based on BerkeleyDB 4.8. If you do not care about wallet compatibility,
pass `--with-incompatible-bdb` to configure.

See the section "Disable-wallet mode" to build Stim Core without wallet.

Optional:

    sudo apt-get install libminiupnpc-dev (see --with-miniupnpc and --enable-upnp-default)

ZMQ dependencies:

    sudo apt-get install libzmq3-dev (provides ZMQ API 4.x)

Dependencies for the GUI: Ubuntu & Debian
-----------------------------------------

If you want to build Stim-Qt, make sure that the required packages for Qt development
are installed. Either Qt 5 or Qt 4 are necessary to build the GUI.
If both Qt 4 and Qt 5 are installed, Qt 5 will be used. Pass `--with-gui=qt4` to configure to choose Qt4.
To build without GUI pass `--without-gui`.

To build with Qt 5 (recommended) you need the following:

    sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

Alternatively, to build with Qt 4 you need the following:

    sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler

libqrencode (optional) can be installed with:

    sudo apt-get install libqrencode-dev

Once these are installed, they will be found by configure and a stim-qt executable will be
built by default.

Notes
-----
To speed up the compile process you can pass `--disable-tests` and `--disable-gui-tests`. The release is built with GCC and then "strip stimd" to strip the debug
symbols, which reduces the executable size by about 90%.
