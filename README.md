
# TCE
MicroPython Tool (tce) - Utility to interact with a MicroPython board over a serial connection.

Tce is meant to be a simple command line tool to manipulate files and run code on a MicroPython
board over its serial connection.  With tce you can send files from your computer to a MicroPython
board's file system, download files from a board to your computer, and even send a Python script
to a board to be executed.  

Note that tce by design is meant to be simple and does not support advanced interaction like a shell
or terminal to send input to a board.  Check out other MicroPython tools like [rshell](https://github.com/dhylands/rshell) 
or [mpfshell](https://github.com/wendlers/mpfshell) for more advanced interaction with boards.

##Installation

	sudo python3 setup.py install
	
## Usage

Tce is made to talk to a MicroPython board over its serial connection.  You will
need your board connected and any drivers to access it serial port installed.
Then for example to list the files on the board run a command like:

    tce --port /dev/tty.SLAB_USBtoUART ls

You should see a list of files on the board's root directory printed to the
terminal.  Note that you'll need to change the port parameter to the name or path
to the serial port that the MicroPython board is connected to.

For convenience you can set an TCE_PORT environment variable which will be used
if the port parameter is not specified.  For example on Linux or OSX:

    export TCE_PORT=/dev/tty.SLAB_USBtoUART
    tce ls

Or on Windows (untested) try the SET command:

    set TCE_PORT=COM4
    tce ls

Other commands are available, run tce with --help to see more information:

    tce --help

Each subcommand has its own help, for example to see help for the ls command  run (note you
unfortunately must have a board connected and serial port specified):

    tce --port /dev/tty.SLAB_USBtoUART ls --help
