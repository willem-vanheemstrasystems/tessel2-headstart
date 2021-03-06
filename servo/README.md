README.md

# Servo

Based on 'Servo' at http://tessel.github.io/t2-start/modules/servo.html

Initialize a tessel project inside the servo directory:

```t2 init```

Plug servo into port “1” on the module as shown.

- the brown wire (ground) goes to -
- the red wire (power) goes to +
- the yellow wire (signal) goes to S

Plug 5V adapter into the barrel jack on the servo module, then plug into wall power.

Install by typing ```npm install servo-pca9685``` into the command line.

Rename “index.js” to “servo.js” and replace the file’s contents with the following:

```
// Any copyright is dedicated to the Public Domain.
// http://creativecommons.org/publicdomain/zero/1.0/

/*********************************************
This servo module demo turns the servo around
1/10 of its full rotation  every 500ms, then
resets it after 10 turns, reading out position
to the console at each movement.
*********************************************/

var tessel = require('tessel');
var servolib = require('servo-pca9685');

var servo = servolib.use(tessel.port['A']);

var servo1 = 1; // We have a servo plugged in at position 1

servo.on('ready', function () {
  var position = 0;  //  Target position of the servo between 0 (min) and 1 (max).

  //  Set the minimum and maximum duty cycle for servo 1.
  //  If the servo doesn't move to its full extent or stalls out
  //  and gets hot, try tuning these values (0.05 and 0.12).
  //  Moving them towards each other = less movement range
  //  Moving them apart = more range, more likely to stall and burn out
  servo.configure(servo1, 0.05, 0.12, function () {
    setInterval(function () {
      console.log('Position (in range 0-1):', position);
      //  Set servo #1 to position pos.
      servo.move(servo1, position);

      // Increment by 10% (~18 deg for a normal servo)
      position += 0.1;
      if (position > 1) {
        position = 0; // Reset servo position
      }
    }, 500); // Every 500 milliseconds
  });
});
```

Save the file.

In your command line, ```t2 run servo.js``` Watch your servo move!

To see what else you can do with the servo module, see the [module docs](https://github.com/tessel/servo-pca9685) here.

If you run into any issues you can check out the [servo forums](https://forums.tessel.io/c/modules/servo).

Have a look at the [Robot Arm](https://tessel.hackster.io/esvit/robot-arm-controlling-with-javascript-bdfeeb) that you can control with JavaScript using the Tessel2 and the servo module for Tessel2.

