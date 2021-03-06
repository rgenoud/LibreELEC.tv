**Unofficial LibreELEC fork with CVBS support**
This is a fork of LibreELEC that supports CVBS output.
It has only been tested on Wetek LibreELEC edition (aka Wetek play - LibreELEC).

Quick Howto:
```
git clone -b libreelec-8.0.1cvbs https://github.com/rgenoud/LibreELEC.tv.git
cd LibreELEC.tv
PROJECT=WeTek_Play ARCH=arm time make image # this takes HOURS (like 5-10 hours the first time)
```
NB: This will use a lot of disk space in LibreELEC.tv (~16Gio) and in ~/.ccache-libreelec (~3Gio).
You can use another directoty for ccache with the option CCACHE_DIR=/my_scratch_partition/ccache-libreelec
ccache is usefull for speed-up next compilations.

Once it's finished, you can copy the tar for update:
```
scp target/LibreELEC-WeTek_Play.arm-8.0.1cvbs.tar wetek_ip_address:/storage/.update/
```
At last, you need to set the fallback cap:
```
ssh wetek_ip_address "echo 576cvbs > /storage/.kodi/userdata/fallback_cap"
```
NB: 480cvbs is also supported.
NB2: override_cap can be used instead of fallback_cap. In this case, HDMI won't work and kodi will use CVBS by default.

Enjoy !

# LibreELEC

LibreELEC is a 'Just enough OS' Linux distribution for running the award-winning [Kodi](http://kodi.tv) software on popular mediacentre hardware. LibreELEC is a conservative fork of the popular [OpenELEC](http://openelec.tv) project with a stronger focus on pre-release testing and post-release change management. Further information on the project can be found on the [LibreELEC website](https://libreelec.tv).

**Issues & Support**

Please report issues via the [LibreELEC forum: Bug Reports](http://forum.libreelec.tv/forum-35.html). Please ask support questions in the [LibreELEC forum: Help & Support](http://forum.libreelec.tv/forum-3.html) or ask a member of project staff in the #libreelec IRC channel on Freenode.

**Donations**

Contributions towards current project funding goals can be sent via PayPal to donations@libreelec.tv

**License**

LibreELEC original code is released under [GPLv2](http://www.gnu.org/licenses/gpl-2.0.html).

**Copyright**

As LibreELEC includes code from many upstream projects it includes many copyright owners. LibreELEC makes NO claim of copyright on any upstream code. However all original LibreELEC authored code is copyright LibreELEC.tv. For a complete copyright list please checkout the source code to examine license headers. Unless expressly stated otherwise all code submitted to the LibreELEC project (in any form) is licensed under [GPLv2](http://www.gnu.org/licenses/gpl-2.0.html) and copyright is donated to LibreELEC.tv. This approach allows the project to stay manageable in the long term by giving us freedom to maintain the code as part of the whole without the management overhead of preserving contact with every submitter, e.g. GPLv3. You are absolutely free to retain copyright. To retain copyright simply add a copyright header to each submitted code page. If you submit code that is not your own work it is your responsibility to place a header stating the copyright.
