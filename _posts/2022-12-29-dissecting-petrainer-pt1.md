---
layout: post
title: "Dissecting an RF Shock Collar (Part 1 - Initial research)"
description: ""
tags:
 - Reverse Engineering
 - Hardware Hacking
---

This is a multi-part series:
- [Part 1 - Initial research]({{ page.url | escape }})
- TODO: Part 2 - Collar teardown
- TODO: Part 3 - Signal reverse engineering
- TODO: Part 4 - Building our own wireless control board

## Premise

I was recently inspired to do some hardware hacking after discovering a project called [PiShock](), which uses a Raspberry Pi to communicate with an RF shock collar, enabling it to be controlled remotely over the internet. Unfortunately the details of this project aren't openly available, so we'll have to do some investigating on our own to figure out how they did it.

## Gathering Information

From the creator's original [Reddit post](https://www.reddit.com/r/BdsmDIY/comments/f9fw2a/long_distance_shock_collar/) and various images online, we can figure out some details about their setup:
- Raspberry Pi Zero W
- Unknown RF transmitter
- 3D printed case
- Petrainer PET998DB E-Collar

Looking up the collar, we find there's a number of different models that seem to be almost identical - the [PET998DB1](https://ipets-mall.com/products/petrainer-pet998db1), [PET998DBB1](https://ipets-mall.com/products/petrainer-pet998dbb1), and [PET998DBU](https://ipets-mall.com/products/petrainer-pet998dbu). As far as I can tell, the only difference is that the PET998DBU has a micro USB connector for charging, while the other two have a barrel jack. The remotes for all of these look identical, so it's probably safe to assume they all use the same (or at least a very similar) protocol to communicate.

All the models have an adjustable shock between 0-100, an adjustable vibration between 0-100, a beep, and a toggleable LED.

## Prior Research

There's a lot of prior research on these collars:
- (Unspecified) https://gist.github.com/tkuester/67f2d8f5c03aee22c6d7
- (PET998DRB) http://brettleaver.com/collar/
- (PET998DRU) https://reverseengineering.stackexchange.com/questions/19671/need-help-to-reverse-engineer-a-dog-collar-transmitter

And some other helpful information I found:
- FCC Test Report: https://fccid.io/YIC201507-998DB/Test-Report/Test-Report-2759146

From this, we know that the collar uses a 433.97Mhz wireless signal. The signal starts with an extra long pulse and then sends short or long pulses for a 0 or a 1 bit respectively. There shouldn't be any extra encoding or security measures in the signal.

## What's Next?

It looks like this project is 100% doable, so let's get one ordered and start playing with it!

I found the two-collar bundle on sale for just $15 [on Amazon](https://www.amazon.com/gp/product/B00W6ZHZMI), and also went ahead and ordered an [RTL-SDR dongle](https://www.amazon.com/gp/product/B0129EBDS2) to help with reverse engineering the signal and a cheap [433Mhz kit](http://hiletgo.com/ProductDetail/2157330.html) for building our own transmitter.

I'll continue this in Part 2 once the goods arive!
