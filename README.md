# FastLED-pulse-lamp

FastLED + Arduino lamp project with multiple modes 

This is my first Arduino project, coming from 0 coding experience.

SUMMARY
Projecting purple from a traditional RGB led causes all three elements to light up to create the color. 
I liked the seperation of colors that are visible from a traditional RGB led.
While I enjoy the beautiful, more seamless blend of the WS2812B purple, I was missing that weird color separation look.
In order to recreate and highlight the effect, I decided to just treat each of three of the WS2812B LED's 
as seperate red value, green value, and blue value dedicated lights.
The lights were not bright enough in the lamp housing, so I duplicated those values to three more of the lights for a total of 6.

In addition to the color changing mode, there is a white light mode so that the lamp could work
as a more traditional light.

There is also an "off" function, which simply turns the LEDs (practically) black. 
The loop and power are still runnning, so this is not a true off switch. 

A simple NO push-button switch selects which mode the lamp should be in.

NOTES - ISSUES - WHAT DID WE LEARN!
The pulsing / color change mode was the most difficult to figure out. I was initially using the Delay function,
but I learned a very important lesson - anything I attempted to do to fade the brightness gradually and consistently 
over time was not happening because the Delay wasn't letting it keep going consistently after each color change.
I learned about millis() and how to get the Arduino to call back on itself for the time in order to sequence events BY TIME!
This way, the loop isn't doing any deadstops during the fading process. 
It made my nonfunctional, bloated code actually work and look way better.
I also learned about beatsin8, a very useful function for creating a sine wave of values at a given tempo in FastLED. 
I bet it would create some interesting effects if assigned to a color value rather than the brightness.

Coming from an electronic music background, the idea of sequencing events, sequencing by time, and sine waves 
(which to me translate as a type of LFO) made a lot of sense, and gave me quite a few ideas for future projects.

I'm still not sure about my syntax in terms of talking about the pieces of code / project, but I'll get there!
