Autopoweroff - Change history
======================================================================

The following changes have been incorporated in the below mentioned
versions:


Version 3.2.1 - 2020-05-31
--------------------------------------------------

* Fixed [GH008](https://github.com/deragon/autopoweroff/issues/8):  'Autopoweroff High CPU usage when only condition remaining is a living remote server'

* Some refactoring in `autopoweroffd`.


Version 3.2.0 - 2020-05-26
--------------------------------------------------

* Implemented [GH009](https://github.com/deragon/autopoweroff/issues/9):  Python3 support

>Code migrated to Python 3.

* Accelerometer "lis3lv02d" ignored.

>Code to ignore accelerometers has been introduced into Autopoweroff.  Currently, only the "lis3lv02d" accelerometer is being ignored, being hardcoded.  Not ideal; more work needs to be done so the code becomes generic and ignores any accelerometer.

>Accelerometers are devices that are way to sensitive for Autopoweroff. A laptop laying on a stable table with nobody touching it will still have its accelerometer reporting movement.  Thus, it is not reasonable nor necessary to take this devices into account when attempting to figure out if the device is being used or not by a person.


Version 3.1.0 - 2019-04-31
--------------------------------------------------

* Fixed [GH001](https://github.com/deragon/autopoweroff/issues/1):  Polkit replaces gksu.  This is the main feature of 3.1.0, allowing
          Autopoweroff to work under modern Linux distributions such as
          Ubuntu 18.04 LTS.  Thanks to @edgimar from GitHub for providing
          the solution.
* Fixed [GH002](https://github.com/deragon/autopoweroff/issues/2):  Added Python's GI module as a dependency.
* Dependency fix for Fedora 29 and openSUSE 15.
* Build improvements.
* Various little fixes.



Version 3.0.0 - 2016-07-18
--------------------------------------------------

3.0.0 has been a major rework of the project.

* Autopoweroff is not limited any more to only poweroff the computer.  It can now execute any command when all conditions are met.
* The GUI has been improved and extended to support the new functionality.  The GUI framework was upgraded to the latest GTK API available on Ubuntu LTS 14.01 Trusty Thar.
* More multithreading has been introduced to simplify the management of asynchronous events.
* PID and cancel file where previously stored under /tmp, which under Ubuntu (and probably Debian), is erased at each reboot. They were moved under /var where they should have been in the first place.
* Made the /etc/init.d/autopoweroff LSB version compliant to the standard.
* Introduced a new icon in SVG format, now the default. PNG format is available for window managers which do not support the SVG format.
* Replaced the GNU 2.0 License text with another GNU 2.0 License text which was updated by the Free Software Foundation. Fundamentally though, the license has not changed.
* Fixed bug regarding 'no shutdown range' crossing over midnight.  Thanks to Kyle Shim (kyle.s.shim@gmail.com) for reporting and proving a patch to fix it.
* Fixed bug in script building .deb package where the wrong value of \${autopoweroff\_bindir} was being used.
* Fixed bug in .deb package; previously, autopoweroff-upgrade was not called upon installation of the package.
* The documentation was converted from [AurigaDoc](http://aurigadoc.sourceforge.net/) to Markdown.
* Moved the source from [Sourceforge](http://autopoweroff.sourceforge.net) to [GitHub](https://github.com/deragon/autopoweroff).



Version 2.9.1 - 2008-06-01
--------------------------------------------------

Following feedback received from user [Tomas Klema](http://tklema.info)
and another anonymous one, multiple small improvements and fixes were
introduced in this version of Autopoweroff:

* Moved the icon from "Applications/System Tools" to "System/Administration".
* LSB and rc.status based bootstrap scripts now supported in the RPMs.
* Now supports officially the three main distributions: Ubuntu, OpenSuSE and
  Fedora.
* \`arping\` is now also used in addition to \`ping\` to test if dependant
  hosts are up. This cascading of tests increase the chances to detect a
  dependant host if the host make use of a firewall.
* If /dev/input/by-path/\* are non-existant on a system, /dev/input/\* entries
  are used instead. This will allow Autopoweroff to detect user events on
  Ubuntu 06.06 for instance.
* About dialog would not close properly. This has been fixed.
* Some small GUI improvement were introduced. Mainly, some widgets were simply
  to small for the font size. They were slightly increased.
* Files in subversion were moved to trunk/. branches/ and tags/ where created
  to better manage the software.



Version 2.9.0 - 2008-05-11
--------------------------------------------------

This release is a complete overhaul of the project.\

* Ubuntu support introduced.
* New techniques are used to probe device, which now include USB devices. For
  the techies, /dev/input/by-path devices get probed.  Modern kernels are
  required.
* Subversion is now used instead of CVS for software configuration management.



Version 2.1.0 - 2004-01-19
--------------------------------------------------

* Like a screensaver, Autopoweroff now detects idle time on the server by
  scanning for keyboard and mouse activity. Currently, PS/2 keyboards and PS/2
  & serial mices are supported (USB devices are unfortunatly not detected
  yet).
* Added automatic configuration file upgrade. If you upgrade Autopoweroff and
  autopoweroff.conf configuration file format has changed, it will
  automatically be upgraded to the new format while preserving the previous
  configuration.
* If Autopoweroff, upon startup, discovers that another instance of itself is
  already running, instead of quiting it kills the old instance and continues.
* Replaced calls to "reboot" and "poweroff" with their corresponding
  "shutdown" command. Some user wrote to me asking where reboot and poweroff
  could be obtained, so I assume that they are not always available.



Version 2.0.0 - 2003-11-23
--------------------------------------------------

* Created a user interface to simplify configuration.
* Miscelleanous Autopoweroff events are now reported in syslog, for tracking
  purposes.
* Removed Gnome dependency, for servers running in text mode only.



Version 1.2.0 - 2003-06-07
--------------------------------------------------

* Fixed \*.desktop files so that the icons now appear in the gnome "system
  tools" menu even if no locale is set.



Version 1.1.1 - 2003-05-03
--------------------------------------------------

* RPM installation now fully recognize Mandrake.
* Improved the Autopoweroff Configuration section of the document and the
  comments in /etc/autopoweroff.conf.
* Added the `Supported distributions` section.



Version 1.1.0 - 2003-04-27
--------------------------------------------------

* Automatic Gnome installation. Under Red Hat 9.0, the cancel and enable
  scripts now have icons showing up under the "System tools" menu.
* Improved the installation and uninstallation of the software from a tarball.



Version 1.0.1 - 2003-04-14
--------------------------------------------------

* Used autoconf to allow installation from a tarball.
* Started using [AurigaDoc](http://aurigadoc.sourceforge.net/) for creating
  this document.



Miscelleanous
======================================================================

* This document source is a Markdown document.  The following tools are used
  for editing it.

  * [Vim text editor](http://www.vim.org/)
  * [MdCharm](http://www.mdcharm.com/)



Contact
======================================================================

If you have any questions or issues with this software, you can contact
the following persons:

Author:    Hans Deragon
Email:     <hans@deragon.biz>
Website:   [www.deragon.biz](http://www.deragon.biz)
