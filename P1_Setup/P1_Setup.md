 # ORCA / Part 1 / Setup 

In this section we will look at how to set up the live coding environment for the lesson. All tutorials work only with VCV Rack, a cross-platform Eurorack modular emulator.

For the tutorial, we need to install some software. We will first install **ORCA** and then **VCV Rack**. 

### Windows / Mac

- Install the **VCV Rack** Software: https://vcvrack.com/Rack
- Install the **ORCA** Software: https://hundredrabbits.itch.io/orca

You must also install a MIDI loopback on your computer: [source](https://github.com/hundredrabbits/Orca/blob/61a3731e22ae72e4be9c1e9de57907690b6beb3e/resources/TUTORIAL.md)

- On **OSX**, setup [IAC virtual MIDI buses](https://help.ableton.com/hc/en-us/articles/209774225-Using-virtual-MIDI-buses).
- On **Windows**, setup [loopMidi](http://www.tobias-erichsen.de/software/loopmidi.html).

Then create a Loop MIDI Port.

### Linux 

First install [qjacktl](https://qjackctl.sourceforge.io/) :

```
$ sudo pacman -Syu qjacktl
```

In order to use **Orca** inside [Electron](https://electronjs.org/), follow these steps:

```
$ git clone https://github.com/hundredrabbits/Orca.git
$ cd Orca/desktop/
$ npm install
$ npm start
```

And then Install **VCV Rack**: (ArchLinux)

```
$ yay -Syu vcvrack
```



