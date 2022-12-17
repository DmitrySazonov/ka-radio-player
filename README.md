# ka-radio-player
This is a ka-radio player build project based on the ESP 32 and the UDA1334A DAC. The player uses the micro-usb connection as a power supply and has a mini-jack output for connecting to headphones or speakers.
There are 2 versions of cases in the project: for the screen 0.96" and 2.42".
![alt text](https://github.com/DmitrySazonov/ka-radio-player/blob/aa57e16a981c3e718910af9d376a0b30e7d48dfe/images/image01.jpeg?raw=true)

V2 version for 2.42 display

![alt text](https://github.com/DmitrySazonov/ka-radio-player/blob/9e1745583cbf18860f8c5a05a4be7fac21672450/images/v2/image0.jpeg?raw=true)

Demo video: https://youtu.be/d_xDyBW4TkM

## Components
- ESP 32 38P - https://sl.aliexpress.ru/p?key=cSeExr8
- UDA1334A DAC - https://sl.aliexpress.ru/p?key=o4eExBC
- Digital knob encoder - https://sl.aliexpress.ru/p?key=FfeExsv
- 2.42" OLED 4 pin display - https://sl.aliexpress.ru/p?key=MNKdxjn
or
0.96" OLED 4 pin display - https://sl.aliexpress.ru/p?key=2NeExj4
- 1K resistor


## Principal schema

![alt text](https://github.com/DmitrySazonov/ka-radio-player/blob/89df3c194219ddf57d0789007161f05c966c0ae5/stl/iradio_schema.png?raw=true)

### UDA1334A connection
| UDA1334A | ESP 32 |
|----------|--------|
| VIN      | 3V3    |
| GND      | GND    |
| DIN      | IO22 |
| WSEL     | IO25 |
| BCLK     | IO26 |

And add 1K resistor between **WSEL-GND**

### Display connection
| OLED Display | ESP 32 |
|--------------|--------|
| GND          | GND    |
| VDD          | 3V3    |
| SCK          | IO14   |
| SDA          | IO13   |

### Knob encoder connection
| Knob | ESP 32 |
|------|--------|
| GND  | GND    |
| S1   | IO17   |
| S2   | IO16   |
| KEY  | IO5    |
| 5V   | 3V3    |

## 3D Print options

### Printing position
![alt text](https://github.com/DmitrySazonov/ka-radio-player/blob/6cac8cc37e62230cf80ba3abce3fe80e388dbd4c/stl/print_position.png?raw=true)

## Player assembly

The player body is printed on a 3-d printer. Models for printing are in the **/stl** folder, select models according to the size of the display.

For mount used:
- M2.5x5 mm bolt (8pc) to mount the boards
- M3x5 mm bolt (4pc) to mount the cap to case
- M2.5x5 mm bolt (2pc or 4pc) to mount display to cap

For v2 case mount:
- M2.5x5 mm bolt (10pc) to mount the boards and case

## Connection

- Plug the usb charger into the micro-usb. 

**IMPORTANT!** 
It is recommended to use a good quality power supply, especially for the 2.42" display version. I use BASEUS Compact Quick Charger USB+Type-C, 3A, 20W.


- Plug your headphones or speakers (with built-in amplifier) into the mini-jack connector.

## Configuration

The project is based on the firmware [karadio32](https://github.com/karawin/Ka-Radio32)

To flash it, just download the archive from the [release](https://github.com/karawin/Ka-Radio32/releases) page and flash it as specified in the [README](https://github.com/karawin/Ka-Radio32#first-use) of the project.

For more information search for karadio32 guides on the internet.

To configure the radio in the settings under *"SOUND SETTINGS"* set it to **I2S**

## Control
- Encoder rotation - volume control.
- Press the encoder knob to start/stop playing
- Press and turn the encoder to switch between stations.
