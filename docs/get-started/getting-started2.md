# Part 2: Take the control

## The remote control part: 💊 You can control the Matrix.

The gate running on your board allows you to take control of any service loaded on your device.

### Setup development environment

We will use Python with the default library of Luos called pyluos.
To install it, run:

```bash
pip install pyluos
```

### Connect and control your device

Pyluos provides a set of tools. To control you device, run:

```bash
pyluos-shell
```

This command will find the serial port of your device and mount it into a "device" object.

For example:

```bash
$ pyluos-shell
Searching for a gate available
Testing /dev/cu.usbserial-D308N885
Testing /dev/cu.usbmodem13102
Connected to "/dev/cu.usbmodem13102".
Sending detection signal.
Waiting for routing table...
Device setup.

 Hit Ctrl-D to exit this interpreter.

Your luos device have been successfully mounted into a "device" object:
  ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
  ┃  ╭node 1            /!\ Not certified            ┃
  ┃  │  Type                Alias               ID   ┃
  ┃  ├> State               led                 2    ┃
  ┃  ├> Pipe                Pipe                3    ┃
  ┃  ├> Gate                gate                1    ┃
  ┃  ╰> Unknown             blinker             4    ┃
╔>┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

```

Now that you are on an IPython command line, you can run Python scripts in it.
The `device` object is your real device and you can interact with it. For example, try to execute these lines one by one:

In \[1\]: `device.blinker.time=0.25`  
In \[2\]: `device.blinker.pause()`  
In \[3\]: `device.led.state=True`  
In \[4\]: `device.led.state=False`  
In \[5\]: `device.blinker.play()`  


Your development environment is now completely installed and you can remote control your device! Well done.
