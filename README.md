pdOSCseq
========

pdOSCseq is an OSC sequencer, it is shipped as a set of puredata patches.

Copyright
=========

Copyright (C) 2014 Aurélien Roux <orl@ammd.net> & Jean-Emmanuel Doucet <jean-emmanuel.doucet@groolot.net>

http://ammd.net/-DIY-

License
=======

pdOSCseq is released under the terms of the GNU General Public License version 2 or later.

Requirements
============

* puredata
* pd-extended or mrpeach patches

http://puredata.info

Installation
============

No installation required, simply open the patches in pdextended.

Documentation
=============

* Please ensure you have pdextended installed, and the path to the patches it provides correctly set in Path or Startup.
* Add the directory containing pdOSCseq to the Path or Startup configuration.
* Open a new file:
	* create a [pos] object: it contains the tempo and the transport of the sequencer,
	* create as many [pos.OSCdest IP port] object as needed
	* for each sequence you want to be played
		* create a sequence patch based upon the patch called jean.pd, save it to myfile.pd (replace myfile by what you like). The file must be in the working directory.
		* create a [pos.sequence myfile] object

jean.pd
=======

A sequence file is composed by:
* a number of steps, this has to be manually set in the "number of steps" part of the file,
* an OSC prefix: this is the common part of every OSC messages that this sequence will send. If no common part exists, let it empty,
* a list of by-step OSC messages which will be sent each time the matching step will be encountered.


