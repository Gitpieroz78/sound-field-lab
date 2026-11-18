# Sound Field Lab

One offline page that shows how sound leaves loudspeakers and fills the space: the molecules
of the air, the pressure field, the level map, the directivity. It grew out of the
"Sound field of a simple source" animation made for Magu after the Meyer Sound
"System Design and Optimization" seminar (20-22 October 2026), and keeps everything he liked
in it: one molecule in a million, the highlighted molecule, colour by pressure,
"Fit 4 wavelengths", ÷2 / ×2, the time period switch, English, Spanish and Italian.

**Open it: https://gitpieroz78.github.io/sound-field-lab/**

Or download `index.html` and open it in any browser: it is a single file and works offline.
No installation, no account.

## The screen

- **Toolbar** (top): five ways of looking at the same field, and three cameras.
- **Transport** (bottom left): play / pause, ÷2, frequency, ×2, fit 4 λ, fit the scene.
- **Readings** (top left): frequency, period, on-screen cycle, speed of sound, wavelength,
  impedance ρc, absorption, screen width, the system and, when it is on, the microphone.
- **Side panel**: four tabs. Signal, Speakers, Medium, View.
- **Examples** (header): sixteen ready-made scenes, from the simple source to the end-fire sub array.

| Mode | What it shows |
|---|---|
| Molecules | one air molecule in a million, moving back and forth; flat dots from the top, shaded spheres at 45° |
| Pressure | the instantaneous pressure as colour (green +, red −), like a ripple tank |
| SPL map | the level in 3 dB bands, relative to the loudest point, like a prediction software |
| Surface | the pressure as the height of a moving sheet |
| Air block | a cube of air cut open: the wavefronts on its faces |

Cameras: **Top**, **45°** (isometric) and **Low** (grazing). Drag to rotate freely,
double-click to go back. Every mode works with every camera.

## Speakers tab

**Installations**

| Installation | Layout | Processing |
|---|---|---|
| Single | one box | — |
| Straight line | N boxes side by side | none: all at the same time |
| Arc | N boxes on a physical arc, aimed outwards | none |
| Arc delay | straight line | edges delayed as if they stood on the arc |
| Gradient (cardioid) | front and rear sub, both facing forward | rear inverted, delayed by depth / c |
| Inverted stack | rear sub turned backwards | rear inverted, delayed by depth / c |
| End-fire | N subs in line along the axis | front ones delayed by spacing / c |
| Left / right | two sources far apart | none: power alley and comb |
| End-fire wings | two end-fire lines on the sides, splayed outwards | as end-fire |
| Steered line | hanging column of 16 small drivers | linear delay ramp: the beam tilts up or down by the angle |
| Line array (J) | flown array, vertical section, J curve | none |
| Delay speaker | main and a delay downstream | delay = distance / c |

Delays are computed with the speed of sound of the medium you are in, as a system tech would
set them. The **processing table** lets you change gain, delay, polarity and mute of each box;
the layout then becomes custom until you press "Back to the installation defaults".

**Loudspeakers**: point, 18" sub, self-cardioid sub, 12" full range with 90° horn,
line array element, column, dipole, small 4" module (for steered columns). Each card shows its
directivity at 2 kHz. The acoustic centre is the middle of the front face, where the main driver sits:
the field starts there, and in the 3-D cameras the slice cuts the cabinet at that height.

**Flown systems hang.** The line array (J) and the steered line are computed in a vertical section:
the **Top** camera becomes **Side**, and at 45° the slice stands upright with the boxes hanging in it.

**Boundary**: free field, a wall behind the system, a side wall (a floor in the vertical
section), with distance and reflection. Modelled with a mirror-image source.

## Medium tab

Air (temperature and humidity), helium, hydrogen, CO₂ (also the cold fog of dry ice),
fresh water, sea water, steel, or any speed of sound. The panel gives λ, c, ρ, impedance
ρc and the absorption at the current frequency.

## The model, and its limits

- Steady-state sine at one frequency. Every box is a point source with a directivity,
  a gain, a delay and a polarity; the field is their complex sum.
- Directivity: cabinet baffle from omni (ka ≪ 1) to front hemisphere (ka ≫ 1); piston
  (Bessel J1) for the 12" woofer; constant-directivity horn; a 35 cm line source for the
  line array element in the vertical section; first-order cardioid for the self-cardioid sub.
- The SPL map uses the true 1/r spreading. Molecules, pressure, surface and block use a
  softer law so the far field stays visible, as in the original animation.
- Air absorption: ISO 9613-1. Sea water: Thorp. Speeds of sound: 331.4 + 0.607·T for air
  (Steve Bush, Audio Physics), Marczak for fresh water, Medwin for sea water.
- This is a teaching tool, not a prediction tool: no measured loudspeaker data, no room,
  no diffraction around cabinets. Use MAPP 3D or the manufacturer's software for design.

## Checks

The physics was checked with automated tests against independent values: the ISO 9613
absorption coefficients, the end-fire and gradient delays used in the Meyer Sound seminar,
cardioid rejection, the steering angle of a delayed line, the +6 dB of a wall close
behind a source and the size of a hanging line array box in the vertical section.
The page makes no network requests.

## Credits

Inspired by Dan Russell's acoustics animations (Penn State), the PhET "Waves" simulations,
Paul Falstad's ripple tank and the Meyer Sound seminar with Mauricio "Magu" Ramírez.
Nothing of theirs is included: the page is built from the equations above.
Free to copy, share and modify.
