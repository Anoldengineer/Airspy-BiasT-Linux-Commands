# Airspy-BiasT-Linux-Commands
Linux commands to turn the Airspy SDR Bias Tee on and off

While the Airspy is an awesome little SDR, the documentation leaves much to be desired, particularly for Linux.
These commands will allow you to turn the Bias Tee power ON or OFF from the command line.

Dependencies: airspy

Airspy installs a number of commands but the one of interest here is airspy_gpio.
You can type the command with no arguments to see the full usage information.
This command allows reading and setting of various pins by providing the port (p) and pin number (n).
The status of all the pins can be displayed by typing:

airspy_gpio -r

The Bias Tee pin is Port 1, Number 13.  The command to turn the Bias Tee ON is:

airspy_gpio -p1 -n13 -w 1

To turn the Bias Tee OFF use:

airspy_gpio -p1 -n13 -w 0

In either case, if successful the command will respond that either a 0 or 1
has been written to gpio[1][13].  You can read the pin status to verify the
state with:

airspy_gpio -p1 -n13 -r


