# List of GCode commands needed for motor record support 

Organized by methods that need to be overwritten

## move 

set acceleration:
set velocity:
send position:

## moveVelocity 

set acceleration: (same as move)
set velocity: (same as move)
jog command:

## home 

set acceleration: (same as move)
set velocity: (same as move)
home command

## stop

stop command:

## poll

read position:
read moving status:
read limit status:
read drive on status:

## setPosition

set position:

## setClosedLoop (?)
