# NightStake
Code originally by The Bytecoin and Cryptonote Team, edited by System96 & Blockinator

## What is Nightstake?
NightStake is a Pow/PoS coin built on the CryptoNight algorithm.

## Build instructions:

### Ubuntu

Download dependencies

> sudo apt-get install build-essential git cmake libboost1.55-all-dev

Then, cd into the Cryptostake folder and make

> make

Wait for the compile, and you'll be done.

If you are getting a compile error on Ubuntu regarding RocksDB, go into external/rocksdb/build_tools and do this command

> chmod 755 build_detect_platform

That should fix the issue and the compile should work.

### Windows compile

Windows compile is a little more tricky, but doable. Download Boost version over 1.5.5. I would suggest using an official installer to
download it. Make sure the version corresponds to your MSVC version (if your msvc version is 14 for example in the cmake generator, download
the msvc-14 version of the boost installer)

Make sure to have MSVC 2015, you could use 2017, but I have trouble using MSbuild with 2017, and you need to use MSbuild command prompt
to create the MSVC solution file.

Here is the command you should use for creating the MSVC solution file:

> cmake -G "your-msvc-generator" -DBOOST_ROOT=file-path-to-boost -DBOOST_LIBRARYDIR=file-path-to-msvc-libs file-path-to-cmakelists.txt

After that, open the solution file in MSVC 2015, build the solution in Release mode, and after a while it should build the binaries.
