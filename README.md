# Community Z Tools
Bart Massey 2016-01-25

This directory contains the Community Z Tools, all
piled together for reasonable installation. Notes on
installation and use:

## `CZTSans.ttf`

Start by installing this TrueType font as your OS
requires. On Linux, you should pretty much just be able to
stick it in a subdirectory of your home directory called
`.fonts` and X apps will find it there.

## `czt.jar`

This is the Java Archive containing the core Community Z
Tools. I currently have it installed a couple of places on
my Linux system:

* It is installed in a standard place where the
  driver shell script I provide can find it: see below.
* It is installed where `jedit` can find it: see below.

## `czt.sh`

This is a shell script so that CZT can conveniently be run
from the command line. On my Linux box I have it installed
in my personal bin as `czt` and marked executable. This
allows me to, for example, typecheck some Z by saying
something like

        czt example.tex

This should also work on a Mac. On a Windows box, you can do
something similar with a `.bat` file. Make sure that you
edit the path inside the script to point to the right place.

## JEdit Plugins

(Note that if you are committed to LaTeX-only Z, you can
avoid this whole section. It might well be worth it.)

There are four CZT plugins for the open-source Java-based
editor [JEdit](http://www.jedit.org).

* `ZCharMap.jar`
* `ZEvesPlugin.jar`
* `ZLivePlugin.jar`
* `ZSideKick.jar`

To use them, first install JEdit. On my Debian Linux box, I
can just `apt-get install jedit`, but your mileage may vary.

In Debian the `/usr/bin/jedit` script actually uses an old
version of the Java Runtime. You need to use JRT version 8
with JEdit for the plugins to work properly. You can
hand-edit the Debian script in the obvious way to make
this happen, but make sure you have the `openjdk-8-jre` package
installed. (You can also make things work with
`oracle-java8-installer`, but it's a little trickier and
doesn't seem to be necessary.)

On Mac or Windows, you should be able to download and
install the appropriate version of Oracle or OpenJDK java
and install JEdit from its website.

Once you have JEdit installed, find its plugin JAR
directory. (On my Linux box, it's `$HOME/.jedit/jars`.)
Dump the four plugins in there and run JEdit and configure
the plugins using its settings. JEdit will ask you to
install the `SideKick` and `ErrorList` plugins as well,
which is straightforward.

Finally, make sure that the default JEdit font is set to
CZT, so that you can do UTF-8 editing. The default file
extension for UTF-8 Z is `.utf8`, which is annoyingly
nonspecific.

To use the JEdit plugins on some Z, you need to parse the Z
buffer using SideKick, You can then mess with the other
plugins. Right now, the only one we'll be using is
ZSideKick. You can use the ZCharMap plugin to help you type
UTF-8 Z.

## `czt.sty`, `czt-latex-guide.pdf`

The CZT LaTeX style, modified a bit by me to stop its
buggy whining, along with a user manual.

## `example.tex`, `example.utf8`

Example Z specification in LaTeX and UTF-8 formats. I haven't
got the CZT automatic conversion tools to work, which is too
bad. I strongly suggest learning to use LaTeX for Z sooner
rather than later.
