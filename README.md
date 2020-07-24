# Dintree-Virtual

This repo contains Dintree Virtual Rack Modules for
[VCV Rack Virtual Eurorack DAW](https://vcvrack.com). Dintree is
the name of DIY open-source modules created by Andrew Kilpatrick of
Kilpatrick Audio. Please visit the links below for information about Andrew
and his DIY and commercial music and audio projects.

**Useful links:**

* [VCV Rack Virtual Eurorack DAW](https://vcvrack.com)
* [Dintree Synth DIY Site](http://dintree.com)
* [Andrew Kilpatrick](https://www.andrewkilpatrick.org)
* [Kilpatrick Audio](https://www.kilpatrickaudio.com)

## Modules

### V100 Scanner
**CV and voltage-control source sequencer / scanner**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V100-Scanner.png" />

The V100 Scanner module can work as a voltage-controlled input selector,
an input sequencer/switcher, or a source of randomly switching inputs. There
are 8 inputs which feed to the two output: OUT A and OUT B. One input is
always connected to the output at one time. The most recently selected input
(shown on the IN 1-8 LEDs) will come out of OUT A. The previously selected
input will come out of OUT B.

#### CTRL CV Mode

When the CTRL switch is up, CV mode is engaged. In this mode the CTRL IN
jack will be read as an analog CV input. A voltage from 0 to 10V will
activate one of the 8 inputs.

#### CTRL Clock Mode

When the CTRL switch is down, clock mode is engaged. In this mode the CTRL IN
jack will be read as a clock input. Each positive edge (>1V) will cause the
input selector to increment by 1 step.

#### RANGE Control

The RANGE control affects the range of outputs selected in either CV or clock
mode. Adjusting from 0-100% will select from 1 to 8 inputs to be included in
the scan. For instance a setting of around 50% will cause only inputs 1-4 to
be selected.

#### RAND Control

When the RAND switch is on, instead of sequentially choosing inputs, either by
CV or clock, a random input is selected. The RAND control observes the CV GAIN
setting so only inputs within the chosen range will be selected.

----

### V101 Dual Envelope
**Dual ADSR, AR and LFO Generator**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V101-Dual_Envelope.png" />

The V101 Dual Envelope module is a VCV clone of the [Dintree D101 Dual Envelope](http://dintree.com/#D101)
DIY module by Andrew Kilpatrick. You can use it as a simple ADSR, AR or LFO
with controllable attack and release times. Because it's based on an old
project based around a PIC16 microcontroller, the processing rate is only 1kHz
and the resolution is only 12 bits, so you might hear some steps in the output.
This is part of the clone and the charm! :)

Use the GATE IN jacks for gate signal inputs, and the ENV OUT jacks to get the
envelope or LFO outputs. Other than sharing a panel the two channels are
completely independent.

#### ADSR Mode

In ADSR mode the output works in a standard Attack, Decay, Sustain, Release mode.

#### AR Mode

In the AR mode a gate trigger starts the Attack / Release cycle which finishes
at its own time.

#### LFO Mode

In LFO mode the ATTACK and RELEASE controls affect the UP/DOWN time of the LFO
wave. A small additional feature not included in the hardware version is the
ability to use the GATE IN jack to start and stop the LFO. When switching to LFO
mode, the LFO will run automatically. However, if you input a gate signal, it
will start and stop the LFO. To reset auto-run mode without a gate preset,
simply switch the mode to another setting and back to LFO to reset it.

----

### V102 Output Mixer
**Four Input Mixer with Pan Pots and Output Level Meter**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V102-Output_Mixer.png" />

The V102 Output Mixer is a VCV clone of the [Dintree D102 Output Mixer](http://dintree.com/#D102)
DIY module by Andrew Kilpatrick. You can use it to mix 4 sources including smooth
level and pan controls for each input. There is a master output level and stereo
level meter. The meter indicates in steps of 6dB. The 0dB indicator is at 5Vpk
(10Vpp) which is considered the nominal level for most audio signals in Eurorack.

**VCV-only Features!**
Unlike the hardware version, the V102 also includes SUB INs jacks which feed
into the master mix bus. These can be used as a convenient effects return or as
a way to daisy-chain multiple mixers together.

Also included are the PRE OUT jacks which gives the pre-master mix and are not
affected by the level of the master control. These can be used for sending the
mix to a master reverb unit, for instance. If you bring the reverb back in via
the SUB IN jacks, you will have an effects loop controlled only by the reverb
module itself.

#### LEVEL Controls

The LEVEL controls affect the level of the input signal before it reaches the
pan pot. The control offers enough gain so that a mid-range setting is probably
best in most cases.

#### PAN Controls

The PAN controls alter the relative balance of the signal from an input into
the left and right mix busses. In the centre both channels are the same level.
Turning to an extreme end will cause about a 6dB boost in that output channel
and the other channel will go all the way to zero.

#### MASTER Control

The MASTER control affects the master output jacks. A midrange setting is
probably best in most cases. You can use the level meters to get a sense of the
overall output level. Aiming for around 0dB will ensure you drive the next
module with a decent level.

----

### V103 Reverb Delay
**Stereo Reverb and Delay Digital Effects Processor**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V103-Reverb_Delay.png" />

The V103 Reverb Delay is a VCV clone of the [Dintree D103 Reverb / Delay](http://dintree.com/#D103)
DIY module by Andrew Kilpatrick. It implements a simple yet effective reverb
algorithm that sounds good on many kinds of sound sources. There is also an
integrated delay line with up to 0.5 seconds of delay. There are three output
modes which offer different mono and stereo taps for useful delay sounds. A clip
LED indicates that the output signal might be too hot.

Please note that the V103 is designed for use with an effects loop and not pass
any dry signal.

#### Reverb Mix

The REVERB MIX control affects the amount of reverb in the output.

#### Delay Mix

The DELAY MIX control affects the amount of delayed signal in the output.

#### Delay Time

The DELAY TIME control sets the total length of the delay line. From 0-500ms.

#### Delay Type

The delay type switch chooses how the delayed signal is created:

- **DEL1** - Mono delay output.
- **DEL2** - Mono delay output plus stereo syncopated echos at 1/3 and 2/3 of the delay time.
- **DEL3** - Mono delay output plus stereo syncopated echos in 1/4 and 3/4 of the delay time.

#### Reverb Type

The reverb type switch selects one of two reverb sounds: BIG or SMALL.

----

### V104 Four Vs
**Four Channel Voltage Source**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V104-Four_Vs.png" />

The V104 Four Vs is a VCV clone of the [Dintree D104 Four Vs](http://dintree.com/#D104)
DIY module by Andrew Kilpatrick. It just produces four different voltages but
can be used for testing and triggering modules that require a voltage present
to operate. Unlike the hardware version, this module produces a bi-polar voltage
which is probably more useful. Also unlike the hardware version, the V104 has
on/off switches on the first two outputs. This lets you toggle on and off a
preset voltage.

#### VOLTAGE Controls

Each output has a dedicated voltage control. In the middle the output will be
about zero volts. By turning counter-clockwise you can create as much as -5V,
and by turning fully clockwise you can create as much as +5V. Manual control like
this is super useful for testing the range of voltages a module can handle as well
as manually adjusting some simpler modules that have input jacks to trigger
functions but no actual panel knobs or buttons to do it manually.

#### ON Switches

As an added bonus the first two channels feature ON switches which can be used
to turn on and off an output. If you want to test a particular voltage and then
try adding and removing that voltage, you can use the ON switch to do this
while leaving the voltage setting preset on the VOLTAGE control.

This can be used to manually generate gates or pulses that are easy to control
with the mouse.

----

### V105 Quad CV Proc
**Quad Control Voltage Processor**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V105-Quad_CV_Proc.png" />

The V105 Quad CV Proc is a VCV clone of the [Dintree D105 Quad CV Proc](http://dintree.com/#D105)
DIY module by Andrew Kilpatrick. It provides four channels of simple CV
processing which allow signals to be mixed, gained up and down, and inverted.
Two inputs on each channel are buffered and mixed together. The gain control
allows the final output to be set from 0x to 2x, offering both attenuation
and gain. Dual outputs from each section offer non-inverted (+) and inverted (-)
outputs.

#### Dual Inputs

Each of the four channels contain two inputs labeled A and B. You can feed two
signals and they will be actively buffered and mixed together before being sent
to the GAIN control. Use this as a basic signal mixer for CV or audio signals.

#### GAIN Controls

Each channel features a GAIN control which is wired after the two inputs are
mixed together. The GAIN controls are marked with the gain range from 0x to 2x.
At the full counter-clockwise position the output signal will be zero. At the
mid-range position the signal will be passed through unaltered. At the full
setting the signal will be doubled in amplitude. (200% or +6dB) Use this to
bring up weak signals or adjust the range of a signal into a module that lacks
any kind of input attenuator.

#### Dual Outputs

Once gained up or down, the signal is fed into a pair of outputs. The + output
carries a non-inverting signal. With the GAIN control set to mid-range, this
jack will create a perfect copy of the input. The - output carries an inverted
version of the signal. Use this instead of an "attenuverter" which is a clumsy
way to adjust gain and invert a signal. By using both outputs at the same time
you can easily make opposing CV signals for such things as panning circuits,
stereo phasing effects, or multiple filters which cross over for unique timbral
characteristics.

----

### V107 Dual Slew
**Dual Slew Rate Limiter**

<img align="right" src="https://github.com/hires/Dintree-Virtual/raw/master/res/images/V107-Dual_Slew.png" />

The V107 Dual Slew is a VCV clone of the [Dintree D107 Dual Slew](http://dintree.com/#D107)
DIY module by Andrew Kilpatrick. It simulates a basic RC filter slew rate limiter
which in the hardware version is based around a large variable resistor feeding a
pair of back to back electrolytic capacitors. The output of the RC junction is
sampled and buffered by a TL082 JFET input op amp which provides nearly zero
current draw. This means that the output signal lags the input by an amount that
is based solely on how fast the capacitors can be charged and discharged via the
variable resistor. A low impedance source is used internally so that the particular
signal fed into the module makes no difference. (in VCV rack of course this is
arbitrary since inputs don't load down cables... but anyway...)

The most common use of a slew rate limiter is for use in portamento by feeding
a control voltage through the slew unit and then into a VCO pitch CV input. But
because a simple RC filter has a log curve the pitch will not track evenly per
octave when used with a V/oct type of CV signal. Another use is for making a
simple lag processor to convert a single CV into multiple versions that have
slightly different offsets. This can create interesting effects with filters.
