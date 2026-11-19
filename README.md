# Sound Field Lab

One offline page that shows how sound leaves loudspeakers and fills the space: the molecules
of the air, the pressure field, the level map, the directivity. It grew out of the
"Sound field of a simple source" animation made for Magu after the Meyer Sound
"System Design and Optimization" seminar (20-22 October 2026), and keeps everything he liked
in it: one molecule in a million, the highlighted molecule, colour by pressure,
"Fit 4 wavelengths", ÷2 / ×2, the time period switch, English, Spanish and Italian, and now French too.

**Open it: https://gitpieroz78.github.io/sound-field-lab/** · **Guide: https://gitpieroz78.github.io/sound-field-lab/guide.html**

Or download `index.html` (and `guide.html`) and open them in any browser: single files that work offline.
No installation, no account.

## The screen

- **Toolbar** (top): five ways of looking at the same field, and three cameras.
- **Transport** (bottom left): play / pause, **Pulse** (fires a click), ÷2, frequency, ×2, fit 4 λ, fit the scene.
- **Readings** (top left): frequency, period, on-screen cycle, speed of sound, wavelength,
  impedance ρc, absorption, screen width, the system and, when it is on, the microphone.
- **Side panel**: four tabs. Signal, Speakers, Medium, View.
- **Examples** (header): nineteen ready-made scenes, from the simple source to the TM Array, a sub in a room and an end-fire pulse.
- **Save** (header): an image, a scene file, or a link to the scene (see below).
- **Guide** (header): opens `guide.html`, an illustrated guide in four languages with ten experiments;
  each experiment opens the lab already set up (`#x=<example>`).
- **Write to us** (header): a short form that opens a prefilled issue on the project's GitHub page,
  with a link to the current scene, the browser and the language. It needs a free GitHub account; no
  e-mail address is published.

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
| TM Array | subs flown in a column (Meyer Sound, Thomas Mundorf): line array in the vertical, point source in the horizontal | none |

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
section), or a **room**: four rigid walls (back, front and sides; in the vertical section back,
front, floor and ceiling) with width or height, length, distance of the system from the back wall,
reflection, and reflections up to order 1, 2 or 3. Modelled with mirror-image sources.

## Signal

- **Continuous sine**: a steady tone, what an analyser shows once the sound has settled.
- **Pulse (click)**: a short band-limited click (Ricker wavelet) centred on the chosen frequency.
  Each box fires at its own delay, with its gain and polarity: you watch the arrivals add up in
  front of an end-fire and spread out behind it, or the reflections come back from the walls.
  The click crosses the screen in about 4 s at the default animation speed (the readout shows
  the real time and how much it is slowed), then fires again. `P` fires a new click. The SPL map
  always shows the continuous sine.

## Save and share

- **Image (PNG)**: what you see, with a caption (system, frequency, medium, screen width), the SPL
  colour scale and the polar plot when they are on.
- **Copy link to this scene**: a link that opens the app exactly as it is now (system, processing,
  medium, view, camera). Good for preparing a lesson or sending one case to a colleague.
- **Save scene (file)** and **Open scene…**: the same, as a small JSON file.

## Medium tab

Air (temperature and humidity), helium, hydrogen, CO₂ (also the cold fog of dry ice),
fresh water, sea water, steel, or any speed of sound. The panel gives λ, c, ρ, impedance
ρc and the absorption at the current frequency.

## The model, and its limits

- Steady-state sine at one frequency. Every box is a point source with a directivity,
  a gain, a delay and a polarity; the field is their complex sum. The pulse is the same sum in
  the time domain, with the directivity taken at the centre frequency.
- Directivity: cabinet baffle from omni (ka ≪ 1) to front hemisphere (ka ≫ 1); piston
  (Bessel J1) for the 12" woofer; constant-directivity horn; a 35 cm line source for the
  line array element in the vertical section; first-order cardioid for the self-cardioid sub.
- The SPL map uses the true 1/r spreading. Molecules, pressure, surface and block use a
  softer law so the far field stays visible, as in the original animation.
- Air absorption: ISO 9613-1. Sea water: Thorp. Speeds of sound: 331.4 + 0.607·T for air
  (Steve Bush, Audio Physics), Marczak for fresh water, Medwin for sea water.
- Walls are rigid mirrors with one reflection factor for every frequency. There is no
  diffraction: objects that cast a shadow (a stage, a column, the cabinets themselves) would need
  a wave solver in the time domain.
- This is a teaching tool, not a prediction tool: no measured loudspeaker data, no frequency bands,
  no absorption by frequency on the walls. Use MAPP 3D or the manufacturer's software for design.

## Checks

The physics was checked with automated tests against independent values: the ISO 9613
absorption coefficients, the end-fire and gradient delays used in the Meyer Sound seminar,
cardioid rejection, the steering angle of a delayed line, the +6 dB of a wall close
behind a source, the size of a hanging line array box in the vertical section, the TM Array
pattern, the number of mirror images in a room and the arrival times of the end-fire click.
A second test checks that the four languages have every text. The pages make no network requests.

## Ideas and bugs

Use **Write to us** in the lab, or open an issue on this repository: suggestions, mistakes in the
physics and bugs are all welcome.

## Credits

Inspired by Dan Russell's acoustics animations (Penn State), the PhET "Waves" simulations,
Paul Falstad's ripple tank and the Meyer Sound seminar with Mauricio "Magu" Ramírez.
Nothing of theirs is included: the page is built from the equations above.
Free to copy, share and modify.
