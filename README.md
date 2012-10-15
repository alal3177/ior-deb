ior-deb
=======

The repo contains the necessary files to package [ior](https://github.com/chaos/ior.git) in a debian systems. I am trying to learn how to package in debian and this is my very first attempt :-)

Building
=======

0. Create a workspace directory, i.e $HOME/ior-building
1. Clone [ior](https://github.com/chaos/ior.git) `git clone https://github.com/chaos/ior.git`
2. Clone [ior-deb](https://github.com/alal3177/ior-deb.git) `git clone https://github.com/alal3177/ior-deb`
3. Cd into ior, run ./bootstrap to create "configure" file. You might want to install automake firt, `apt-get install automake`
4. Install ncessary tools to build deb package, `apt-get install build-essential autoconf automake autotools-dev dh-make debhelper devscripts fakeroot xutils lintian pbuilder`
5. Copy debian folder from ior=deb to ior, `cp -r ior-deb/debian ior/`
6. Install ior deps, `apt-get install libopenmpi-dev openmpi-bin mime-support libc6-i686 mawk`
7. Build the package, `dpkg-buildpackage -rfakeroot`.
8. If everything go as planned, a deb file should be in your workspace directory.
