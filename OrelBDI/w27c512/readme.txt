Due to schematic, there is place for 28c256, so to fit 27c512 instead, you need to make changes on the board or re-arrange rom. The second approach less insulating. Main difference between 28c256 and 27c512 that A14 pin has number 1 for 28c256 and 27 for 27c512. Since 27c512 has twice more room, it has A15 which has number 1. In order to switch between Basic and TRDOS, board drives pin number 1 and pin 27 pulled high. 

      28C256                  27C512
     --------                --------     
 1 -|A14  VCC|- 28       1 -|A15  VCC|- 28
 2 -|A12  /WE|- 27       2 -|A12  A14|- 27
 3 -|A7   A13|- 26       3 -|A7   A13|- 26
 4 -|A6    A8|- 25       4 -|A6    A8|- 25
 5 -|A5    A9|- 24       5 -|A5    A9|- 24
 6 -|A4   A11|- 23       6 -|A4   A11|- 23
 7 -|A3   /OE|- 22       7 -|A3   /OE|- 22
 8 -|A2   A10|- 21       8 -|A2   A10|- 21
 9 -|A1   /CE|- 20       9 -|A1   /CE|- 20
10 -|A0    D7|- 19      10 -|A0    D7|- 19
11 -|D0    D6|- 18      11 -|D0    D6|- 18
12 -|D1    D5|- 17      12 -|D1    D5|- 17
13 -|D2    D4|- 16      13 -|D2    D4|- 16
14 -|GND   D3|- 15      14 -|GND   D3|- 15
     --------                --------     

Based on that rom schema for 27c512 will look like this:

[0x0000-0x3FFF][0x4000-0x7FFF][0x8000-0xBFFF][0xC000-0xFFFF]
[   nothing   ][    48k.rom  ][   nothing   ][  trdos.rom. ]

cat zero-16kb.bin 48k.ROM zero-16kb.bin trd504t.rom > 48k+trdos-w27c512.rom
