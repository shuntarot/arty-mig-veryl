# Arty FPGA sample for MIG and JTAG-AXI in Veryl

Vivado 2024.1 or higher is required.

## Build RTL

Generate system verylog code from veryl code. Run veryl command in top directory.

```
veryl build
```


## Build IP

Need IP generation before top-level synthesis or simulation.

- MIG
- JTAG-AXI
- MMCM

are generated.

```
cd ip
make build
```

If Arty board file are not ready, download
[board_files](https://github.com/Digilent/vivado-boards/tree/master/new/board_files "board_files")
and set path in ip/Makefile

## Build

Arty-7 35T FPGA image are built. It takes about 5 minutes on my machine.

```
cd syn
make build
```

## Program

Need USB connected Arty board.

```
cd syn
make program
```

## Run

Test DDR3 R/W via JTAG-AXI.

```
cd test/01_axi_rw
make
```

## Run RTL Simulation

DDR3 initialization and connection test only.

```
cd sim
make
```
