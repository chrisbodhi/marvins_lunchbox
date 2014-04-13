marvins_lunchbox
================

Submission for 2014 NASA Space Apps Challenge.

This is a program for a LEGO Mindstorm NXT 2.0 robot.  The robot is the control
system for an automatically regulated lunar greenhouse prototype, to be
deployed at the lunar poles.  On the lunar poles, as with any pole, there are
long periods of sunlight coming in nearly horizontally, but from any direction
around the horizon.  The other half of the orbital period is dark.

The robotic greenhouse needs to position itself in orientation to the sun, when
it's available, and gather light into the greenhouse by opening its lid, which
has a curved reflective inner surface.  If there is too much light, so that the
contents are in danger of overheating, the lid needs to close itself somewhat
to catch less sunlight.  On a real lunar robotic greenhouse, the front of the
greenhouse would have solar panels on it for collecting energy to supplementally
heat the contents or to provide power for the colony.

This program controls two motors to open the lid and to rotate the platform
that the greenhouse is sitting on.  It uses two light sensors on either side of
the greenhouse to determine whether the greenhouse is pointed towards the sun.
A third motor is used as a lid position sensor in read-only mode, coaxial with
the hinges on the lid.  The lid is opened by pulling a lever downward by
spooling a string onto a spindle, until the lid positioning sensor indicates
that the lid is opened as far as needed.  A significant difference in the
readout values of the light sensors causes the rotation motor to turn the
greenhouse so as to balance out the light readings.

There are only two functions, positioning the greenhouse towards the light and
opening, half opening and closing the lid, and it may have made sense to have
independent threads for those two activities, but the code is simple enough
this way.  It just uses a main loop with 100ms delay at the start of each loop
to let the motors run.  The motors run at low speed to keep things from
happening too fast.
