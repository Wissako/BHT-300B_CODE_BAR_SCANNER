# DENSO BHT Inventory Scanner

A custom inventory management utility developed in **BHT-BASIC 4.0** for **DENSO BHT-300B** and **BHT-8000** series Handy Terminals. 

This program transforms the terminal into a standalone inventory collector, allowing users to scan barcodes, input quantities, and subsequently transfer the collected data to a host PC via a serial connection.

### Features
* **Barcode Capture:** Scans and captures barcodes using the terminal's built-in laser.
* **Data Entry:** Allows manual input of quantities for each scanned item.
* **Local Storage:** Saves scanned records locally in the device's flash memory as a text file (`MOLDURAS.TXT`) in CSV format.
* **Paginated Viewer:** Includes an on-device UI to review saved records in batches to prevent screen overflow.
* **Serial Transfer:** Exports the data file to a host PC via the communication cradle (compatible with *BHTComm 2005* via YMODEM/Serial).
* **Memory Management:** Built-in option to safely clear the data file after a successful transfer.

### Requirements
* DENSO BHT-300B or BHT-8000 series terminal.
* DENSO BHT-BASIC 4.0 Compiler.
* Communication Cradle with a straight-through RS-232 serial cable (or USB-to-Serial adapter).

### Compilation & Deployment Guide

Since BHT terminals cannot run raw basic text files, you must compile the `.bas` source code into a binary format before transferring it to the device.

1. **Open the Compiler:** Launch your DENSO BHT-BASIC Compiler (typically `BHTB32.EXE` or via the BHT-BASIC IDE).
2. **Load Source:** Open the `Molduras.bas` file in the environment.
3. **Compile:** Run the build/compile command. 
4. **Verify Output:** Check the compiler's output log. A successful build will explicitly display `0000 Error statement`. If any syntax errors occur, the log will point to the exact line number that needs correction.
5. **Locate Executable:** Once successfully compiled, a binary file (usually named `Molduras.bht`, `Molduras.pd3`, or `Molduras.en3` depending on your compiler version) will be generated in the same folder.
6. **Transfer to Device:** Put the terminal in the cradle, set it to "Receive" (Download) mode via the System Menu, and use a tool like **BHTComm 2005** to send the compiled binary file to the scanner.
