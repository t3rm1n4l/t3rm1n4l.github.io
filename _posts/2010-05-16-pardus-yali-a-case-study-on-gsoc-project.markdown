---
layout: post
status: publish
published: true
title: Pardus YALI - a case study on GSoc Project
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 505
wordpress_url: http://www.sarathlakshman.com/?p=505
date: 2010-05-16 13:08:02.000000000 +05:30
categories:
- General
- Open Source
- Pardus
- GSOC
tags:
- linux
- python
- pardus
- yali
- live installer
comments:
- id: 10410
  author: Marlena Rynkowski
  author_email: Rurup436@yahoo.com
  author_url: http://www.eaoyudriry.com
  date: '2010-12-30 12:28:58 +0530'
  date_gmt: '2010-12-30 12:28:58 +0530'
  content: Your post is informative. Safety is very important, excellent post about
    this subject, thank you for sharing.
- id: 11639
  author: Liz
  author_email: eliminatefruitflies@gmail.com
  author_url: http://fruitfliesinhouse.weebly.com
  date: '2011-08-21 11:20:47 +0530'
  date_gmt: '2011-08-21 11:20:47 +0530'
  content: Very helpful post, thanks for that! I was looking for that, hope it works
    =)
- id: 12005
  author: John Elites
  author_email: eliteenergycontractor@gmail.com
  author_url: http://www.eliteenergycontractors.com/
  date: '2012-01-18 06:13:16 +0530'
  date_gmt: '2012-01-18 06:13:16 +0530'
  content: Interesting post! Keep up the good work
---
Being a python and? code enthusiast, The most exciting feature about Pardus project is about their designs. All the of the applications pardus teams has ever written are awesome with their beauty in their code design. When ever you look at any project's code, they are very transparent, readable and highly modular designs.

I am hacking with YALI ( Yet Another Linux Installer) Project for developing a Live OS installer. I went through the basic code and came up with an over view of YALI architecture. Hope this would be helpful for future YALI contributors and developers also.

### Working of Yali4
Yali starts with xdm service, which runs start-yali4 shell script. It runs /usr/bin/yali4-bin using /usr/bin/xinit and runs in fullscreen mode without KDE WM environment.
It invokes the method yali4.default_runner() which is yali4.gui.runner.Runner()

Pardus has its own service scripting and management technology COMAR. xdm is a comar script to serve as service for loading X.

#### runner.py
Runner class servers as the major class which runs the Yali. It imports the main widget from gui/YaliWindow.py (Widget class). Widget class is Setup_ui using Ui_YaliMain (main.ui)
Resolution and screen size is set to maximum by reading QApplication.desktop()

Yali has a configuration system to behave as per different install_type.

{% highlight python %}
YALI_INSTALL,YALI_DVDINSTALL, YALI_FIRSTBOOT, YALI_OEMINSTALL, YALI_PLUGIN, YALI_PARTITIONER, YALI_RESCUE = range(7) is defined in gui/installdata.py
{% endhighlight %}

In Runner class, it checks which sets install_type variable according to the configuration.

gui/context.py defines many constants and context variables (yali4/constants.py) . yali4.sysutils.
*checkYaliParams()* is used to identify the install_type configuration,
which can be passed as argument to kernel parameter.

In Runner, it creates an installer object by passing install_type and install_option to yali4.installer.Yali(). install_option is identified by yali4.sysutils.checkYaliOptions()

#### installer.py

Yali class in installer.py is the main class which handles the Yali screens. Yali4 operates with the concept of screens.? mainStack Widget in the main.ui is called screen.
We dynamically load and remove different screen widgets required for the instalallation wizard. The base fullscreen UI is setup by runner and the screen is loaded from installer.py
Yali class in installer.py defines screen list for each install_type defined. Eg: self._screens[YALI_DVDINSTALL]

All different screens as defined as seperate .py files with name prefixed with Scr in yali4/gui. Each of these screen py files consist of a QWidget class Widget.
Widget class gui/YaliWindow.py has createWidgets() method which loads the required screens for given install_type. stackMove() method is used to show each screen
at appropriate time according to user interaction.

### Changes needed for Live installer
Most of the components required for the live installer can be reuse of existing screens from Yali4 and APIs.

To make Yali work as window mode and change the window size to a required size, yali4/Ui/main.ui require some changes as well as runner.py require some changes to prevent it from
resizing to available full screen width and height.

We need to add a new a new install_type YALI_LIVEINSTALL in gui/installdata.py

Instead of yali4/gui/ScrInstall.py, which handles installation for real pardus install medias. we have to write a new screen, ScrLiveinstall.py which can handle
installation from Live media.

yali4/installer.py will require an entry for YALI_LIVEINSTALL,
{% highlight python %}
self._screens[YALI_LIVEINSTALL] = [                              # Numbers can be used with -s paramter
                                       yali4.gui.ScrKahyaCheck,        # 00
                                       yali4.gui.ScrWelcome,             # 01
                                       yali4.gui.ScrCheckCD,             # 02
                                       yali4.gui.ScrKeyboard,            # 03
                                       yali4.gui.ScrDateTime,            # 04
                                       yali4.gui.ScrUsers,               # 05
                                       yali4.gui.ScrAdmin,               # 06
                                       yali4.gui.ScrPartitionAuto,       # 07
                                       yali4.gui.ScrPartitionManual,     # 08
                                       yali4.gui.ScrBootloader,          # 09
                                       yali4.gui.ScrSummary,             # 10
                                       yali4.gui.ScrLiveinstall,         # 11
                                       yali4.gui.ScrGoodbye              # 12
                                      ]

{% endhighlight %}

Above changes are required to bring a minimal Live installer.

I have written a basic command line minimal Pardus Live installer, <a href="http://web.sarathlakshman.com/gsoc/pardus/installer.py" target="_blank">http://web.sarathlakshman.com/gsoc/pardus/installer.py</a>. Most of the required logic appears in its code.
