## Keylogger for Windows, Linux and Mac
Read below for installation instructions.

---

### Windows
Simply compile into an .exe, and then run. 

There are two files; klog_visible and klog_invisible. It is pretty simple, but I will expand:

`klog_visible` is visible, and the window does not close when typing. Great for testing it out. `klog_invisible` makes the window of the logger disappear, and it also starts up hidden from view. Note that it is still visible in the task manager.

Both of these save the keystrokes to a .txt file when closed.

---

### Mac
This is a little more complicated, as its Apple after all! Please note, it does not work for secure areas such as password inputs. I have not found a work around yet.

#### Installation
Download the repo. It will install in `/usr/local/bin/keylogger`.

Install it:

 `$ git clone https://github.com/GiacomoLaw/Keylogger && cd keylogger`

`$ make && make install`

It will log to `/var/log/keystroke.log`. This may require root access, but you can change that if you want. Set where you want it to log:

`$ keylogger ~/logfile.txt`

`Logging to: /var/log/keystroke.log`

Want to make it start on system startup?

`$ sudo make uninstall`

That will run it on startup.

#### Uninstall
`$ sudo make uninstall`

This will uninstall the program, but not the logs.

---

### Linux
#### Installation

You'll need to install python-xlib if you don't have it.

You can install it using `pip`:

`pip install python-xlib`

...or your system package manager:

`sudo apt-get install python-xlib`

Check that you have git installed, and then run this.

`git clone https://github.com/GiacomoLaw/Keylogger`

This will clone this entire repo. Find the linux folder, extract it, and open it. Rename the extracted folder to `linux-logger` Then run this:

`giacomo@vostro:~$ cd linux-logger/`

#### Options
There are several options that can be set with environment variables:

- `pylogger_file`: File path to use as the log file.
Default: `~/Desktop/file.log`
- `pylogger_cancel`: The key to use as the cancel key, in character form.
Default: \`
- `pylogger_clean`: Whether to clear the file on startup. This can be set to anything to clear the file.
Default: No (not set)

#### Running

You can use Python 2 or 3 to run the logger.

To run it:
```
$ python keylogger.py
<class 'Xlib.protocol.request.QueryExtension'>
<class 'Xlib.protocol.request.QueryExtension'>
RECORD extension version 1.13
```

Or, using the options mentioned above:
```bash
# This tells the logger to use /home/me/myfile.txt,
# clearing the file on startup, and using ! as the
# cancel key.
# You don't have to use all of these options at once, or any at all.
$ pylogger_file="/home/me/myfile.txt" pylogger_clean=1 pylogger_cancel="!" python keylogger.py
```

The keylogger is now running! It will log your strokes to the file you
specified. Stop it by hitting the cancel key (grave or \`, if not set with
`pylogger_cancel`. That's the one under escape on a standard keyboard.)

You can make it run on startup:

`$ sudo make startup`

---

### Authors and Contributors
@GiacomoLaw. Please note that the contributors are not responsible for any results of the use of this program.

### Support or Contact
Having trouble with Pages? Check out the [repo](https://github.com/GiacomoLaw/Keylogger) to submit an issue, or even fork it and fix it. You can also email me [here](mailto:thenerdystudent@gmail.com).
