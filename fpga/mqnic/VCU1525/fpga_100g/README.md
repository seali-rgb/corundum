# Corundum mqnic for VCU1525

## Introduction

This design targets the Xilinx VCU1525 FPGA board.

* FPGA: xcvu9p-fsgd2104-2L-e
* MAC: Xilinx 100G CMAC
* PHY: 100G CAUI-4 CMAC and internal GTY transceivers
* RAM: 64 GB DDR4 2400 (4x 2G x72 DIMM)

## How to build

Run make to build.  Ensure that the Xilinx Vivado toolchain components are
in PATH.

Run make to build the driver.  Ensure the headers for the running kernel are
installed, otherwise the driver cannot be compiled.

## How to test

Run make program to program the VCU1525 board with Vivado.  Then load the
driver with insmod mqnic.ko.  Check dmesg for output from driver
initialization.


