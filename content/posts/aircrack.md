---
title: "WIFI Cracking"
date: 2018-04-12T22:56:13-04:00
draft: true
author: "Jason Li"
description: "A tutorial of Aircrack-ng to crack WPA2 wifi passwords "
---

## Requirements

#1 Downloading Aircrack-ng.

If you have windows, you can download the zip file from the official website,
unzip it, and then navigate to it in the cmd to use the aircrack-ng commands.

if you are using linux, you can always use the git command   
```
git clone http://github.com/aircrack-ng/aircrack-ng
```
#2 Wifi-adapter

This is essential to the process as the Wifi-adapter will allow you to go Into
monitor mode.

There are 2 modes of Wifi, Monitor mode and promiscuous mode. Default wifi cards
are in promiscuous mode. Which means that you cannot see the traffic that is not
meant to you. We can compare the 2 modes as walking down the street. I  n
promiscuous mode, you cannot hear any side conversation that people are having,
since they are not meant for you. However, if you are in monitor mode, you can
hear all the side conversations even though they are not directly talking to you.

That's all for requirements. Now we can begin the actual process

## let the fun begin
Even though it's the aircrack-ng suite, the actual commands we are going to use
do not include aircrack.

First step, we have to turn on monitor mode.

your Wifi card will usually appear as wlan0 or wlan1. you can check that by either
ipconfig(windows) or ifconfig(linux).

so the command is
```
sudo airmon-ng start wlan0
```
now if you type in
```
ifconfig
```
you should be able to see that your wlan0 has turned into wlan0mon. This means
that your have successfully turned on monitor mode.

## see traveling packets around you
all you have to do now is to type in
```
airodump-ng
```
and now you should enter a console that enlist all the wifi packets around you

![airodump image](/img/airodump.png)

As you can see, the BSSID is the MAC address of the wifi, ESSID is the name of
the WIFI's name which the owner named.
