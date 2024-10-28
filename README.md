# OREL-BDI-TO-ZXBUS-ADAPTER

The motivation to create such kind of adapter was a problem to find ready-to-solder boards for ZX Spectrum BDI.
Most of them were designed for specific clones and on Ukrainian marketplaces easily accessible was only boards for Orel BK.

A bit of history...

Somewhere in 2021 I soldered Harlequin 128k and as far as I played with Tape input, decided to expand and connect disk drive.
As I mentioned before, I faced mostly with BDI for Orel computer. Research had shown that all signals on the board were available on Harlequin ZXBUS Edge slot. So, I decided to give a chance and buy this adapter from one of sellers who stated that controller was tested and worked fine. Indeed, he sold DIY package with all components, so, itt was a huge plus.
After I received and soldered it, another kind of issue appeared - how to connect to Harlequin. Solder by wires ZXBUS Slot? Or something else?
I decided to go with adapter, on prototype board solder socket to connect controller and solder ZXBUS Slot with appropriate wiring.
This idea looked more reliable then just wires.

![First Try](https://github.com/user-attachments/assets/9f6a4674-6c41-4b27-9845-f5a056aa724c)

and...

![It Works!](https://github.com/user-attachments/assets/962e1164-06db-4440-8568-23cb4c16fcbc)

Later I expanded this adapter with optional Kempston Joystick interface, separate TRDOS rom that can in different modes and simple protection schematics for IC KP1818VG93.

The latest version looked like Frankenstien...

![image](https://github.com/user-attachments/assets/0a0ad775-c3cc-432a-9e29-f622c6610da8)

Over a time I collected on prototype board quite a lot of useful features and implemented them on final schematic:
 -  Optional Kempston Joystic, can be off, always on or depends on BETA signal from Orel BDI
 -  Optional ROM, can be off, only TRDOS part activated and stock ROM with Basic, TRDOS and Basic in optional ROM, in addition, 27C512 can be used without schematic changes
 -  Magic Button
 -  External +12v
 -  Safe +12V for 1818VG93
 -  Block external Kempston Joystic by /KJOY connected to A28 on ZXBUS Slot

So, I decided make it more beatuful. This is how it looks now!

![Front](https://github.com/user-attachments/assets/a6c51c50-5229-422b-8bf5-36aefec4eb1e)

![Back](https://github.com/user-attachments/assets/25d68d1c-d072-4bc9-bad7-413a0bf37dd5)

