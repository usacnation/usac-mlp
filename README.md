# USAC Multiloop Messages

Extensions to the MyLaps Mutliloop protocol (MLP) have been added to preserve backward compatibility while supporting concepts not included in the original MLP specification. Notably, time zones, team driving, virtual loops and virtual sectors.

## Common URLs & Ports (per series)

### Porsche Sprint Challenge

- Multiloop: timing.usacnation.com:20837
- RMonitor: timing.usacnation.com:20854
- WS: wss://timing.usacnation.com/ws/psc
- Timing: [https://timing.usacnation.com/live/?channel=psc](https://timing.usacnation.com/live/?channel=psc)
- GPS: [https://timing.usacnation.com/gps/?channel=psc](https://timing.usacnation.com/gps/?channel=psc)

Questions? [timing@usacnation.com](timing@usacnation.com)

### SRO America

- Multiloop: timing.usacnation.com:50003
- RMonitor: timing.usacnation.com:50000
- WS: wss://timing.usacnation.com/ws/sro
- Timing: [https://timing.usacnation.com/live/?channel=sro](https://timing.usacnation.com/live/?channel=sro)
- GPS: [https://timing.usacnation.com/gps/?channel=sro](https://timing.usacnation.com/gps/?channel=sro)

Questions? [srotiming@usacnation.com](srotiming@usacnation.com)

## Naming Conventions

### Loops
- Fixed: `SF, SFPIT, POUT, PIN, IM1, IM2, VIN or VOUT (when used)`
- Virtual: `IM(1-99)(a-z) IM1a or IM3c`

### Sectors
- Sectors: `S1, S2, S3, PIT, VMAX (when used)`
- Virtual: `S(1-99)(a...z) S1a or S3b`

## $USAC:DRIVERID - Driver ID
This message is emitted on detecting driver changes for an Entry ($E).

|Fieldname|Data description|Comments|
|-|-|-|
|MLP Entry ID|0 - 1024|Entry ID from $E command|
|Timestamp|0-FFFFFFFF|Time in milliseconds (hex characters)|
|Driver ID|0-9 (string) |Driver ID selection for driver, provided by Driver ID hardware in use|
|Driver Name|Michael Schumacher|Name of active driver|

## $USAC:S - Sectors
Sent when a fixed or virtual sector is completed. Note that virtual sectors may not be included in the $T definition.

|Fieldname|Data description|Comments|
|-|-|-|
|MLP Entry ID|0 - 1024|Entry ID from $E command|
|Timestamp|0-FFFFFFFF|Time in milliseconds (hex characters)|
|Name|0-FFFFFFFF|Name of section|
|Elapsed time|0-FFFFFFFF|Time in milliseconds (hex characters)|

## $USAC:TZ - Timezone
The timezone and current timestamp of the on-site USAC data relay routing messages from the MLP and other sub systems.

|Fieldname|Data description|Comments|
|-|-|-|
|Timezone|America/Los_Angeles|IANA Timezone|
|Timestamp|0-FFFFFFFF|Time in milliseconds (hex characters)|


## Series Colors

### SRO America

#### GTWCA

Pro = White #FFFFFF

Pro-Am = Black #000000

Am = Red #E21F26

#### GTAM

SRO3 = Red #E21F26

GT2 = Blue #1D3C6F

GT4 = Yellow #F7EC13

#### GT4AM

Silver = Grey #A3A3A3

Pro-Am = Black #000000

Am = Red #E21F26

#### TCAM

TCX = Red #E21F26

TC = Blue #1D3C6F

TCA = Yellow #F7EC13

### Porsche Sprint Challenge

991 NA = #BF0D2B

991 UW = #BF0D2B

992 M NA = #006298

992 M UW = #006298

992 NA = #BCBCBC

992 UW = #BCBCBC

Cay M NA = #FFCD00

Cay NA = #FFFFFF

Cay UW = #FFFFFF

Cay M UW = #FFCD00
