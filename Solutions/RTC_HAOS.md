# Introduction
Home Assistant works best when it's connected to the internet. It can control devices remotely, it can gather info from various services and it **needs** to synchronise the time with a web server (NTP Server).  
The problem comes when we are in an offline environment. I would personally like to have full control of my home even when I'm offline.  
From my testing, Home Assisstant OS can boot up even if there is no internet. However, it doesn't always boot up properly. This means that there are some add-ons missing in the supervisor and the supervisor doesn't work correctly.  

## The Real Problem
The real problem with not having internet is getting the time from the internet. The Raspberry Pi usually doesn't have a built-in clock to know the time. Once it's turned off, the clock inside the Pi stops
and needs to be readjusted the next time it boots up. This causes a problem with any automations. For example, I've set my alarm to wake me up at 8 AM. In this scenario, I have no internet. Imagine that I had a power outage for
an hour and a half. The Pi thinks that the clock is 8 AM, when in reality it is 9:30 AM. By this time, I would've missed my bus, or work. Now you might see why this is a problem.  

# The RTC
The RTC is an abbreviation for *Real Time Clock*. This is simply a device that is inside most computers which is always running and consumes very little power. This causes it to be a **real** time clock.
It keeps track of time at all times, so it always has some accurate estimation of the real time. There are cheap **RTC modules that are sold in electronic stores**.  
The good thing is: Raspberry Pis support connecting an RTC. The bad thing is: Home Assistant OS doesn't support syncing time from an RTC. It has to be done manually.

## Connecting the RTC
There are RTCs designed to be used with a Raspberry Pi. These can be used right away without any additions. Just open up the datasheet of the module and see how it can be connected.
Or simply google "How to connect XXX to Raspberry Pi".  
The RTC module we had was not designed for the Raspberry Pi so we had to do some modifications to it. This would require some knowledge in soldering and desoldering.

[This is the exact model of the RTC module we had.]()
