## Introduction

This repo contains the source and binary files that I created
in 1983 for the TRS-80 Model 3 for controlling an
[XR-1](http://www.theoldrobots.com/rhinoarm.html).  The XR-1 was a
robotic arm manufactured by Rhino Robots of Champaign, Illinois.

The `disk` directory has the files in their original TRS-80 format.

The `src` directory has the converted files to a more readable form.
If they're binary, they're disassembled.  If they're an editor file
or text, they're converted into a more conventional ASCII format.

The initial committed versions of some files are what I believe were
older copies from a backup disk.  The final checkin on `master` is
what I believe were the files that I delivered to Rhino Robots for
their release.  Maybe some day a TRS-80 release disk for the XR-1
will turn up, and I'll finally find out what was actually shipped.

## Files

The files under `disk`:
```
DEMO.BAS    The BASIC program for demoing the XR-1
RHINO.DVR   The driver used by "DEMO/BAS" for communicating with the controller
RHINO.TST   The "RHINO/DVR" file with debug tracing enabled
RHINO.SRC   The Z-80 assembly source code for "RHINO/DVR"
RS.BLD      Batch file for running "RHINO/BAS"
STARTUP.BLD Boot batch file system initialization and running "RHINO/BAS"
KBD.ASC     Help file describing arm motions controlled in real-time by keys
IJTB.ASC    Help file for pre-programming a sequence of steps for each motor
XYZM.ASC    Help file for 'teach' subprogram
XYZS.ASC    Help file for 'XYZ' subprogram
```

In the top-level directory, `rhino.dmk` contains a DMK of the
fully bootable XR-1 demo disk for the TRS-80 Model 3.

The `RHINO/TST` driver is built from the `RHINO/SRC` assembly file,
but with lines 4700-4710 uncommented and with the added line:
```
04795         CALL    033AH
```
