                              
# MIDI Piano Christmas Light Show

- Author: Nathan Krause
- Email: nathankrause@verizon.net OR nkrause@ucsd.edu
- Last *Major* Update: 2/9/18 by Nathan Krause

## Overview:
  This simple program written for an Arduino with an open source MIDI shield
  allows the arduino to interpret serial data from the shield into which Key was
  pressed and the velocity in which the note was played (force applied to key).
  The midi protocal dictates an on byte and an off byte for the corresponding
  key that was played. [Learn More](http://www.indiana.edu/~emusic/etext/MIDI/chapter3_MIDI4.shtml) 
  about the MIDI instrument communication. 

## Origin and Project History:
  The project was inspired after from my neighborhood. Each year thousands of
  cars drive through each night of December to see the lights (yes it really is
  that crazy). And the displays were great; however, I noticed that kids would
  constanly try to interact with the display i.e. playing with reindeers and
  other figurines, but these static displays were not meant to be messed with by
  hundreds of little kids which wasn't fair to the owner of the house or the
  kid. Therefore, I decided to get rid of the static display at my house and
  introduce a dynamic light show which was synced to music inspired by hundreds
  of YouTube videos of peoples light shows. This was great and brought joy to a
  lot of kids and adults but it still lacked the user interactive feature. The
  next year I took the same backbone (relay box used to switch the lights off
  and on) and introduced the piano aspect. Anyone walking down the street could
  now play the piano and thus control the lights. It was an immediate success
  and I will have to post the reactions on YouTube soon (the kids could play
  better than most of the adults!). This piano feature was introduce in December
  of 2017 and will most likely receive multiple upgrades, either hardware or
  software functionality, before next December and hopefully every year
  thereafter. 



## Usage and Behaviour:
The program is currently written to look for a piano (or possibly and MIDI 
device) that is trasnmitting on channel 0. 
  
There are two modes:
   1) Default
   2) User
   
  "Default" is the base state in which all relays are on except for two that
  control lights illuminating the piano keys and the piano player. 
  In "user" mode the lights are initially all shut off except for the two relays
  controlling lights on the piano keys and one spotlight overheard illuminating 
  the current player. 
  
  Upon pressing a button, wired to digital pin on the arduino, the mode is
  switched from "Default" to "User". After initial deployment it
  was discovered that most people did not understand the button system so the 
  program was modified to accept any piano key press as a trigger to switch
  modes. The program doesn't switch back to "Default" until a key has not been
  pressed for 5 seconds implying the player has walked away in which the lights
  should all come back on. 



## Key Mapping:
  The keyboard has 66 keys (including sharps). Instead of having 66 different
  relays every 7 keys are interpreted the same and the sharps are mapped to
  trigger the same key as their flat note (I apologize if this is musically
  incorrect I'm a Computer Engineering Major not a Music ;) ). For example:
  pressing key 1, which is a C, triggers the same relay as any other C on the
  piano. C# also triggers the same relay as C flat. The reason for this is to
  allow each key a greater effect on the display. What I mean by that is rather
  than having one string linked to one key, a group of strings for a particular
  portion of the display are controlled by the same relay thereby giving a much
  large effect upon key press. This was derived after real world testing with
  the display and actual random players. 


## Future Improvements:
  1) Pattern recognition of certain songs and auto-completing the rest or some
     other response or rewared system.
  2) PWM Dimming. Unfortuneately the current setup uses Zero-Cross Solid State
     Relays which makes it possible to dim. Switching the Zero-Cross for Random
     Cross or any other MOSFET would be a viable solution.
  3) Projection mapping
  
     Suggestions are welcome...

## Parts Used:
* Arduino Mega 2560
* (3) eight channel solid state relay board
* MIDI piano 66 key
* [MIDI Shield by OLIMEX](https://www.olimex.com/Products/Duino/Shields/SHIELD-MIDI/open-source-hardware)
* Momentary Push Button
* Outlets (3 prong safety proof)


