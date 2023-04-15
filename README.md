## Introduction

This repo contains the source and binary files that I wrote
for the TRS-80 Model 3 in 1983 for controlling an
[XR-1](http://www.theoldrobots.com/rhinoarm.html).  The XR-1 was a
robotic arm manufactured by Rhino Robots of Champaign, Illinois.

The `disk` directory has the files in their original TRS-80 format.

The `src` directory has the converted files to a more readable form.
If they're binary, they're disassembled.  If they're an editor
save file or text, they're converted into a more conventional ASCII
format.

The initial versions of some files are what I believe were older
versions from a backup disk.  The final checkin on `master` is
what I believe were the files that I delivered to Rhino Robots for
their release.  Maybe some day an TRS-80 release disk for the XR-1
will turn up and I'll find out what was actually shipped.

## Files

The older copy of files I found saved under `disk`:
```
DEMO.BAS    An older version of the released `DEMO/BAS`
DEMO.BAK    The oldest known saved version of `DEMO/BAS`
RHINO.DVR   An older version of the released `RHINO/DVR`
RHINO.CMD   The oldest known saved version of `RHINO/DVR`
RS.BLD      Batch file for running `RHINO/BAS`
RS2.BLD     Batch file for loading `RHINO/BAS`
STARTUP.BLD Boot batch file initializing system and running `RHINO/BAS`
KBD.ASC     Help file describing arm motions controlled in real-time by keys
IJTB.ASC    Help file for pre-prgroamming a sequence of steps for each motor
XYZM.ASC    Help file for 'teach' subprogram
```
