# Espruino

I attended a guest lecture by [Niels Leenheer](https://github.com/NielsLeenheer) where he spoke at length about cool modern Web APIs that are available these days.
One of the things he showed was a demonstration where he was able to program and then control an ESP8266 controlled car using Javascript.
The browser would connect over Bluetooth with it and make it work.
I was pretty impressed by this, so I did some more digging to find out how this all worked, because no way that a language like Javascript could actually do something so low level right?

I studied Network & Systems Engineering, where I studied software engineering for microcontrollers, among other things.
Since I know that microcontrollers are traditionally programmed with languages like C and C++ (and more recently others like Go and Rust), I was quite skeptical about "programming Javascript and running it on a microcontroller".
How are you going to get Javascript running on a microcontroller?

## Espruino

It turned out that most of the internal logic was indeed not handled by Javascript at all, but massive firmware written in C, what a disappointment.
I would have expected nothing less than Javascript compiled down straight to machine code running on an ESP8266.
Jokes aside, the project that powered all of it is called [Espruino](https://github.com/espruino/Espruino).

It turns out that the Espruino project is actually active since 2012, predating the popular ESP8266 itself by 2 years!
The project aims to make it possible to program embedded chips using Javascript, rather than the more traditional option of C/C++.
The main selling point is that JS code is often highly event-based, which allows the microchip to be far more power-efficient during idle than a traditional implementation using C/C++ would have been able to achieve.
They sell a board called the [Puck.js](https://www.espruino.com/Puck.js) where their claim is that the device can run on as little 3uA [source](https://www.espruino.com/Puck.js#power-consumption) while idle and waiting for commands.
This is quite impressive, especially considering that the ESP32 chip draws 10uA in deep-sleep mode [source](https://lastminuteengineers.com/esp32-sleep-modes-power-consumption/), where basically everything except the RTC (Real-time clock) turns off to save power.

According to their documentation, Espruino is fast as well [source](https://www.espruino.com/Performance).
It wouldn't be able to rival actual low level implementations of the same code however, since there still needs to be processing power used for the JS interpreter.
However, they have made an excellent workaround for this by allowing the developer to write C or assembly code within the Javascript.

## My thoughts

I started extremely skeptical, but it turns out that that wasn't necessary at all.
The main concerns I had with running Javascript on a microcontroller were the speed and power consumption, since you need to have an interpreter running.
However, as it turns out there is no need for any of such concerns.
The developers of Espruino have thought about all of this and actually impressed me with their claims of the power consumption.
It makes sense too, given the event-based nature of Javascript.

After all of this, I still don't think I will ever use Espruino, however :).
I don't program microcontrollers anymore, not until the cloud starts running on microcontrollers.
