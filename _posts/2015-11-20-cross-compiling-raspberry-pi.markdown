---
layout: post
title:  "Cross-compiling-raspberry-pi"
date:   2015-11-20 17:19
categories: raspberrypi arm 
---

Compiling or installing things on a RaspberryPi is not the best of
experiences. It doesn't have the best CPU performance, the storage medium is
far from fast and, if you work remotely, the bandwidth gods might not want to
hear your pleas of good connectivity.

Fortunately there is a better way to do this, and that's cross-compiling on your own machine. There are already tutorials on how to do this, but some that I used are already missing from the internet, so blame me for plagiarism if you will.

Start with downloading an image that works on your Raspberry Pi. We unzip it and then mount it as a loopback device. To do this, first check the first loop device available:

{% highlight bash %}

$ sudo losetup -f
/dev/loop1

{% endhighlight %}

Remember this output, it will come in handy later. 

The next step is *mounting* the image on the loopback device:

{% highlight bash %}

$ sudo losetup -f <name-of-image>.img
$ sudo partprobe /dev/loop1

{% endhighlight %}

The `partprobe` command will notify the kernel that there is a new device on `/dev/loop1` and it will make its partitions available for mounting. 

 _TODO: give mounting example_


For the ARM architecture emulation we need qemu, specifically the `qemu-user-static` package. Install it and copy it inside 

{% highlight bash %}

$ sudo apt-get install qemu-user-static
$ sudo partprobe /dev/loop1

{% endhighlight %}
