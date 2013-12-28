enconfig
========

enconfig is a  thin wrapper around [encfs] written in bash. Encfs is a
convenient little tool for managing encrypted directories within the
filesystem leveraging Fuse.

Unfortunately, it comes without any management interface making it easy
to loose track of you encfs's. enconfig tries to fill that little gap.


Installation
============

You can install enconfig in a root-shell as follows:

    # git clone github.com/baccenfutter/enconfig.git
    # ln -s $PWD/enconfig/enconfig /usr/local/bin/
    # ln -s /usr/local/bin/enconfig /usr/local/bin/encup
    # ln -s /usr/local/bin/enconfig /usr/local/bin/encdown


Configuration
=============

The main configuration file is: ~/.privatedirs

In this file create blank-seperated encfs directory pair line with the
following pattern:

    /absolute/path/to/encfs /absolute/path/to/mountpoint
    /absolute/path/to/another_encfs /absolute/path/to/another_mountpoint


Usage
=====

After setting up ~/.privatedirs you can use enconfig like this:

    # enconfig      - list all encfs mountpoints
    # encup 1       - mount directory pair from first line in
                      ~/.privatedirs
    # encdown 1     - unmount directory pair from first in line
                      ~/.privatdirs
    # encup         - mount all directory pais in ~/.privatedirs
    # encdown       - unmount all directory pairs in ~/.privatedirs


[1]: http://www.arg0.net/encfs
