# List of GCode commands needed for motor record support 

Organized by methods that need to be overwritten

## General Notes:

* motor module methods can only reference one axis at a time, so only use g codes with 1 motor
    * need to figure out how to translate motor number into X, Y, Z, etc.
* ";" is a the comment character in G-code
* Probably should use "realtime" Grbl commands when possible, which are single character ASCII
commands that can be sent at any time and will execute within 10s of milliseconds.

## move 

* set acceleration:
* set velocity:         F\<feed rate\>
    * sets feed rate (velocity) in either in/s or mm/s depending on how controller is configured
* move:                 G1 X\<position\>
    * can also move with specified feed rate: G1 X<position> F\<feed rate\>

## moveVelocity 

* set acceleration: (same as move)
* set velocity: (same as move)
* jog command: `$J=`
    * [Grbl jogging](https://github.com/gnea/grbl/wiki/Grbl-v1.1-Jogging)


## home 

* set acceleration: (same as move)
* set velocity: (same as move)
* home command `G28`
    *  `[X]`: flag to home X axis
    *  `[Y]`: flag to home Y axis
    *  `[Z]`: flag to home Z axis
    * Example: `G28 X Z ; home the X and Z axes`
    * Example: `G28 Y; home just the Y axis`

## stop

* stop command: `!`
    - `~` (Grbl realtime): Resume
    - `M0` is the G-code pause. `!` is probably better here

## poll

`?` gets a realtime status report which *should* be able to provide all the below info:
* position
* moving status
* limit status
* drive on status

## setPosition

* set position (coordinate system offset): `G92`
    * get the current value of the offset with the `$#` command

## setClosedLoop (?)
