
# Table of Contents

1.  [mt-cvw](#org4b9c430)
    1.  [Setup](#orgd9ff042)


<a id="org4b9c430"></a>

# mt-cvw

Fine-grain multi-thread implementation of the openhwgroup&rsquo;s CV Wally


<a id="orgd9ff042"></a>

## Setup

The project is developed on Ubuntu 24.04 LTS development environment because this distribution is readily supported with the Wally toolchain.

-   Installing pre-requisites

    git submodule update --init --recursive
    source ./cvw/setup.sh
    sudo $WALLY/bin/wally-package-install.sh
    $WALLY/bin/wally-tool-chain-install.sh

-   Running elf files with verilator and spike

    cd $WALLY/examples/C/hello
    make
    wsim rv64gc --sim verilator --elf hello --args "+MAKE_VCD=1"
    spike hello
    cd fibonacci
    make
    wsim rv64gc --sim verilator --elf fibonacci --args "+MAKE_VCD=1"
    spike fibonacci

