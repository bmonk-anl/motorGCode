# List of GCode commands needed for motor record support 

Organized by methods that need to be overwritten

## General Notes:

* motor module methods can only reference one axis at a time, so only use g codes with 1 motor
    * need to figure out how to translate motor number into X, Y, Z, etc.

## move 

* set acceleration:
* set velocity:         F<velocity>
    * sets feed rate
* move:                 G1 X<position>

## moveVelocity 

* set acceleration: (same as move)
* set velocity: (same as move)
* jog command:

## home 

* set acceleration: (same as move)
* set velocity: (same as move)
* home command

## stop

* stop command:

## poll

* read position:
* read moving status:
* read limit status:
* read drive on status:

## setPosition

* set position: G92 X<position>

## setClosedLoop (?)
