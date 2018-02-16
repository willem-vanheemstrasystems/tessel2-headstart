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


