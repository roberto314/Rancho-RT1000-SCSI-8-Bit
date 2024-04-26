# Rancho-RT1000-SCSI-8-Bit
Recreation of a bootable ISA 8-Bit SCSI Card.

![](pics/RT1000-Front.jpg)

There can be one PAL on the Card (GAL20L8), this is for the floppy part only.
BIOS EPROM is a 27C128 Type, but only 8k are used.

[Schematic](schematic/Rancho%20RT1000/pdf/Rancho%20RT1000%20SCSI%20Controller.pdf)

For now there is no plan to manufacture the board.

Card works in my XT but the ASPI driver doesn't

Heads and Sectors working:

Tested with MSDOS 5.

(spc = Sectors/Cluster, spf = Sectors/FAT)

* C: 1023 / H:2  / S:32 32 MB (FAT16/4) spc=4,spf=0x40: works
* C: 1023 / H:4  / S:32 64 MB (FAT16/6) spc=4,spf=0x80: non-system disk
* C:  511 / H:8  / S:32 64 MB (FAT16/6) spc=4,spf=0x80: non-system disk
* C: 1015 / H:3  / S:43 65510 kB (FAT16/6) spc=4,spf=0x80: works
* C: 1023 / H:8  / S:32 128 MB (FAT16/6) spc=4,spf=0x100: non-system disk
* C: 1007 / H:5  / S:52 128 MB (FAT16/6) spc=4,spf=0x100: works
* C: 1021 / H:9  / S:57 261800 kB (FAT16/6) spc=8,spf=0x100: works
* C: 1023 / H:9  / S:57 262627 kB (FAT16/6) spc=16,spf=0x100: non-system disk
* C: 1010 / H:17  / S:60 515072 kB (FAT16/6) spc=16,spf=0xFC: works
* C: 1011 / H:31  / S:62 948 MB (FAT16/6) spc=32,spf=0xEE: works