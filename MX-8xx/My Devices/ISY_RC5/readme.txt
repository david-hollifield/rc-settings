UDI ISY/IR Philips RC-5 Infrared Protocol .IRP, .HEX, and .CCF File Readme
--------------------------------------------------------------------------

The ISY/IR series of automation controllers from Universal Devices Inc.
have the capability of receiving infrared (IR) commands based on the
Philips RC-5 IR protocol which has become a de facto standard.  Almost any
so-called universal remote control will include in its code database, many
codesets which use the RC-5 protocol.  However, for use with programmable
remote controls, the complete RC-5 codeset understood by the ISY/IR series
of controllers is presented here, making it easy for the user to simply
select the number of codes he requires, without having to search a code
database for an RC-5 codeset.

Each Philips RC-5 protocol command frame consists of 14-bits, composed of
two start bits, a toggle bit, five device-code bits, and six command-code
bits.  Thus the protocol allows for 32 devices of 64 commands each, for a
total of 2048 possible unique codes.  The ISY/IR controllers support 1024
unique codes within this protocol, rolling over devices 16-31 to devices
0-15.  Therefore only the device 0 to 15 codes have been generated here.

This .zip file contains the .irp, .hex, and .ccf files for the RC-5 IR
protocol.  The .irp files are the source files for the MakeHex utility,
which generates the .hex files, which in turn serve as the source files
for the Hex2CCF utility, which generates the .ccf files.  Both the MakeHex
utility and the Hex2CCF utility are available from remotecentral.com, for
the user who would like to generate his own codes.

The MakeHex utility reads a small profile (.irp) file which describes the
desired protocol, and generates a .hex file containing the hex strings
representing the requested device/command codes within that protocol.

The files are named rc5modnn.xxx because the .irp files have been modified
from the rc5.irp template provided with MakeHex, to change the Time Base
from 889 to 833, which represents 30 cycles of 36kHz carrier (27.7..
microseconds X 30 = 833.3.. microseconds) rather than the original 32
cycles (27.7.. microseconds X 32 = 888.8.. microseconds).  This was done
because ISY did not recongnise the codes with the original time base.

The .hex files contain standard ASCII text.  The hex strings for each code
may be copied and pasted into any IR device software which understands
such hex strings.

The Hex2CCF utility reads a MakeHex .hex file, and generates a standard
Pronto .ccf file, which may be used by any software which understands the
Pronto .ccf format.  This includes the Universal Browser found in the
editor software included with computer programmable remote controls from
Universal Remote Controls (URC).  These files were tested with an MX-850
remote control and an ISY-99i/IR PRO controller.

Darrell Peters
Universal Devices Inc.
http://www.universal-devices.com
