# USAC Multiloop Messages

Extensions to the MyLaps Mutliloop protocol (MLP) have been added to preserve backward compatibility while supporting concepts not included in the original MLP specification. Notably, time zones, team driving, virtual loops and virtual sectors.


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
