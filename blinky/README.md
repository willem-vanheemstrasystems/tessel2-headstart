README.md

# Blinky

Based on 'Hello, (Physical) World!' at http://tessel.github.io/t2-start/blinky.html

Make sure you have installed Node, NPM and the Tessel2 driver(s), as explained at [http://tessel.github.io/t2-start/index.html](http://tessel.github.io/t2-start/index.html).

Also, make sure you have installed the Tessel2 Command Line Interpreter (CLI) globally, like so:

```javascript
npm install -g t2-cli
```

Note: If you get the common npm EACCES error, correct it by fixing npm permissions and then running ```npm install -g t2-cli``` again.

To make sure it has been installed successfully, find its version number:

```javascript
npm ts2-cli -v
```

It should give you e.g.: 3.10.10

## Find your Tessel

Plug in your Tessel over USB (use Tessel’s microUSB port, between the USB ports and the module ports).

It takes ~30s to finish booting up (track the issue [here](https://github.com/tessel/t2-firmware/issues/117)); lights will flash during this process.

Run: ```t2 list```

You should be able to see your Tessel (and any other Tessels connected to the same network as your computer):

```javascript
INFO Searching for nearby Tessels...
  USB Tessel-02A397FA63A5
```

Yay, you found it! At this point, your Tessel is operational and in communication with your computer.

Bonus: give your Tessel a name, like “Frank” or “Bulbasaur”:

```t2 rename <name>```

If you run t2 list again, you’ll see your Tessel has changed its name:

```javascript
INFO Searching for nearby Tessels...
  USB Bulbasaur
```

## Hello (Physical) World!

Blinking some lights is the “Hello World” of hardware. Let’s make those LEDs built into Tessel 2 dance for us.

In your command line, make a folder for your Tessel code, then initialize a Tessel project in that folder by running each of the following commands in the terminal:

```mkdir blinky```

```cd blinky```

```t2 init```

Have a look at [the CLI docs](https://tessel.gitbooks.io/t2-docs/content/API/CLI.html#starting-projects) to explore the ```t2 init``` command.

Great! Now you’re set up to run code on Tessel. Your “blinky” folder now contains:

- a “package.json” with some metadata Node uses for your project
- a “.tesselinclude” file which the T2 CLI uses to optimize bundle size
- an entrypoint file called “index.js”. It contains the code to make the blue and green LEDs blink.

In your command line, enter

```t2 run index.js```

to run your code in Tessel’s RAM.

Look at your Tessel! The blue and green LEDs on your Tessel’s LED panel should blink back and forth.

