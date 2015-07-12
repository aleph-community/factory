Aleph Factory Set
=================

4 scenes for audio processing. All sharing common functions.

Created by: [**dspk**](http://llllllll.co/users/dspk)

https://vimeo.com/video/124805949

versions
--------
  - bees 0.6.0
  - aleph-lines 0.2.2

download
--------
- See the [releases](https://github.com/aleph-community/factory/releases) page

!!! WARNING !!!
  - Lines (versions 0.2.1 and earlier) fills the buffer with whitenoise when you load it, for a number of these scenes this will blast your/ears speakers when you load them up, turn the volume down!

OVERVIEW
--------

All these scenes share a common design, switches are used to shift modes which change the function of the encoders. The switches are set to momentary, i.e. only when holding them down is the new mode active, when you let go it will revert to CORE mode (See below) - if this is not a useful method you could set the switches to TOGGLE but you need to remember to turn them off to get back to CORE mode.
Also easy to use footpedals instead of switches.

ROUTING
-------

All scenes share the following audio routing (possibly idiosyncratic, it is designed for one mono guitar input and two drum machine / synth input)

ADC0
- -> output to DAC0 + DAC1 controlled in MIX mode
- -> send to delay lines controlled in MIX mode
- -> fixed routing out of DAC3

ADC1
- -> output to DAC0 + DAC1 controlled in MIX mode
- -> send to delay lines controlled in MIX mode

ADC2
- -> fixed routing to DAC2

( hacking note - there are 4 SUB operators already in place at 38,39,30,41 - changing the B value of these will allow you to adjust the panning of DEL0 and DEL1 out of the main outputs )

MODES
-----

**MIX**
hold down SW4 to access

- ENC0 - controls level of ADC0 + ADC1 to DAC0 + DAC1
- ENC1 - controls level of DEL0 to DAC0 + DAC1
- ENC2 - selects which input goes to delay lines ADC0 (turn left) or ADC1 (turn right)
- ENC3 - controls level of DEL0 to DAC0 + DAC1

**PITCH**
hold down SW3 to access

- ENC0 - controls pitch of DEL0
- ENC1 - controls cutoff of DEL0 (N.B. in GRANNYfactory this controls direction of playback, see video)
- ENC2 - controls pitch of DEL1
- ENC3 - controls cutoff of DEL1

( hacking note, the filter settings are quite soft for now, you could change these to make the cutoff control more pronounced )


**CORE**
activated when no SW are held down, functions change per scene

**MOD**
hold down SW1 to access, only available in RESDELAYfactory

- ENC0 - changes speed of modulation metro (turn fully left to turn off)
- ENC1 - changes depth of random DEL0 delay time modulation
- ENC2 - changes speed of modulation metro (turn fully left to turn off)
- ENC3 - changes depth of random DEL1 delay time modulation




SCENES
======

### WALK

*Random pitch jumping rhythmic pulsing*

SW1 - turns on/off random pitch increase
SW2 - turns on/off random pitch decrease

CORE
- ENC0 - changes rate of pitch jumps
- ENC1 - changes how many pitch jumps before input is resampled
- ENC2 - delay time of DEL1 (above 0 and DEL0 is sent to DEL1)
- ENC3 - DEL1 feedback

### RESDELAY

*simple dual delay line*

SW1 - MOD mode (see above)

CORE
- ENC0 - DEL0 delay time
- ENC1 - DEL0 feedback
- ENC2 - DEL1 delay time
- ENC3 - DEL1 feedback

### STASIS

*emulation of two EHX Freeze guitar pedals but with pitch control*

SW1 - momentary sample into DEL0
SW2 - momentary sample into DEL1

CORE
- ENC0 - rate of grains
- ENC1 - scrub playhead position of DEL0
- ENC2 - randomisation of playhead position ( DEL0 + DEL1 )
- ENC3 - scrub playhead position of DEL1

### GRANNY

*based on MicroGranny sampler*

N.B. - often has buffer noise issue, recommend that after loading you sample using SW1 for at least 30secs with no input. Also PITCH mode has slightly different functionality, see above.

SW1 - record into DEL0 (toggle switch)
SW2 - begin overdub recording (rec position is reset to 0 by playback loop)

CORE
- ENC0 - rate of grains
- ENC1 - rate of playhead movement through loop
- ENC2 - DEL1 delaytime
- ENC3 - DEL1 feedback
