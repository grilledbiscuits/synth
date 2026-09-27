# 808 kick schematic review

Reference: `../../references/808kick/808kick-reference-eddybergman.JPG`.

The schematic is arranged into trigger buffering, pulse/excitation, pitch/click,
resonator, decay feedback, and tone/clip/level/output sections. Named local nets
replace the original long wire runs. Existing component UUIDs were retained where
components were retained; the sheet UUID and parent project instance paths remain.

Circuit corrections made to follow the image:

- Restored the input NPN (Q3), second envelope NPN (Q4), and pitch NPN (Q5).
- Restored the 100K trigger pull-down, 10K PNP-base resistor, parallel 100K/15n
  excitation network, 4.7K excitation pull-down, and 100n tone capacitor.
- Corrected R3 to 4.7K (the reference uses a decimal comma).
- Corrected transistor connections, op-amp input polarities, TL074 supply pins,
  the timing capacitor connection, feedback paths, and potentiometer connections.
- Restored the optional clipper switch, and wired the unused TL074 section as a
  grounded unity-gain follower instead of the previous LED circuit.
- Matched the reference's 100n rail-to-rail bypass. C10 and D4 were removed;
  the previous LED resistor R20 is now the 100K trigger pull-down. The unsupported
  RV1 was removed. Panel controls are RV2 (pitch), RV3 (tone), RV4 (decay), RV5 (level).

Added wiring headers: J1 = trigger/GND, J2 = output/GND, J3 = VCC/GND/VSS.
SW1 uses a two-pin header footprint for an off-board SPST clipper switch.
Power flags declare the externally supplied rails and ground at the module boundary.
VCC is the positive rail; VSS is the negative rail.

All 50 physical components have assigned standard KiCad through-hole footprints.
No EasyEDA downloads were needed. Footprint availability and used pin/pad numbers
were checked against the installed KiCad 10 libraries. The panel potentiometer
footprints are Alps RK09K single vertical; check the actual purchased mechanical
parts and capacitor sizes before PCB layout. The unlabelled reference diodes retain
1N4148, as in the original project.

Validation: KiCad 10.0.6 standalone-sheet ERC: **0 errors, 0 warnings**.
All 33 exported nets were checked against pin groups transcribed from the reference,
and the rendered sheet was visually inspected. This is a schematic/reference check;
no circuit simulation or hardware measurement was performed.

Follow-up corrections (re-checked against the reference image):

- R5 (2.7K) is a pull-down from Q2's base to GND, with R6 (8.2K) feeding that
  same node. It had been wired in series between R6 and the base.
- R11 (470K) connects DECAY_OUT to BRIDGE (the 6.8K / 1M / C4-C5 junction), not
  to PITCH_BIAS on the pitch side of R10.

Re-layout: the sheet was rearranged to follow the reference drawing's layout, with
every connection drawn as a wire (no local net labels). The netlist was checked
identical to the corrected version above, and project ERC is clean for this sheet.
