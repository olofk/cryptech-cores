# cryptech-cores
Core description files for the Cryptech project

## How to use

### Install FuseSoC
Clone the FuseSoC repo from https://github.com/olofk/fusesoc, cd into fusesoc and run:

    autoreconf -i && ./configure && make
    sudo make install
    fusesoc init

Test your installation by running `fusesoc list-cores`. This should return the list of cores that FuseSoC has found

### Install cryptech-cores
1. Clone the cryptech-cores repo.

2. Create an empty workspace directory.
3. Enter the directory and copy ~/.local/share/fusesoc/fusesoc.conf here
4. Edit fusesoc.conf and add the location of the cloned cryptech-cores repo to the space-separated list of FuseSoC core libraries (cores_root)
5. Run `fusesoc list-cores` from this directory to verify that the new cryptech cores were found
6. Try out the cores by running for example `fusesoc sim cryptech-aes` to run the regression tests on the Cryptech AES core (this requires the Icarus Verilog simulator. If you want to use modelsim, run instead `fusesoc sim --sim=modelsim cryptech-aes`)
7. Generate the CycloneV board FPGA image by running `fusesoc build cryptech-terasic_c5g` (requires Altera Quartus)


